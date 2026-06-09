# BridgeDriverHelper::BridgeNetworks(_NET_LUID_LH,_NET_LUID_LH)

- ea: `0x180080a8c`
- end: `0x180080cbd`
- name: `?BridgeNetworks@BridgeDriverHelper@@QEAAXT_NET_LUID_LH@@0@Z`
- size: `561`
- prototype: `void __fastcall(BridgeDriverHelper *__hidden this, union _NET_LUID_LH, union _NET_LUID_LH)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18011fe90`

## callees

- `0x18005f0c0`
- `0x1800759d8`
- `0x180075aac`
- `0x180080918`
- `0x180080a8c`
- `0x180080e90`
- `0x180088bac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180080b41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180080c83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180080b41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180080c83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180080ad3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180080ad3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080c74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080c74`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180080b89`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180080b89`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180080bf7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180080bf7`

## string_xrefs

- `0x180080ba1`: `Failed to open a handle to l2bridge driver.`
- `0x180080bb1`: `onecore\vm\dv\net\hns\service\common\helperlib\src\bridgedriverhelper.cpp`
- `0x180080c28`: `onecore\vm\dv\net\hns\service\common\helperlib\src\bridgedriverhelper.cpp`

## pseudocode

```c

```
