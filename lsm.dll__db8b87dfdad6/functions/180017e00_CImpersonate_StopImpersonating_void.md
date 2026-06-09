# CImpersonate::StopImpersonating(void)

- ea: `0x180017e00`
- end: `0x180017e5b`
- name: `?StopImpersonating@CImpersonate@@QEAAJXZ`
- size: `91`
- prototype: `__int64 __fastcall(CImpersonate *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016ee4`
- `0x180017a50`
- `0x180030b90`
- `0x18005b080`
- `0x18005caf0`
- `0x18005d000`

## callees

- `0x180017e00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e43`
- `RPCRT4!RpcRevertToSelf` at `0x180017e14`
- `RPCRT4!RpcRevertToSelf` at `0x180017e14`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017e39`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017e39`

## pseudocode

```c

```
