# SetCommState

- ea: `0x180189f80`
- end: `0x18018a3eb`
- name: `SetCommState`
- size: `1131`
- prototype: `BOOL __stdcall(HANDLE hFile, LPDCB lpDCB)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180189e90`
- `0x180189f80`

## callees

- `0x18004b9d0`
- `0x18004be40`
- `0x180053c30`
- `0x1801108d0`
- `0x180119a00`
- `0x180189f80`
- `0x180194f10`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x18018a06a`
- `ntdll!NtWaitForSingleObject` at `0x18018a2aa`
- `ntdll!NtWaitForSingleObject` at `0x18018a33b`
- `ntdll!NtWaitForSingleObject` at `0x18018a3b7`
- `ntdll!NtWaitForSingleObject` at `0x18018a06a`
- `ntdll!NtWaitForSingleObject` at `0x18018a2aa`
- `ntdll!NtWaitForSingleObject` at `0x18018a33b`
- `ntdll!NtWaitForSingleObject` at `0x18018a3b7`
- `ntdll!NtDeviceIoControlFile` at `0x18018a04d`
- `ntdll!NtDeviceIoControlFile` at `0x18018a289`
- `ntdll!NtDeviceIoControlFile` at `0x18018a320`
- `ntdll!NtDeviceIoControlFile` at `0x18018a39c`
- `ntdll!NtDeviceIoControlFile` at `0x18018a04d`
- `ntdll!NtDeviceIoControlFile` at `0x18018a289`
- `ntdll!NtDeviceIoControlFile` at `0x18018a320`
- `ntdll!NtDeviceIoControlFile` at `0x18018a39c`

## pseudocode

```c

```
