# haproxy

```
vrrp_script haproxy {
    script "/usr/bin/pgrep haproxy"
}

vrrp_instance VI_1 {
    state MASTER
    interface enp1s0
    track_script {
        haproxy
    }
    unicast_src_ip 192.168.122.98
    unicast_peer {
        192.168.122.230
    }
    virtual_router_id 50
    priority 100
    virtual_ipaddress {
        192.168.122.122
    }
    authentication {
        auth_type PASS
        auth_pass 1234
    }
}
```
```
vrrp_script haproxy {
    script "/usr/bin/pgrep haproxy"
}

vrrp_instance VI_1 {
    state MASTER
    interface enp1s0
    track_script {
        haproxy
    }
    unicast_src_ip 192.168.122.230
    unicast_peer {
        192.168.122.98
    }
    virtual_router_id 50
    priority 100
    virtual_ipaddress {
        192.168.122.122
    }
    authentication {
        auth_type PASS
        auth_pass 1234
    }
}
```
