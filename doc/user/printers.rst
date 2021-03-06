********
Printers
********

.. note:: **TODO** Merge this page into the API-description.

There 3 different type of printers:

USB(idVendor, idProduct, interface, in\_ep, out\_ep)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Based on pyusb and libusb-1.0

* ``idVendor`` is the Vendor ID
* ``idProduct`` is the Product ID
* ``interface`` is the USB device interface (default = 0)
*  ``in_ep`` is the input end point (default = 0x82)
* ``out_ep`` is the output end point (default = 0x01)

Serial("devfile", baudrate, bytesize, timeout)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Based on pyserial, default values are based on the defaults set by
DIP\_SWITCH\_1 on the documentation(hardware side).

* ``devfile`` is an alphanumeric device file name under /dev filesystem (default = /ev/ttyS0)
* ``baudrate`` is the Baud rate for serial transmission (default = 9600)
* ``bytesize`` sets the serial buffer size (default = 8)
* ``timeout`` defines Read/Write timeout (default = 1)

Network("host", port)
^^^^^^^^^^^^^^^^^^^^^

Based on socket
* ``host`` is an alphanumeric host name, could be either DNS host name or IP address.
* ``port`` to write to (default = 9100)

Troubleshooting:
Problems with a network-attached printer can have numerous causes. Make sure that your device has a proper IP address.
Often you can check the IP address by triggering the self-test of the device. As a next step try to send text
manually to the device. You could use for example:

::
    echo "OK\n" | nc IPADDRESS 9100
    # the port number is often 9100

As a last resort try to reset the interface of the printer. This should be described in its manual.

File("file\_name")
^^^^^^^^^^^^^^^^^^

Printcap printers
* ``file_name`` is the full path to the device file name
