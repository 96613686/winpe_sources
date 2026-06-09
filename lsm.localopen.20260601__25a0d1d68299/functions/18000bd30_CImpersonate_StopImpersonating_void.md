# CImpersonate::StopImpersonating(void)

- ea: `0x18000bd30`
- end: `0x18000bda0`
- name: `?StopImpersonating@CImpersonate@@QEAAJXZ`
- size: `112`
- prototype: `__int64 __fastcall(CImpersonate *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b978`
- `0x18000cb34`
- `0x180032be0`
- `0x18005ea70`
- `0x180060530`
- `0x180060a60`

## callees

- `0x18000bd30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd81`
- `RPCRT4!RpcRevertToSelf` at `0x18000bd44`
- `RPCRT4!RpcRevertToSelf` at `0x18000bd44`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000bd71`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000bd71`

## pseudocode

```c

```
