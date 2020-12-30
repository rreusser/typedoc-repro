# typedoc-repro

Reproducing a possible typedoc issue. I am able to use `tsc` via `npm run build` successfully and obtain the expected output, but `typedoc` via `npm run build:docs` yields the failed assertion:

```
npm run build:docs

> typedoc-repro@ build:docs /path/to/tsdoctest
> typedoc

Debug: Arguments reader reading with: []
Debug: Arguments reader reading with: []
Debug: Using TypeScript 4.1.3 from /path/to/tsdoctest/node_modules/typescript/lib
Debug: Converting with 1 programs
Debug: Begin readme search at /path/to/tsdoctest/src
TypeDoc exiting with unexpected error:
{ AssertionError [ERR_ASSERTION]: The expression evaluated to a falsy value:

  assert(declaration)

    at Object.convertTypeAlias (/path/to/tsdoctest/node_modules/typedoc/dist/lib/converter/symbols.js:103:5)
    at Object.convertSymbol (/path/to/tsdoctest/node_modules/typedoc/dist/lib/converter/symbols.js:75:79)
    at Converter.convertExports (/path/to/tsdoctest/node_modules/typedoc/dist/lib/converter/converter.js:167:23)
    at Converter.compile (/path/to/tsdoctest/node_modules/typedoc/dist/lib/converter/converter.js:143:34)
    at Converter.convert (/path/to/tsdoctest/node_modules/typedoc/dist/lib/converter/converter.js:42:14)
    at Application.convert (/path/to/tsdoctest/node_modules/typedoc/dist/lib/application.js:151:31)
    at run (/path/to/tsdoctest/node_modules/typedoc/bin/typedoc:59:25)
    at Object.<anonymous> (/path/to/tsdoctest/node_modules/typedoc/bin/typedoc:26:1)
    at Module._compile (internal/modules/cjs/loader.js:778:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:789:10)
  generatedMessage: true,
  name: 'AssertionError [ERR_ASSERTION]',
  code: 'ERR_ASSERTION',
  actual: undefined,
  expected: true,
  operator: '==' }
```

