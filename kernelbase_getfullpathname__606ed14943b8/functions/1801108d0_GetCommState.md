# GetCommState

- ea: `0x1801108d0`
- end: `0x180110b29`
- name: `GetCommState`
- size: `601`
- prototype: `BOOL __stdcall(HANDLE hFile, LPDCB lpDCB)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801895d0`
- `0x180189f80`

## callees

- `0x18004b9d0`
- `0x18004be40`
- `0x180053c30`
- `0x1801108d0`
- `0x180194f10`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x180110ace`
- `ntdll!NtWaitForSingleObject` at `0x180110aef`
- `ntdll!NtWaitForSingleObject` at `0x180110b10`
- `ntdll!NtWaitForSingleObject` at `0x1801a30b3`
- `ntdll!NtWaitForSingleObject` at `0x180110ace`
- `ntdll!NtWaitForSingleObject` at `0x180110aef`
- `ntdll!NtWaitForSingleObject` at `0x180110b10`
- `ntdll!NtWaitForSingleObject` at `0x1801a30b3`
- `ntdll!NtDeviceIoControlFile` at `0x18011098e`
- `ntdll!NtDeviceIoControlFile` at `0x1801109fd`
- `ntdll!NtDeviceIoControlFile` at `0x180110a68`
- `ntdll!NtDeviceIoControlFile` at `0x1801a3098`
- `ntdll!NtDeviceIoControlFile` at `0x18011098e`
- `ntdll!NtDeviceIoControlFile` at `0x1801109fd`
- `ntdll!NtDeviceIoControlFile` at `0x180110a68`
- `ntdll!NtDeviceIoControlFile` at `0x1801a3098`

## pseudocode

```c

```
