# NatCancelRedirect

- ea: `0x180046200`
- end: `0x180046346`
- name: `NatCancelRedirect`
- size: `326`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, int, __int16, int, __int16, int, __int16)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180088200`

## callees

- `0x180046200`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046244`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046244`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180046301`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180046301`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046313`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046313`
- `ntdll!NtDeviceIoControlFile` at `0x1800462e6`
- `ntdll!NtDeviceIoControlFile` at `0x1800462e6`
- `ntdll!RtlNtStatusToDosError` at `0x180046329`
- `ntdll!RtlNtStatusToDosError` at `0x180046329`

## pseudocode

```c

```
