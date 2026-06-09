# NlPrintRpcDebug(char const *,long)

- ea: `0x180040fe4`
- end: `0x180041387`
- name: `?NlPrintRpcDebug@@YAXPEBDJ@Z`
- size: `931`
- prototype: `void __fastcall(const char *, int)`
- caller_count: `12`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002346c`
- `0x18002a8e0`
- `0x180030078`
- `0x180031a3c`
- `0x180033f80`
- `0x180036420`
- `0x1800369f8`
- `0x180036c94`
- `0x180038f68`
- `0x18005b2b0`
- `0x18005c514`
- `0x18006e50c`

## callees

- `0x180007518`
- `0x18000e910`
- `0x18000f3e4`
- `0x180040fe4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004114b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041306`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004114b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041306`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041135`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800412f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041135`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800412f2`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800410ed`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800410ed`
- `RPCRT4!RpcErrorStartEnumeration` at `0x180041042`
- `RPCRT4!RpcErrorStartEnumeration` at `0x180041042`
- `RPCRT4!RpcErrorGetNextRecord` at `0x1800410c2`
- `RPCRT4!RpcErrorGetNextRecord` at `0x1800410c2`
- `RPCRT4!RpcErrorEndEnumeration` at `0x180041353`
- `RPCRT4!RpcErrorEndEnumeration` at `0x180041353`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180041175`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180041175`
- `ntdll!RtlLeaveCriticalSection` at `0x180041342`
- `ntdll!RtlLeaveCriticalSection` at `0x180041342`
- `ntdll!RtlEnterCriticalSection` at `0x180041095`
- `ntdll!RtlEnterCriticalSection` at `0x180041095`

## string_xrefs

- `0x180041126`: ` [%lu] ComputerName is %ws\n`
- `0x18004115b`: ` [%lu] ProcessID is %d\n`
- `0x1800411d2`: ` [%lu] Generating component is %d\n`

## pseudocode

```c

```
