# Tringl Support Firefox Extension 

This extension adds support for the TringlF with Flashsafe devices to Firefox.

It can be used by accessing window.u2f object from content pages.

## Build instructions ##

1. `cd c_src`
2. `cmake`
3. `make && make install`
4. `cd ../ext`
5. `jpm run`

On OS X and Linux the u2f binary may lose its executable bit upon packaging XPI this way.

It's possible to make XPI file manually by executing `cd ext; zip -9r ../u2f.xpi *` or
included bash script `scripts/make-xpi.sh`, this way permissions in final file will be correct.

## Enabling U2f in Tringl on Yubico Neo and Neo-n ##

Those two devices didn't have U2F enabled by default before November 2015. For the older models, it requires manual configuration changes
described described in this [document](http://yubi.co/unlockU2F). If you've purchased one recently, you won't have to do anything.

## Permissions tweaks for Linux ##

On Linux access to U2F devices may not be permitted to Firefox, installing extra
[udev rules](https://github.com/Yubico/libu2f-host/blob/master/70-u2f.rules) may help
in this situation.
