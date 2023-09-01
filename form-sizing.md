# Auto-growing text form controls

## Problem

Suppose that a web author wants to provide a text control that automatically resizes to a size fit to the entered text.
This can be achieved with some JavaScript code, but we propose a new CSS property to make it easier to achieve.

`<textarea>` and `<input type="text">` elements retain a constant size regardless of
the amount of the entered text, even if its sizing CSS property is set to `auto`.

## Solution

We propose a new CSS property called `form-sizing` to disable this behavior that is unique to form controls.

`form-sizing: auto;`
The default value. Maintains the current behavior.

`form-sizing: normal;`
Disables the form control's behavior of retaining a constant size, allowing size determination to be based on the content.

## Examples

The default `<textarea>` size is something like `10em` x `2lh`, and their size does not change by the amount of the entered text.

```html
<div style="width:11em; background:yellow; padding:4px;">
<textarea>
</textarea>
<br>
<textarea>
The quick brown fox jumps over the lazy dog.
</textarea>
</div>
```


If `form-sizing: normal` is specified, the following two `<textarea>` elements will have different sizes.
They are minimum sizes which fit to their content.

```html
<div style="width:11em; background:yellow; padding:4px;">
<textarea style="form-sizing:normal;">
</textarea>
<br>
<textarea style="form-sizing:normal;">>
The quick brown fox jumps over the lazy dog.
</textarea>
</div>
```

## Links

* HTML issue: https://github.com/whatwg/html/issues/6807
* CSSWG issue: https://github.com/w3c/csswg-drafts/issues/7542
* Chromestatus: https://chromestatus.com/feature/5176596826161152
