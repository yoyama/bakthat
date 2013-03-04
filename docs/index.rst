.. Bakthat documentation master file, created by
   sphinx-quickstart on Fri Mar  1 10:32:38 2013.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Bakthat
=======

Release v\ |version|.

Compress, encrypt (symmetric encryption) and upload files directly to Amazon S3/Glacier in a single command. Can also be used as a python module.

Here are some features:

* Compress with `tarfile <http://docs.python.org/library/tarfile.html>`_
* Encrypt with `beefish <http://pypi.python.org/pypi/beefish>`_ (**optional**)
* Upload/download to S3 or Glacier with `boto <http://pypi.python.org/pypi/boto>`_
* Local Glacier inventory stored with `DumpTruck <http://www.dumptruck.io/>`_
* Automatically handle/backup/restore a custom Glacier inventory to S3
* Delete older than, and `Grandfather-father-son backup rotation <http://en.wikipedia.org/wiki/Backup_rotation_scheme#Grandfather-father-son>`_ supported

You can restore backups **with** or **without** bakthat, you just have to download the backup, decrypt it with `Beefish <http://pypi.python.org/pypi/beefish>`_ command-line tool and untar it.

Be careful, if you want to be able to **backup/restore your glacier inventory**, you need **to setup a S3 Bucket even if you are planning to use bakthat exclusively with glacier**, all the archives ids are backed up in JSON format in a S3 Key.

Requirements
------------

* `aaargh <http://pypi.python.org/pypi/aaargh>`_
* `pycrypto <https://www.dlitz.net/software/pycrypto/>`_
* `beefish <http://pypi.python.org/pypi/beefish>`_
* `boto <http://pypi.python.org/pypi/boto>`_
* `GrandFatherSon <https://pypi.python.org/pypi/GrandFatherSon>`_
* `DumpTruck <http://www.dumptruck.io/>`_
* `byteformat <https://pypi.python.org/pypi/byteformat>`_
* `pyyaml <http://pyyaml.org>`_

Installation
------------

With pip/easy_install:

::

    $ pip install bakthat

From source:

::

    $ git clone https://github.com/tsileo/bakthat.git
    $ cd bakthat
    $ sudo python setup.py install


Next, you need to set your AWS credentials:

::

    $ bakthat configure


User Guide
----------

.. toctree::
   :maxdepth: 2

   user_guide

Developer's Guide
-----------------

.. toctree::
   :maxdepth: 2

   developer_guide


API Documentation
-----------------

.. toctree::
   :maxdepth: 2

   api


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
