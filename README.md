###Usage###
1. **Command Line**
    ```bash
    $ node index.js --depth 8 pngdir/*.png
   OR
    $ node index.js --checkenv
   
    ```
    Options:
    ```bash
    $ node index.js --help
    Usage: C:\apps\nodejs\node.exe C:\dev\appMagics\ssutils\index.js [options] <files>
    
    Options:
      -f, --format          format of spritesheet (starling, sparrow, json, yaml, pixi.js, easel.js, zebkit, cocos2d)                                        [default: ""]
      --cf, --customFormat  path to external format template                                                                                                 [default: ""]
      -n, --name            name of generated spritesheet                                                                                                    [default: "spritesheet"]
      -p, --path            path to export directory                                                                                                         [default: "."]
      --fullpath            include path in file name                                                                                                        [default: false]
      --prefix              prefix for image paths                                                                                                           [default: ""]
      --trim                removes transparent whitespaces around images                                                                                    [default: false]
      --square              texture should be s square                                                                                                       [default: false]
      --powerOfTwo          texture width and height should be power of two                                                                                  [default: false]
      --validate            check algorithm returned data                                                                                                    [default: false]
      --scale               percentage scale                                                                                                                 [default: "100%"]
      --fuzz                percentage fuzz factor (usually value of 1% is a good choice)                                                                    [default: ""]
      --algorithm           packing algorithm: growing-binpacking (default), binpacking (requires passing width and height options), vertical or horizontal  [default: "growing-binpacking"]
      --padding             padding between images in spritesheet                                                                                            [default: 0]
      --sort                Sort method: maxside (default), area, width or height                                                                            [string]  [default: "maxside"]
      --divisibleByTwo      every generated frame coordinates should be divisible by two                                                                     [default: false]
      --cssOrder            specify the exact order of generated css class names                                                                             [default: ""]
      --depth               specify number of bits in color sample within pixel, default is 8.                                                               [default: 8]
      --width               specify maximum width of output image, required by algorithm binpacking.
      --height              specify maximum height of output image, required by algorithm binpacking.
      --checkenv            check if required tool convert and optipng exist in current environment.                                                         [default: false]

    ```
2. **Node.js**
    ```javascript
    var ssutils = require('ssutils');
    
        ssutils.generate('assets/*.png', {format: 'json'}, function (err) {
        if (err) throw err;

        console.log('spritesheet successfully generated');
    });
  ```