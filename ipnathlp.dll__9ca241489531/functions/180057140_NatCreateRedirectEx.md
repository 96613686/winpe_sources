# NatCreateRedirectEx

- ea: `0x180057140`
- end: `0x18005736d`
- name: `NatCreateRedirectEx`
- size: `557`
- prototype: `ULONG __fastcall(HANDLE FileHandle, int, char, int, __int16, int, __int16, int, __int16, int, __int16, int, char *, HANDLE Event, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800570a0`
- `0x180082180`

## callees

- `0x18004bc74`
- `0x180057140`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057214`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057214`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180057223`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180057223`
- `ntdll!NtDeviceIoControlFile` at `0x180057343`
- `ntdll!NtDeviceIoControlFile` at `0x180057343`
- `ntdll!RtlNtStatusToDosError` at `0x180057353`
- `ntdll!RtlNtStatusToDosError` at `0x180057353`

## pseudocode

```c

```
