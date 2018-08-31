# A simple color module for Elm

This module provides a simple way of describing colors with alpha transparency, based on this simple data structure:

```
type alias Color =
    { red : Int, green : Int, blue : Int, alpha : Float }
```

This module is intended as a stand-in to help port Elm 0.18 applications that were using the old `Color` module
there. That module was deliberately removed, so this module does not exactly replicate it.

## Why no HSLA representation/how is this different to the old `Color` module?

The pixels on your screen are colored in levels of RGB and graphics cards process colors as 4-vectors or RGB and alpha channel. An HSL represnetation can be useful, but will always be rendered down to RGBA. For this reason, I see no real loss of efficiency in support only the RGBA representation in this simple implementation.

The intention here is not to assist with the manipulation of colors and color spaces, it is simply to provide a convenient common representation of color for rendering purposes.

For this reason, the `Gradient` type and functions from the old `Color` module were also dropped. It is a case of do the math yourself, you will only find a minimal set of basics here.
