# doctest-conflict

Example of doctests failing because of ambiguous module names.

Running `stack build` and `stack test compat` after that results in

```
compat-0.1.0.0: test (suite: doctest-conflict-test)

src/Lib.hs:7: failure in expression `import Prelude.Compat'
expected: 
 but got: 
          <no location info>: error:
              Ambiguous module name ‘Prelude.Compat’:
                it was found in multiple packages:
                base-compat-0.10.5 base-compat-batteries-0.10.5

Examples: 2  Tried: 1  Errors: 0  Failures: 1

compat-0.1.0.0: Test suite doctest-conflict-test failed
Test suite failure for package compat-0.1.0.0
    doctest-conflict-test:  exited with: ExitFailure 1
Logs printed to console
```

This applies at least to the currenly (at the moment of writing this) stable
Stack version 1.9.3
