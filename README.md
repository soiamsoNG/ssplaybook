# ssplaybook
Deploy [shadowsocks-go](https://github.com/shadowsocks/shadowsocks-go) by Ansible

Will enable and start shadowsocks-go as **ss-local** service

Can check the service status by
```
systemctl --user status ss-local
```

Test under Fedora 26

## Requirement
* ansible
* libselinux-pytohn

## Step 1
Write config to conifg_file/cofnig.json
```
server          your server ip or hostname
server_port     server port
local_port      local socks5 proxy port
method          encryption method, null by default (table), the following methods are supported:
                    aes-128-cfb, aes-192-cfb, aes-256-cfb, bf-cfb, cast5-cfb, des-cfb, rc4-md5, chacha20, salsa20, rc4, table
password        a password used to encrypt transfer
timeout         server option, in seconds
```
## Step 2
Run the palybook by
```
ansible-palybook ss.yml
```
