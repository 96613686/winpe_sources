# CRpcUtils::GetClientSessionId(long *)

- ea: `0x180087700`
- end: `0x1800877c0`
- name: `?GetClientSessionId@CRpcUtils@@SAJPEAJ@Z`
- size: `192`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180062120`

## callees

- `0x1800077a0`
- `0x180087700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008777e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008777e`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18008776e`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18008776e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180087729`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180087729`

## pseudocode

```c

```
