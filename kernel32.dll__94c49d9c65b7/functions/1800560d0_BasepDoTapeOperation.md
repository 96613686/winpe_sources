# BasepDoTapeOperation

- ea: `0x1800560d0`
- end: `0x18005618d`
- name: `BasepDoTapeOperation`
- size: `189`
- prototype: `__int64 __fastcall(HANDLE FileHandle, ULONG IoControlCode, PVOID InputBuffer, ULONG InputBufferLength, PVOID, ULONG)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180061760`
- `0x1800617c0`
- `0x180061800`
- `0x180061890`
- `0x1800618c0`
- `0x180061900`
- `0x180061950`
- `0x1800619e0`
- `0x18006d4a0`

## callees

- `0x18000f920`
- `0x1800560d0`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x18005614b`
- `ntdll!NtDeviceIoControlFile` at `0x18005614b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005616d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005616d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180056160`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180056160`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800560f8`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800560f8`

## pseudocode

```c

```
