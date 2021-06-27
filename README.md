<!--

@license Apache-2.0

Copyright (c) 2018 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->

# Iterator Symbol

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] [![dependencies][dependencies-image]][dependencies-url]

> Iterator [symbol][mdn-symbol] which specifies the default iterator for an object.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->

<section class="installation">

## Installation

```bash
npm install @stdlib/symbol-iterator
```

</section>

<section class="usage">

## Usage

```javascript
var IteratorSymbol = require( '@stdlib/symbol-iterator' );
```

#### IteratorSymbol

Iterator [`symbol`][mdn-symbol] which specifies the default iterator for an object.

```javascript
var s = typeof IteratorSymbol;
// e.g., returns 'symbol'
```

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

## Notes

-   The [symbol][mdn-symbol] is only supported in environments which support [symbols][mdn-symbol]. In non-supporting environments, the value is `null`.

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var IteratorSymbol = require( '@stdlib/symbol-iterator' );

var obj;
var v;

function iterator() {
    var iter;
    var i;

    i = -1;

    iter = {};
    iter.next = next;
    iter.return = done;

    if ( IteratorSymbol ) {
        // Allow the iterator to work with `for...of`:
        iter[ IteratorSymbol ] = iterator;
    }
    return iter;

    function next() {
        i += 1;
        return {
            'value': i,
            'done': false
        };
    }

    function done( value ) {
        if ( arguments.length === 0 ) {
            return {
                'done': true
            };
        }
        return {
            'value': value,
            'done': true
        };
    }
}

obj = iterator();
while ( v === void 0 || ( v.value < 10 && v.done === false ) ) {
    v = obj.next();
    console.log( v.value );
}
```

</section>

<!-- /.examples -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2021. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/symbol-iterator.svg
[npm-url]: https://npmjs.org/package/@stdlib/symbol-iterator

[test-image]: https://github.com/stdlib-js/symbol-iterator/actions/workflows/test.yml/badge.svg
[test-url]: https://github.com/stdlib-js/symbol-iterator/actions/workflows/test.yml

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/symbol-iterator/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/symbol-iterator?branch=main

[dependencies-image]: https://img.shields.io/david/stdlib-js/symbol-iterator.svg
[dependencies-url]: https://david-dm.org/stdlib-js/symbol-iterator/main

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://gitter.im/stdlib-js/stdlib/

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/symbol-iterator/main/LICENSE

[mdn-symbol]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol

</section>

<!-- /.links -->
