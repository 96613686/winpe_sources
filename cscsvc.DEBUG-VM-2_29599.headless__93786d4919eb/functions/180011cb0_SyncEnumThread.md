# SyncEnumThread

- ea: `0x180011cb0`
- end: `0x180011edf`
- name: `SyncEnumThread`
- size: `559`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180011cb0`
- `0x180011ef0`
- `0x1800360c0`
- `0x180036394`
- `0x18003c460`
- `0x18004fef4`
- `0x180089010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180011dd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011d92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011d92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011d84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011d84`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011cd7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011cd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180011d6f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180011eba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180011d6f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180011eba`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011ed4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011ed4`
- `KERNEL32!TlsSetValue` at `0x180011e2d`
- `KERNEL32!TlsSetValue` at `0x180011e2d`

## string_xrefs

- `0x180011e3b`: `SyncEnumThread: Context: 0x%p`
- `0x180011e7d`: `SyncEnumThread: Thread initialization failed`
- `0x180011de3`: `SyncEnumThread: 0x%x`

## pseudocode

```c

```
