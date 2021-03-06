# PaletteNet
.NET port of Android's Palette https://developer.android.com/reference/android/support/v7/graphics/Palette.html

## Example
```c#
var palette = PaletteHelper.From(new BitmapHelper(bitmap));
var color = palette.GetDarkMutedColor(Color.White);
```
or
```c#
using PaletteNet;
using PaletteNet.WriteableBitmapEx;
using Windows.UI.Xaml.Media.Imaging;
using Windows.UI;

public class UWPExample
{
    public Color GetDarkMutedColor(WriteableBitmap bitmap)
    {
        IBitmapHelper bitmapHelper = new WriteableBitmapHelper(bitmap);
        PaletteBuilder paletteBuilder = new PaletteBuilder();
        Palette palette = paletteBuilder.Generate(bitmapHelper);
        Color color = ColorConverter.IntToColor(palette.GetDarkMutedColorvalue());
        return color;
    }
}
```

Supported platforms:
- UWP >= 10.0.16299
- Android >= 8.0
- .Net 4.5

![alt text](https://github.com/tmk907/PaletteNetStandard/blob/master/images/example1.jpg "Example 1")
![alt text](https://github.com/tmk907/PaletteNetStandard/blob/master/images/example2.jpg "Example 2")
