# NatShutdownPortReservation

- ea: `0x18004cb40`
- end: `0x18004cb95`
- name: `NatShutdownPortReservation`
- size: `85`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18004cb40`
- `0x18004cb9c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cb76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cb76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004cb8e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004cb70`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004cb70`
- `ntdll!NtClose` at `0x18004cb67`
- `ntdll!NtClose` at `0x18004cb67`

## pseudocode

```c

```
