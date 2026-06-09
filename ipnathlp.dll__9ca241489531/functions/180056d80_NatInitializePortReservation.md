# NatInitializePortReservation

- ea: `0x180056d80`
- end: `0x180056edf`
- name: `NatInitializePortReservation`
- size: `351`
- prototype: `ULONG __fastcall(unsigned __int16, struct _RTL_CRITICAL_SECTION **)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x180056d80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056e34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056e6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056e34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056e6a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056e43`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056e43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056e78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056e78`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180056ea3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180056ea3`
- `ntdll!RtlInitUnicodeString` at `0x180056dca`
- `ntdll!RtlInitUnicodeString` at `0x180056dca`
- `ntdll!NtCreateFile` at `0x180056e28`
- `ntdll!NtCreateFile` at `0x180056e28`
- `ntdll!RtlNtStatusToDosError` at `0x180056e80`
- `ntdll!RtlNtStatusToDosError` at `0x180056e80`
- `ntdll!NtClose` at `0x180056e5f`
- `ntdll!NtClose` at `0x180056e5f`

## pseudocode

```c

```
