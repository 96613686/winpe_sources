# Microsoft::Diagnostics::ApiServer::RegisterInterface(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,void *)

- ea: `0x1801ad868`
- end: `0x1801ada89`
- name: `?RegisterInterface@ApiServer@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAX@Z`
- size: `545`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801ad074`
- `0x1802549f8`

## callees

- `0x18002b7c0`
- `0x18002df00`
- `0x180064e8c`
- `0x18006f32c`
- `0x18008abf4`
- `0x18009c78c`
- `0x1800f9c3c`
- `0x180102bbc`
- `0x180142fcc`
- `0x1801ad868`
- `0x18020aac0`
- `0x1802f1d0c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801ad8ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801ad8ce`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1801ad9c2`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1801ad9c2`
- `RPCRT4!RpcEpRegisterW` at `0x1801ad9da`
- `RPCRT4!RpcEpRegisterW` at `0x1801ad9da`
- `RPCRT4!RpcServerInqBindings` at `0x1801ad97d`
- `RPCRT4!RpcServerInqBindings` at `0x1801ad97d`
- `RPCRT4!RpcServerRegisterIf3` at `0x1801ad933`
- `RPCRT4!RpcServerRegisterIf3` at `0x1801ad933`

## string_xrefs

- `0x1801ad8ed`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1801ad953`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1801ad99b`: `onecore\base\telemetry\utc\common\apiserver.cpp`

## pseudocode

```c

```
