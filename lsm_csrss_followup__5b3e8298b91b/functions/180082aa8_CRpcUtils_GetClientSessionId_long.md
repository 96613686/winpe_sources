# CRpcUtils::GetClientSessionId(long *)

- ea: `0x180082aa8`
- end: `0x180082b55`
- name: `?GetClientSessionId@CRpcUtils@@SAJPEAJ@Z`
- size: `173`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18005e640`

## callees

- `0x1800074c0`
- `0x180082aa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082b1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082b1a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180082b10`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180082b10`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180082ad1`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180082ad1`

## pseudocode

```c

```
