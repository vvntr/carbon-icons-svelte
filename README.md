<img alt="Carbon Icons Svelte" src="docs/banner.png" width="100%" />

# carbon-icons-svelte

[![NPM][npm]][npm-url]
[![Dependencies][deps]][deps-badge]
![npm](https://img.shields.io/npm/dt/carbon-icons-svelte)
[![Build][build]][build-badge]
[![Coverage][codecov-shield]][codecov]

> Svelte components for icons in digital and software products using the [Carbon Design System](https://github.com/carbon-design-system).

This library builds [Carbon Design System icons](https://www.carbondesignsystem.com/guidelines/icons/library) using [@carbon/icons](https://github.com/carbon-design-system/carbon/tree/master/packages/icons) with zero dependencies.

**Try it in the [Svelte REPL](https://svelte.dev/repl/931e6a3461434622adad0557579c0a29?version=3.16.7) or on [CodeSandbox](https://codesandbox.io/s/github/IBM/carbon-icons-svelte/tree/master/examples/webpack).**

## [Icon Preview](https://ibm.github.io/carbon-icons-svelte/)

## Getting Started

`carbon-icons-svelte` can be installed using `yarn` or `npm`.

```bash
yarn add carbon-icons-svelte
# OR
npm i carbon-icons-svelte
```

## Usage

Supported icon sizes include `16`, `20`, `24` and `32`. See the [Icon Preview](https://ibm.github.io/carbon-icons-svelte/) for a list of supported icons.

### Base Import

```html
<script>
  import { Add16 } from 'carbon-icons-svelte';
</script>

<Add16 />
```

### Individual Import (Recommended)

Import icons individually for faster compiling.

```js
import Add16 from 'carbon-icons-svelte/lib/Add16';
```

**Note:** Even if using the base import method, a modern application bundler (e.g. Rollup, Webpack) should treeshake unused icons.

#### Import Path Pattern

```js
import Icon from 'carbon-icons-svelte/lib/<ModuleName>';
```

See the [Icon Preview](https://ibm.github.io/carbon-icons-svelte/) for sample usage.

## API

### Props

All props are optional.

| Name            | Value                                           |
| --------------- | ----------------------------------------------- |
| id              | `string`                                        |
| aria-label      | `string`                                        |
| aria-labelledby | `string`                                        |
| tabindex        | `string`                                        |
| title           | `string`                                        |
| focusable       | `boolean` (default: `false`)                    |
| class           | `string`                                        |
| style           | `string` (default: `"will-change: transform;"`) |

#### `title` as a Slot

`title` can be passed as a prop or through the slot as an element.

```html
<Add16 title="Add" />
<!-- OR -->
<Add16>
  <title>Add</title>
</Add16>
```

### Forwarded Events

Event directives are forwarded directly to the SVG element.

```html
<Add16
  on:click="{() => {}}"
  on:mouseenter="{() => {}}"
  on:mouseover="{() => {}}"
  on:mouseleave="{() => {}}"
  on:keyup="{() => {}}"
  on:keydown="{() => {}}"
/>
```

### `data-carbon-icon` selector

Each icon embeds its module name in the `data-carbon-icon` selector for easier querying. This may be useful for automated testing in a headless browser.

```html
<svg data-carbon-icon="Add16">...</svg>
```

```js
// selects all carbon icons
document.querySelectorAll('[data-carbon-icon]');

// selects all `Add16` icons
document.querySelectorAll('[data-carbon-icon="Add16"]');
```

## Recipes

### Custom Fill Color

#### Using `class`

```html
<style>
  :global(svg.custom-class) {
    fill: blue;
  }
</style>

<Add16 class="custom-class" />
```

#### Using `style`

```html
<Add16 style="fill: blue" />
```

### Labelled

```html
<Add16 aria-label="Add" />
```

### Labelled with Focus

```html
<Add16 aria-label="Add" tabindex="0" />
```

### Labelled by

```html
<label id="addFile">Add file</label>

<Add16 aria-labelledby="addFile" />
```

## Limitations

This library supports the `ES` format. Currently, `UMD` is not supported.

Use Webpack or Rollup for application bundling (see [examples](examples) for sample set-ups).

## Examples

- [examples/Webpack](examples/webpack) (Try it on [CodeSandbox](https://codesandbox.io/s/github/IBM/carbon-icons-svelte/tree/master/examples/webpack))
- [examples/Rollup](examples/rollup) (Try it on [CodeSandbox](https://codesandbox.io/s/github/IBM/carbon-icons-svelte/tree/master/examples/rollup))

## [Changelog](CHANGELOG.md)

## [Contributing](CONTRIBUTING.md)

## License

[Apache 2.0](LICENSE)

[npm]: https://img.shields.io/npm/v/carbon-icons-svelte.svg?color=blue
[npm-url]: https://npmjs.com/package/carbon-icons-svelte
[deps]: https://david-dm.org/ibm/carbon-icons-svelte/status.svg
[deps-badge]: https://david-dm.org/ibm/carbon-icons-svelte
[build]: https://travis-ci.com/ibm/carbon-icons-svelte.svg?branch=master
[build-badge]: https://travis-ci.com/ibm/carbon-icons-svelte
[codecov]: https://codecov.io/gh/ibm/carbon-icons-svelte
[codecov-shield]: https://img.shields.io/codecov/c/github/ibm/carbon-icons-svelte.svg
