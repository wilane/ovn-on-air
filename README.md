# OVN on air

Let's make OVN, Open Virtual Networking, on MacBook Air!

## Setup

I'm using KVM/libvirt to have those three KVM instances on Air and
reachable through `hv11`, `hv12`, and `hv13`, respectively.  And
to make the playbook clean, I'm using ubuntu 16.04 for all three
KVM instances.

```
                      +------------+
                      |            |
                      |    hv11    |
                      |            |
                      +------+-----+
                             |
                             |
                             |
         +------------+      |     +------------+
         |            |      |     |            |
         |    hv12    |      |     |    hv13    |
         |            |      |     |            |
         +------+-----+      |     +------+-----+
                |            |            |
                |            |            |
+---------------+------------+------------+----------------+
|                                                          |
|                          air                             |
|                                                          |
+----------------------------------------------------------+

```

## Playbooks

### build.yml

[build.yml](build.yml) is to setup the build environment on hv11, as explained in
[Documentation/intro/install/debian.rst](https://github.com/openvswitch/ovs/blob/master/Documentation/intro/install/debian.rst).

```
air$ ansible-playbook build.yml
```

## References

Many thanks to all those docs!

- [OVN primar](http://blog.spinhirne.com/2016/09/a-primer-on-ovn.html)
- [OVN tutorial](http://openvswitch.org/support/dist-docs-2.5/tutorial/OVN-Tutorial.md.html)
- [OVN with Kubernetes](https://github.com/openvswitch/ovn-kubernetes/blob/master/README.md)

Happy Hacking!