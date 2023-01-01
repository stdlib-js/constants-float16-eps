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

# Epsilon

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Difference between one and the smallest value greater than one that can be represented as a [half-precision floating-point number][half-precision-floating-point-format].

<section class="intro">

[Epsilon][machine-epsilon] is defined as

<!-- <equation class="equation" label="eq:epsilon_float16" align="center" raw="\epsilon = b^{-(p-1)}" alt="Epsilon for a half-precision floating-point number."> -->

<div class="equation" align="center" data-raw-text="\epsilon = b^{-(p-1)}" data-equation="eq:epsilon_float16">
    <img src="https://cdn.jsdelivr.net/gh/stdlib-js/stdlib@5d87cc7cb2c58aeb732872f89562d2c89571cc8a/lib/node_modules/@stdlib/constants/float16/eps/docs/img/equation_epsilon_float16.svg" alt="Epsilon for a half-precision floating-point number.">
    <br>
</div>

<!-- </equation> -->

where `b` is the radix (base) and `p` is the precision (number of radix bits in the significand). For [half-precision floating-point numbers][half-precision-floating-point-format], `b` is `2` and `p` is `11`.

</section>

<!-- /.intro -->

<section class="installation">

## Installation

```bash
npm install @stdlib/constants-float16-eps
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm` branch][esm-url].
-   If you are using Deno, visit the [`deno` branch][deno-url].
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd` branch][umd-url].

The [branches.md][branches-url] file summarizes the available branches and displays a diagram illustrating their relationships.

</section>

<section class="usage">

## Usage

```javascript
var FLOAT16_EPSILON = require( '@stdlib/constants-float16-eps' );
```

#### FLOAT16_EPSILON

Difference between one and the smallest value greater than one that can be represented as a [half-precision floating-point number][half-precision-floating-point-format].

```javascript
var bool = ( FLOAT16_EPSILON === 0.0009765625 );
// returns true
```

</section>

<!-- /.usage -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var abs = require( '@stdlib/math-base-special-abs' );
var maxabs = require( '@stdlib/math-base-special-maxabs' );
var randu = require( '@stdlib/random-base-randu' );
var FLOAT16_EPSILON = require( '@stdlib/constants-float16-eps' );

var bool;
var a;
var b;
var i;

function isApprox( a, b ) {
    var delta;
    var tol;

    delta = abs( a - b );
    tol = FLOAT16_EPSILON * maxabs( a, b );

    return ( delta <= tol );
}

for ( i = 0; i < 100; i++ ) {
    a = randu() * 10.0;
    b = a + (randu()*2.0e-3) - 1.0e-3;
    bool = isApprox( a, b );
    console.log( '%d %s approximately equal to %d', a, ( bool ) ? 'is' : 'is not', b );
}
```

</section>

<!-- /.examples -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   <span class="package-name">[`@stdlib/constants/float32/eps`][@stdlib/constants/float32/eps]</span><span class="delimiter">: </span><span class="description">difference between one and the smallest value greater than one that can be represented as a single-precision floating-point number.</span>
-   <span class="package-name">[`@stdlib/constants/float64/eps`][@stdlib/constants/float64/eps]</span><span class="delimiter">: </span><span class="description">difference between one and the smallest value greater than one that can be represented as a double-precision floating-point number.</span>

</section>

<!-- /.related -->

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

Copyright &copy; 2016-2023. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/constants-float16-eps.svg
[npm-url]: https://npmjs.org/package/@stdlib/constants-float16-eps

[test-image]: https://github.com/stdlib-js/constants-float16-eps/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/constants-float16-eps/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/constants-float16-eps/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/constants-float16-eps?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/constants-float16-eps.svg
[dependencies-url]: https://david-dm.org/stdlib-js/constants-float16-eps/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://gitter.im/stdlib-js/stdlib/

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/constants-float16-eps/tree/deno
[umd-url]: https://github.com/stdlib-js/constants-float16-eps/tree/umd
[esm-url]: https://github.com/stdlib-js/constants-float16-eps/tree/esm
[branches-url]: https://github.com/stdlib-js/constants-float16-eps/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/constants-float16-eps/main/LICENSE

[half-precision-floating-point-format]: https://en.wikipedia.org/wiki/Half-precision_floating-point_format

[machine-epsilon]: https://en.wikipedia.org/wiki/Machine_epsilon

<!-- <related-links> -->

[@stdlib/constants/float32/eps]: https://github.com/stdlib-js/constants-float32-eps

[@stdlib/constants/float64/eps]: https://github.com/stdlib-js/constants-float64-eps

<!-- </related-links> -->

</section>

<!-- /.links -->
