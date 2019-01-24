# pylint issue with init-hook and setup.cfg

```bash
$ pipenv run pylint --version
pylint 2.2.2
astroid 2.1.0
Python 3.7.2 (default, Dec 27 2018, 07:35:52)
[Clang 10.0.0 (clang-1000.11.45.5)]
```

## Working

`find . -name "*.py" -not -path '*/\.*' -exec pipenv run pylint --rcfile=.pylintrc '{}' +`

### Using .pylintrc: result

```bash

------------------------------------
Your code has been rated at 10.00/10
```

## Not working

`find . -name "*.py" -not -path '*/\.*' -exec pipenv run pylint --rcfile=setup.cfg '{}' +`

### Using setup.cfg: result

```bash
************* Module src.hello_world
src/hello_world.py:1:0: E0401: Unable to import 'libs.hello_world' (import-error)

--------------------------------------------------------------------
Your code has been rated at 0.00/10 (previous run: 10.00/10, -10.00)
```
