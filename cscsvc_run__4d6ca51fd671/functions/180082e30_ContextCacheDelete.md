# ContextCacheDelete

- ea: `0x180082e30`
- end: `0x180082f98`
- name: `ContextCacheDelete`
- size: `360`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180082c98`
- `0x180082fa0`
- `0x1800836e8`

## callees

- `0x180036394`
- `0x1800413c8`
- `0x180082e30`
- `0x180089010`

## import_xrefs

- `ntdll!NtClose` at `0x180082ed2`
- `ntdll!NtClose` at `0x180082ed2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082ef5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082ef5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082ec3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082eeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082ec3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082eeb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180082f42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180082f56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180082f42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180082f56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082f34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082f48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082f34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082f48`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180082e4c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180082e4c`

## pseudocode

```c

```
