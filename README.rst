Minifold
==============

.. _git: https://github.com/nokia/minifold.git 
.. _wiki: https://github.com/nokia/minifold/wiki

==================
Overview
==================

Minifold is a Python module able to interact with various data sources (e.g. CSV, LDAP, SQL, twitter, etc.) and to query/combine/aggregate them with database-like operators.

For more information, visit the wiki_.

==================
Dependencies
==================

Minifold requires `Python 3 <http://python.org/>`.

To use all connectors, it is advised to also install the following packages:

- ``python3-ldap3`` for LDAP connector;
- ``python3-pycountry``, ``python3-urllib``, ``python3-urllib3`` for HAL connector;
- ``python3-pycountry``, ``python3-urllib3``, ``python3-xmltodict`` for DBLP connector;
- ``python3-tweepy`` for Twitter connector.

For example, under Debian-based distribution, run:

.. code:: shell

  sudo apt-get update
  sudo apt-get install python3 python3-ldap3 python3-pycountry python3-urllib python3-urllib3 python3-tweepy python3-xmltodict

==================
Installation steps
==================
From sources
------------------

- The sources are available on git_.

.. code:: shell

  mkdir ~/git
  cd ~/git
  git clone https://github.com/nokia/minifold.git
  cd minifold
  python3 setup.py build
  sudo python3 setup.py install

==================
Testing
==================

1. Test scripts are provided in ``tests/`` directory.
2. Install ``python3-pytest``. 
3. Run tests as follows:

.. code:: shell

  cd ~/git/minifold/tests/
  pytest-3

==================
Packaging
==================

Install the packages needed to build ``.rpm`` and ``.deb`` packages:

- ``python3-setuptools``
- ``python3-stdeb`` for ``.deb`` packages
- ``rpm`` for ``.rpm`` packages

For example, under Debian-based distribution, run:

.. code:: shell

  sudo apt-get update
  sudo apt-get install python3-setuptools python3-stdeb rpm

To build ``.rpm`` package (in ``dist/``), run:

.. code:: shell

  cd ~/git/minifold/tests/
  python3 setup.py bdist_rpm

To build ``.deb`` package (in ``deb_dist/``), run:

.. code:: shell

  python3 setup.py --command-packages=stdeb.command bdist_deb

