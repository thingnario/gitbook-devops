# Python Language Conventions

## Configurations {#docs-internal-guid-4fc3ad29-200a-1126-798c-c9f3e176c38d}

* Linter: pycodestyle
* setup.cfg

```text
[pycodestyle]
max-line-length = 100

[tool:pytest]
addopts = --cov=<package name>
```

* .editorconfig

```text
root = true
indent_style = space
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true

[*.md]
trim_trailing_whitespace = false

[*.py]
indent_size = 4
```

## Editor Instructions {#docs-internal-guid-4e664964-200b-e570-034f-101ee81763d4}

### Atom

```bash
apm install atom-python-virtualenv \
  editorconfig \
  atom-ide-ui \
  ide-python
pip install python-language-server
pip install \
https://github.com/capitalm-chen/pydocstyle/archive/match-against-file.zip
```

### ~/.atom/config.cson {#docs-internal-guid-8b9bc1f1-200c-d15a-6ae5-6890a8d725f8}

```javascript
"*":
  "atom-python-virtualenv":
    getWorkOnHome: "$HOME/.virtualenvs;"
  "ide-python":
    pylsPlugins:
      pycodestyle:
        maxLineLength: 100
      pydocstyle:
          enabled: true
```

## Code Template {#docs-internal-guid-8b9bc1f1-200d-b22e-e367-fc700728e8ff}

```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-
"""Module summary.

Module descriptions.

Example:
    Module usage description.

        $ ./example_module.py

Continue module description.

Attributes:
    module_level_variable1 (int): description.

"""
from __future__ import absolute_import, print_function, unicode_literals
```



## Naming {#docs-internal-guid-2982091e-200e-d6ae-44ea-2a5357fcc7ae}

* ClassNamesAreInCamelCase
* variables\_and\_functions\_are\_in\_snake\_case
* CONSTANTS\_ARE\_ALL\_CAPITAL
* \_private\_functions\_and\_variables\_are\_padded\_with\_a\_underscore

## Imports

Imports should be grouped in the following order:

1. standard library imports
2. related third party imports
3. local application/library specific imports

## Docstrings {#docs-internal-guid-8b9bc1f1-200f-00da-8f75-aa866790241a}

[Google style docstrings](http://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html)

## Tools {#docs-internal-guid-8b9bc1f1-200f-2d32-3cb8-3606a3b317af}

### Unittest

* Built-in unittest / pytest
* Coverage / pytest-cov

### Packaging

* setuptools

setup.py:

```python
#!/usr/bin/env python
from setuptools import setup


setup(
    name='thingnario_pyutils',
    version='1.0.1',
    description='thingnario Python SDK Library',
    maintainer='Freddie Hsinfu Huang',
    maintainer_email='freddie.hsinfu.huang@gmail.com',
    url='https://gitlab.com/thingnario/thingnario-pyutils/',
    packages=['thingnario', 'thingnario.solar'],
    install_requires=[
        'certifi==2018.1.18',
        'chardet==3.0.4',
        'coverage==4.5.1',
        'elasticsearch==5.4.0',
        'idna==2.6',
        'pyowm==2.8.0',
        'python-dateutil==2.6.1',
        'pytz==2017.2',
        'requests==2.18.4',
        'requests-mock==1.4.0',
        'six==1.11.0',
        'urllib3==1.22',
    ]
)
```



## References {#docs-internal-guid-8b9bc1f1-2010-12b2-6463-6121826d9be0}

* [https://www.python.org/dev/peps/pep-0008/](https://www.python.org/dev/peps/pep-0008/)
* [https://www.python.org/dev/peps/pep-0257/](https://www.python.org/dev/peps/pep-0257/)
* [https://google.github.io/styleguide/pyguide.html?showone=Comments\#Comments](https://google.github.io/styleguide/pyguide.html?showone=Comments#Comments)
* [http://sphinxcontrib-napoleon.readthedocs.io/en/latest/example\_google.html](http://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html)

