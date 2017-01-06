# rollup-plugin-image-base64

Import JPG, PNG, GIF and ~~SVG~~ files.

Fork of rollup-plugin-image to skip the part in which a `new Image()` is created and just return the base64 as String

## Installation

```bash
npm install --save-dev rollup-plugin-image-base64
```


## Usage

```js
// rollup.config.js
import imageBase64 from 'rollup-plugin-image-base64';

export default {
  entry: 'src/index.js',
  dest: 'dist/my-lib.js',
  plugins: [
    imageBase64()
  ]
};
```

You can now use images in your bundle like so:

```js
import logo from './rollup.png';

console.log(logo); // base64 of image as String
```

Images are encoded using base64, which means they will be 33% larger than the size on disk. You should therefore only use this for small images where the convenience of having them available on startup (e.g. rendering immediately to a canvas without co-ordinating asynchronous loading of several images) outweighs the cost.


## License

MIT

Original code by Rich Harris
