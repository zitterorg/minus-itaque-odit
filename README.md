# @zitterorg/minus-itaque-odit <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

Is this value a JS ArrayBuffer? This module works cross-realm/iframe, does not depend on `instanceof` or mutable properties, and despite ES6 Symbol.toStringTag.

## Example

```js
var assert = require('assert');
var isArrayBuffer = require('@zitterorg/minus-itaque-odit');

assert(!isArrayBuffer(function () {}));
assert(!isArrayBuffer(null));
assert(!isArrayBuffer(function* () { yield 42; return Infinity; });
assert(!isArrayBuffer(Symbol('foo')));
assert(!isArrayBuffer(1n));
assert(!isArrayBuffer(Object(1n)));

assert(!isArrayBuffer(new Set()));
assert(!isArrayBuffer(new WeakSet()));
assert(!isArrayBuffer(new Map()));
assert(!isArrayBuffer(new WeakMap()));
assert(!isArrayBuffer(new WeakRef({})));
assert(!isArrayBuffer(new FinalizationRegistry(() => {})));
assert(!isArrayBuffer(new SharedArrayBuffer()));

assert(isArrayBuffer(new ArrayBuffer()));

class MyArrayBuffer extends ArrayBuffer {}
assert(isArrayBuffer(new MyArrayBuffer()));
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@zitterorg/minus-itaque-odit
[npm-version-svg]: https://versionbadg.es/inspect-js/@zitterorg/minus-itaque-odit.svg
[deps-svg]: https://david-dm.org/inspect-js/@zitterorg/minus-itaque-odit.svg
[deps-url]: https://david-dm.org/inspect-js/@zitterorg/minus-itaque-odit
[dev-deps-svg]: https://david-dm.org/inspect-js/@zitterorg/minus-itaque-odit/dev-status.svg
[dev-deps-url]: https://david-dm.org/inspect-js/@zitterorg/minus-itaque-odit#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@zitterorg/minus-itaque-odit.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@zitterorg/minus-itaque-odit.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@zitterorg/minus-itaque-odit.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@zitterorg/minus-itaque-odit
[codecov-image]: https://codecov.io/gh/inspect-js/@zitterorg/minus-itaque-odit/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/inspect-js/@zitterorg/minus-itaque-odit/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/inspect-js/@zitterorg/minus-itaque-odit
[actions-url]: https://github.com/zitterorg/minus-itaque-odit/actions
