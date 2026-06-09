# NatShutdownPortReservation

- ea: `0x180050920`
- end: `0x18005098c`
- name: `NatShutdownPortReservation`
- size: `108`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180050920`
- `0x180050994`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050962`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050962`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050980`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180050956`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180050956`
- `ntdll!NtClose` at `0x180050947`
- `ntdll!NtClose` at `0x180050947`

## pseudocode

```c

```
