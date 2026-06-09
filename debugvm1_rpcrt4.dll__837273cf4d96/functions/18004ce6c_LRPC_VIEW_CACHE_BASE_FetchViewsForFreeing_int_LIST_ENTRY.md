# LRPC_VIEW_CACHE_BASE::FetchViewsForFreeing(int,_LIST_ENTRY *)

- ea: `0x18004ce6c`
- end: `0x18004d10f`
- name: `?FetchViewsForFreeing@LRPC_VIEW_CACHE_BASE@@QEAAXHPEAU_LIST_ENTRY@@@Z`
- size: `675`
- prototype: `void __fastcall(LRPC_VIEW_CACHE_BASE *__hidden this, int, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18004cdec`

## callees

- `0x18004baec`
- `0x18004ca30`
- `0x18004ce6c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18004cf1d`
- `ntdll!RtlLeaveCriticalSection` at `0x18004cf80`
- `ntdll!RtlLeaveCriticalSection` at `0x18004cf1d`
- `ntdll!RtlLeaveCriticalSection` at `0x18004cf80`
- `ntdll!RtlEnterCriticalSection` at `0x18004cee3`
- `ntdll!RtlEnterCriticalSection` at `0x18004cf4b`
- `ntdll!RtlEnterCriticalSection` at `0x18004cee3`
- `ntdll!RtlEnterCriticalSection` at `0x18004cf4b`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x18004cf8e`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x18004cf8e`

## pseudocode

```c

```
