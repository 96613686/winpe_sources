# LibraryCache::LoadLibraryExW(wchar_t const *,void *,ulong)

- ea: `0x1801bfed0`
- end: `0x1801c001d`
- name: `?LoadLibraryExW@LibraryCache@@QEAAPEAUHINSTANCE__@@PEB_WPEAXK@Z`
- size: `333`
- prototype: `HINSTANCE(LibraryCache *__hidden this, const wchar_t *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800dac50`

## callees

- `0x1801bfed0`
- `0x18020ba70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801bff72`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801bff72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801bfee5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801bfee5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801bff8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801c0009`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801bff8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801c0009`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801bff5b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801bff5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801bff47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801bff9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801bff47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801bff9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801bffa8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801bffa8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801bffb0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801bffb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bff80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bff80`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801bff16`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801bff16`

## pseudocode

```c

```
