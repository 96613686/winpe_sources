# TellRpcToStartListening(DTC_SECURITY_LEVEL,ulong,ulong,ushort *,_UUID_VECTOR const *,int)

- ea: `0x180054d28`
- end: `0x180054f23`
- name: `?TellRpcToStartListening@@YAJW4DTC_SECURITY_LEVEL@@KKPEAGPEBU_UUID_VECTOR@@H@Z`
- size: `507`
- prototype: `int __high(enum DTC_SECURITY_LEVEL, unsigned int, unsigned int, unsigned __int16 *, const struct _UUID_VECTOR *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800588c0`

## callees

- `0x180003cf0`
- `0x18005430c`
- `0x1800543ec`
- `0x180054968`
- `0x180054d28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054ef9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054ef9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054d51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054d51`
- `RPCRT4!RpcServerInqBindings` at `0x180054e8a`
- `RPCRT4!RpcServerInqBindings` at `0x180054e8a`
- `RPCRT4!RpcEpRegisterA` at `0x180054ec6`
- `RPCRT4!RpcEpRegisterA` at `0x180054ec6`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180054e60`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180054e60`
- `RPCRT4!RpcBindingVectorFree` at `0x180054f0c`
- `RPCRT4!RpcBindingVectorFree` at `0x180054f0c`

## string_xrefs

- `0x180054d65`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x180054d96`: `InitRpcSecurity call failed`
- `0x180054de5`: `RpcServerRegisterIfEx is called to registry for Mutual Auth with Schannel`
- `0x180054e13`: `RpcServerRegisterIfEx is called to registry for Mutual Auth`

## pseudocode

```c

```
