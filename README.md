# postcss-animation.css-data

Autogenerated data for [postcss-animations](https://github.com/retyui/postcss-animations) plugin.

Parsed all `@keyframes` from [magic.css](https://minimamente.com/example/magic_animations/).

## Install

```bash
yarn add -D postcss-animation.css-data postcss-animations
# or npm i -D postcss-animation.css-data postcss-animations
```

## Use

```js
const           postcss = require('postcss');
const postcssAnimations = require('postcss-animations');

(async () => {
  const CSS = `.my-jackInTheBox { animation-name: jackInTheBox; }`;
  const PLUGINS = [
    postcssAnimations({
      data: [require('postcss-animation.css-data')],
      checkDuplications: true,
      disableCheckCssVariables: true
    })
  ];

  try {
    const { css, messages } = await postcss(PLUGINS).process(CSS/*, {from,to}*/);
    messages.map(msg => console.log(msg.toString()));

    console.log(css);
    /*
      .my-jackInTheBox { animation-name: jackInTheBox; }
      @keyframes jackInTheBox { }
    */
  } catch (e) {
    console.error(e);
  }
})();
```

## Other animation data:

* ![npm postcss-magic.css-data](https://img.shields.io/npm/dm/postcss-magic.css-data.svg) [postcss-magic.css-data](https://github.com/retyui/postcss-magic.css-data)
* ![npm postcss-mimic.css-data](https://img.shields.io/npm/dm/postcss-mimic.css-data.svg) [postcss-mimic.css-data](https://github.com/retyui/postcss-mimic.css-data)
* ![npm postcss-tuesday.css-data](https://img.shields.io/npm/dm/postcss-tuesday.css-data.svg) [postcss-tuesday.css-data](https://github.com/retyui/postcss-tuesday.css-data)

## Update data:

```bash
git clone https://github.com/retyui/postcss-animation.css-data
cd postcss-animation.css-data
yarn
yarn build
```