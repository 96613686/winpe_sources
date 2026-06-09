# BasepDoTapeOperation

- ea: `0x18005b3d4`
- end: `0x18005b4ad`
- name: `BasepDoTapeOperation`
- size: `217`
- prototype: `__int64 __fastcall(HANDLE FileHandle, ULONG IoControlCode, PVOID InputBuffer, ULONG InputBufferLength, PVOID, ULONG)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180068140`
- `0x1800681a0`
- `0x1800681e0`
- `0x180068270`
- `0x1800682b0`
- `0x1800682f0`
- `0x180068340`
- `0x1800683d0`
- `0x180074c90`

## callees

- `0x18000ccf0`
- `0x18005b3d4`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x18005b458`
- `ntdll!NtDeviceIoControlFile` at `0x18005b458`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b486`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b486`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005b473`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005b473`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18005b3fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18005b3fc`

## pseudocode

```c

```
