<a name="image.drawing"></a>
## Simple Drawing Routines ##
This section includes simple routines to draw on images.

<a name="image.drawText"></a>
### [res] image.drawText(src, x, y, [options]) ###
Draws text onto a 3-channel Tensor (C x H x W) at the x-offset `x` and y-offset `y`.

The `options` table can be passed in to set color, background color, in-place etc.

Options:
* `color` - [table] The text color. A table of 3 numbers `{R, G, B}`, each number scaled between 0 and 255. For example, `red` is `{255, 0, 0}`
* bg - [table] The background color where text is drawn. Same format as color.
* size - [number] Size of the text to be drawn. `Default value = 1`.
* wrap - [boolean] If the text goes out of bounds, wrap it with a newline automatically. `default value = true`
* inplace - [boolean] If true, draws directly on the input tensor and returns it. `default value = false`

Example:

```lua
image.drawText(image.lena(), "hello\nworld", 10, 10)
image.drawText(image.lena(), "hello\nworld", 10, 20,{color = {0, 255, 0}, size = 5})
image.drawText(image.lena(), "hello\nworld", 10, 20,{color = {0, 255, 0}, bg = {255, 0, 0}, size = 5})
```