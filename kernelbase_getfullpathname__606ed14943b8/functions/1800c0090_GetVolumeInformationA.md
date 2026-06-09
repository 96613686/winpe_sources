# GetVolumeInformationA

- ea: `0x1800c0090`
- end: `0x1800c0366`
- name: `GetVolumeInformationA`
- size: `726`
- prototype: `BOOL __stdcall(LPCSTR lpRootPathName, LPSTR lpVolumeNameBuffer, DWORD nVolumeNameSize, LPDWORD lpVolumeSerialNumber, LPDWORD lpMaximumComponentLength, LPDWORD lpFileSystemFlags, LPSTR lpFileSystemNameBuffer, DWORD nFileSystemNameSize)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18004b9d0`
- `0x1800c0090`
- `0x1800c0370`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800c031b`
- `ntdll!RtlFreeUnicodeString` at `0x1801972c1`
- `ntdll!RtlFreeUnicodeString` at `0x1800c031b`
- `ntdll!RtlFreeUnicodeString` at `0x1801972c1`
- `ntdll!RtlInitUnicodeString` at `0x1800c0241`
- `ntdll!RtlInitUnicodeString` at `0x1800c027c`
- `ntdll!RtlInitUnicodeString` at `0x1800c0241`
- `ntdll!RtlInitUnicodeString` at `0x1800c027c`
- `ntdll!RtlSetLastWin32Error` at `0x1800c02b9`
- `ntdll!RtlSetLastWin32Error` at `0x1800c0354`
- `ntdll!RtlSetLastWin32Error` at `0x1800c02b9`
- `ntdll!RtlSetLastWin32Error` at `0x1800c0354`
- `ntdll!RtlInitAnsiStringEx` at `0x1800c00de`
- `ntdll!RtlInitAnsiStringEx` at `0x1800c00de`
- `ntdll!RtlFreeHeap` at `0x1800c02e2`
- `ntdll!RtlFreeHeap` at `0x1800c030a`
- `ntdll!RtlFreeHeap` at `0x180197289`
- `ntdll!RtlFreeHeap` at `0x1801972b0`
- `ntdll!RtlFreeHeap` at `0x1800c02e2`
- `ntdll!RtlFreeHeap` at `0x1800c030a`
- `ntdll!RtlFreeHeap` at `0x180197289`
- `ntdll!RtlFreeHeap` at `0x1801972b0`
- `ntdll!RtlAllocateHeap` at `0x1800c0185`
- `ntdll!RtlAllocateHeap` at `0x1800c01c9`
- `ntdll!RtlAllocateHeap` at `0x1800c0185`
- `ntdll!RtlAllocateHeap` at `0x1800c01c9`

## pseudocode

```c

```
