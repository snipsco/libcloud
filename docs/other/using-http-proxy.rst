Using an HTTP proxy
===================

.. note::

    Support for HTTP proxies is only available in Libcloud trunk and higher.

Libcloud supports using an HTTP proxy for outgoing HTTP and HTTPS requests. At
the moment, using a proxy is only supported if you are using Python 2.7 or
above (it has been tested with 2.7, PyPy, 3.1, 3.3, 3.3, 3.4).

You can specify which HTTP proxy to use using one of the approaches described
bellow:

* By setting ``http_proxy`` environment variable (this setting is system /
  process wide)
* By passing ``http_proxy`` argument to the
  :class:`libcloud.common.base.LibcloudHTTPConnection` class constructor (this
  setting is local to the connection instance)
* By calling :meth:`libcloud.common.base.LibcloudHTTPConnection.set_http_proxy`
  method (this setting is local to the connection instance)

Known limitations
-----------------

* HTTP proxies which require authentication are not supported
* Python 2.6 is not supported

Examples
--------

This section includes some code examples which show how to use an HTTP proxy
with Libcloud.

1. Using http_proxy environment variable
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. sourcecode:: python

    http_proxy=http://<proxy hostname>:<proxy port> python my_script.py

2. Passing http_proxy argument to the connection class
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. literalinclude:: /examples/http_proxy/constructor_argument.py
   :language: python

3. Calling set_http_proxy method
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. literalinclude:: /examples/http_proxy/set_http_proxy_method.py
   :language: python