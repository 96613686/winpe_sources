# DuplicateSystemHandleCommon(void *,uchar,ulong,bool,void * *,bool)

- ea: `0x18001eae8`
- end: `0x18001ec11`
- name: `?DuplicateSystemHandleCommon@@YAJPEAXEK_NPEAPEAX1@Z`
- size: `297`
- prototype: `__int64 __fastcall(void *originalHandle, unsigned __int8 idlType, DWORD accessMask, bool restrictAccess, void **pDuplicatedHandle, bool suppressMarshalingSideTypeSpecificWork)`
- caller_count: `22`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d3ec`
- `0x18001d7e0`
- `0x18001d8a0`
- `0x18001e3a0`
- `0x18001e9e0`
- `0x18017b700`
- `0x1801b5940`
- `0x1801c2284`
- `0x1801c2350`
- `0x1801c2a80`
- `0x1801c3640`
- `0x1801c36a0`
- `0x1801c3700`
- `0x1801c4560`
- `0x1801c4710`
- `0x1801c4770`
- `0x1801c47d0`
- `0x1801c4830`
- `0x1801c4b50`
- `0x1801c4bb0`
- `0x1801c4c10`
- `0x1801c4c70`

## callees

- `0x18001eae8`

## import_xrefs

- `RPCRT4!I_RpcSystemHandleTypeSpecificWork` at `0x18001eb27`
- `RPCRT4!I_RpcSystemHandleTypeSpecificWork` at `0x18001eba8`
- `RPCRT4!I_RpcSystemHandleTypeSpecificWork` at `0x18001eb27`
- `RPCRT4!I_RpcSystemHandleTypeSpecificWork` at `0x18001eba8`
- `RPCRT4!I_RpcFreeSystemHandle` at `0x18001ec02`
- `RPCRT4!I_RpcFreeSystemHandle` at `0x18001ec02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebe0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001eb8a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001eb8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001eb51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001eb62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001eb51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001eb62`

## pseudocode

```c

```
