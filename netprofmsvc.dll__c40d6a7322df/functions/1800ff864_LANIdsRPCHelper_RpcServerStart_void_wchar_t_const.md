# LANIdsRPCHelper::RpcServerStart(void *,wchar_t const *)

- ea: `0x1800ff864`
- end: `0x1800ffb30`
- name: `?RpcServerStart@LANIdsRPCHelper@@SAKPEAXPEB_W@Z`
- size: `716`
- prototype: `__int64 __fastcall(void *, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800fdfa4`

## callees

- `0x18000fab0`
- `0x180010340`
- `0x1800a88a0`
- `0x1800ff864`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff8e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff8e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ffae4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ffae4`
- `RPCRT4!RpcBindingVectorFree` at `0x1800ffaca`
- `RPCRT4!RpcBindingVectorFree` at `0x1800ffaca`
- `RPCRT4!RpcEpRegisterW` at `0x1800ffa39`
- `RPCRT4!RpcEpRegisterW` at `0x1800ffa39`
- `RPCRT4!RpcServerInqBindings` at `0x1800ff9fe`
- `RPCRT4!RpcServerInqBindings` at `0x1800ff9fe`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800ff9cc`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800ff9cc`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800ff964`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800ff964`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800ff91c`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800ff91c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ff8d8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ff8d8`

## pseudocode

```c

```
