# NlPrintRpcDebug(char const *,long)

- ea: `0x18003e7dc`
- end: `0x18003eb39`
- name: `?NlPrintRpcDebug@@YAXPEBDJ@Z`
- size: `861`
- prototype: `void __fastcall(const char *, int)`
- caller_count: `12`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180022374`
- `0x1800291f4`
- `0x18002e478`
- `0x18002fdb4`
- `0x180032160`
- `0x1800344a4`
- `0x180034a68`
- `0x180034cfc`
- `0x180036df8`
- `0x180057434`
- `0x1800585a0`
- `0x180069580`

## callees

- `0x180007278`
- `0x18000e270`
- `0x18000ed34`
- `0x18003e7dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e925`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003eacb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e925`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003eacb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e915`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003eabd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e915`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003eabd`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003e8d3`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003e8d3`
- `RPCRT4!RpcErrorStartEnumeration` at `0x18003e83a`
- `RPCRT4!RpcErrorStartEnumeration` at `0x18003e83a`
- `RPCRT4!RpcErrorGetNextRecord` at `0x18003e8ae`
- `RPCRT4!RpcErrorGetNextRecord` at `0x18003e8ae`
- `RPCRT4!RpcErrorEndEnumeration` at `0x18003eb0c`
- `RPCRT4!RpcErrorEndEnumeration` at `0x18003eb0c`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18003e949`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18003e949`
- `ntdll!RtlLeaveCriticalSection` at `0x18003eb01`
- `ntdll!RtlLeaveCriticalSection` at `0x18003eb01`
- `ntdll!RtlEnterCriticalSection` at `0x18003e887`
- `ntdll!RtlEnterCriticalSection` at `0x18003e887`

## string_xrefs

- `0x18003e906`: ` [%lu] ComputerName is %ws\n`
- `0x18003e92f`: ` [%lu] ProcessID is %d\n`
- `0x18003e9a0`: ` [%lu] Generating component is %d\n`

## pseudocode

```c

```
