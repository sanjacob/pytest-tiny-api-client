# pytest-tiny-api-client

[![License: GPL  v2][license-shield]][gnu]

An official companion pytest plugin for the [`tiny-api-client`][tiny-api-client] library.

```python
from my_api import MyClient

def test_my_client(api_call):
    api_call.return_value = {"name": "Peter"}
    user = MyClient().find_user(user_id=...)
    assert user.name == "Peter"
```

One of the problems with testing functions that have been decorated is that
decoration happens at import time, which means the decorators cannot
be patched within each test without having to re-import the modules.

This plugin will patch these decorators at import time, and allow you to patch
the implementation during testing. To make this easier, this plugin exposes the
`api_call` fixture, which is a `unittest.mock.Mock` object which can be used to
test your endpoint methods with fake data.

For more details on how to use this fixture, check the documentation.



## Installation

```bash
pip install pytest-tiny-api-client
```



## Documentation

You can find the documentation at https://tiny-api-client.readthedocs.io



## License

[![License: LGPL  v2.1][license-shield]][gnu]

This software is distributed under the [Lesser General Public License v2.1][license], more information available at the [Free Software Foundation][gnu].


<!-- LINKS -->

[tiny-api-client]: https://github.com/sanjacob/tiny-api-client


<!-- LICENSE -->

[license]: LICENSE "Lesser General Public License v2.1"
[gnu]: https://www.gnu.org/licenses/old-licenses/lgpl-2.1.html "Free Software Foundation"
[license-shield]: https://img.shields.io/github/license/sanjacob/pytest-tiny-api-client


<!-- SHIELD LINKS -->

[pypi]: https://pypi.org/project/pytest-tiny-api-client


<!-- SHIELDS -->

[pypi-shield]: https://img.shields.io/pypi/v/pytest-tiny-api-client
[build-shield]: https://img.shields.io/github/actions/workflow/status/sanjacob/pytest-tiny-api-client/build.yml?branch=master
[docs-shield]: https://img.shields.io/readthedocs/tiny-api-client
