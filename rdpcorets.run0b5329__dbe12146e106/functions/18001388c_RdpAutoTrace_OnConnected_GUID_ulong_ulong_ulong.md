# RdpAutoTrace::OnConnected(_GUID,ulong,ulong,ulong)

- ea: `0x18001388c`
- end: `0x180013aef`
- name: `?OnConnected@RdpAutoTrace@@QEAAJU_GUID@@KKK@Z`
- size: `611`
- prototype: `__int64 __fastcall(RdpAutoTrace *__hidden this, struct _GUID *, unsigned int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d6e0`
- `0x180064830`

## callees

- `0x1800091a8`
- `0x18001388c`
- `0x18002e600`
- `0x180032f60`
- `0x180033da0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800139ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013a31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800139ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013a31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013935`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013935`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013921`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013921`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180013961`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180013961`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013941`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013941`

## pseudocode

```c

```
