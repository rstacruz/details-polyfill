# details-polyill

> Polyfill for the HTML5 `<details>` element

![](docs/images/details-polyfill.gif)

How it works
------------

In case the browser doesn't support `<details>`, it adds the following behaviors:

  - When clicking `details > summary`, it toggles the `open` attribute in `details`.

It also adds these CSS styles:

  - `summary:before` is styled with a disclosure triangle.
  - `details:not([open]) > :not(summary)` elements are hidden. (that is: all children of closed `details`, except `summary`)
  - The `<html>` element gets the `no-details` class.

Usage
-----

details-polyfill is available via npm.

```
npm install --save details-polyfill
```

Requiring it will immediately inject the needed behaviors.

```js
require('details-polyfill')
```

The file [index.js](index.js) is also usable as a standalone script.

Limitations
-----------

The `<details>` element must not have loose text inside it. Everything inside it should be in elements. For instance, this will not work:

```html
<details>
  <summary>More info...</summary>
  No info available.
</details>
```

But this will:

```html
<details>
  <summary>More info...</summary>
  <span>No info available.</span>
</details>
```

Also, since we're styling `summary:before`, you shouldn't use `summary:before` other than to create your own disclosure triangle.

Thanks
------

**details-polyfill** © 2016+, Rico Sta. Cruz. Released under the [MIT] License.<br>
Authored and maintained by Rico Sta. Cruz with help from contributors ([list][contributors]).

> [ricostacruz.com](http://ricostacruz.com) &nbsp;&middot;&nbsp;
> GitHub [@rstacruz](https://github.com/rstacruz) &nbsp;&middot;&nbsp;
> Twitter [@rstacruz](https://twitter.com/rstacruz)

[MIT]: http://mit-license.org/
[contributors]: http://github.com/rstacruz/details-polyfill/contributors

