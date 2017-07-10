# tahoe2pf
Generate (OpenBSD) pf rules from Tahoe-LAFS configuration. This tool should make
running Tahoe-LAFS nodes inside FreeBSD jails a bit more convenient. It assumes
to be run *inside* the Tahoe-LAFS jail and that the external /NATed interface is
stored in "$ext_if" as it is often the case.
Example run:
```
./tahoe2pf tahoe.cfg
# port redirection to tahoe node
rdr pass on $ext_if inet proto tcp to port 41304 -> 192.168.23.42 port 41304
```

# references
* [FreeBSD handbook Chapter 14: Jails](https://www.freebsd.org/doc/en_US.ISO8859-1/books/handbook/jails.html)
* [FreeBSD handbook Chapter 29.3: PF](https://www.freebsd.org/doc/en_US.ISO8859-1/books/handbook/firewalls-pf.html)
