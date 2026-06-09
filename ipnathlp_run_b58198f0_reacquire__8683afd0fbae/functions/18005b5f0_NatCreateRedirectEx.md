# NatCreateRedirectEx

- ea: `0x18005b5f0`
- end: `0x18005b836`
- name: `NatCreateRedirectEx`
- size: `582`
- prototype: `ULONG __fastcall(HANDLE FileHandle, int, char, int, unsigned __int16, int, __int16, int, __int16, int, __int16, int, char *, HANDLE Event, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18005b550`
- `0x180088820`

## callees

- `0x18004f880`
- `0x18005b5f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b6c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b6c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b6d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b6d9`
- `ntdll!NtDeviceIoControlFile` at `0x18005b7ff`
- `ntdll!NtDeviceIoControlFile` at `0x18005b7ff`
- `ntdll!RtlNtStatusToDosError` at `0x18005b815`
- `ntdll!RtlNtStatusToDosError` at `0x18005b815`

## pseudocode

```c

```
