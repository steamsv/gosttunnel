### 开启一个TCP转发服务

* 监听端口 `8080` 并转发到 `192.168.1.1:8080`

%accordion%命令行%accordion%
```
gost -L tcp://:8080/192.168.1.1:8080
```
%/accordion%


%accordion%yaml%accordion%
```
services:
- name: service-0
  addr: :8080
  handler:
    type: tcp
  listener:
    type: tcp
  forwarder:
    targets:
    - 192.168.1.1:8080
```
%/accordion%

%accordion%json%accordion%
```
{
    "services": [
        {
            "name": "service-0",
            "addr": ":8080",
            "handler": {
                "type": "tcp"
            },
            "listener": {
                "type": "tcp"
            },
            "forwarder": {
                "targets": [
                    "192.168.1.1:8080"
                ]
            }
        }
    ]
}
```
%/accordion%

### 开启多个TCP转发服务

* 监听端口 `8080` 并转发到 `192.168.1.1:8080`
* 监听端口 `8090` 并转发到 `192.168.1.1:8090`

%accordion%命令行%accordion%
```
gost -L tcp://:8080/192.168.1.1:8080 -L tcp://:8090/192.168.1.1:8090
```
%/accordion%


%accordion%yaml%accordion%
```
services:
- name: service-0
  addr: :8080
  handler:
    type: tcp
  listener:
    type: tcp
  forwarder:
    targets:
    - 192.168.1.1:8080
- name: service-1
  addr: :8090
  handler:
    type: tcp
  listener:
    type: tcp
  forwarder:
    targets:
    - 192.168.1.1:8090
```
%/accordion%

%accordion%json%accordion%
```
{
    "services": [
        {
            "name": "service-0",
            "addr": ":8080",
            "handler": {
                "type": "tcp"
            },
            "listener": {
                "type": "tcp"
            },
            "forwarder": {
                "targets": [
                    "192.168.1.1:8080"
                ]
            }
        }，
        {
            "name": "service-1",
            "addr": ":8090",
            "handler": {
                "type": "tcp"
            },
            "listener": {
                "type": "tcp"
            },
            "forwarder": {
                "targets": [
                    "192.168.1.1:8090"
                ]
            }
        }
    ]
}
```
%/accordion%
