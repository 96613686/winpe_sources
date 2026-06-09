# GetVolumeInformationByHandleW

- ea: `0x1800b5ab0`
- end: `0x1800b5d95`
- name: `GetVolumeInformationByHandleW`
- size: `741`
- prototype: `BOOL __stdcall(HANDLE hFile, LPWSTR lpVolumeNameBuffer, DWORD nVolumeNameSize, LPDWORD lpVolumeSerialNumber, LPDWORD lpMaximumComponentLength, LPDWORD lpFileSystemFlags, LPWSTR lpFileSystemNameBuffer, DWORD nFileSystemNameSize)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b5770`

## callees

- `0x1800134a0`
- `0x1800b5ab0`
- `0x180188eb9`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x1800b5bd7`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800b5cdb`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800b5bd7`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800b5cdb`
- `ntdll!RtlSetLastWin32Error` at `0x1800b5c88`
- `ntdll!RtlSetLastWin32Error` at `0x1800b5c95`
- `ntdll!RtlSetLastWin32Error` at `0x1800b5c88`
- `ntdll!RtlSetLastWin32Error` at `0x1800b5c95`
- `ntdll!RtlFreeHeap` at `0x1800b5d16`
- `ntdll!RtlFreeHeap` at `0x1800b5d33`
- `ntdll!RtlFreeHeap` at `0x1800b5d63`
- `ntdll!RtlFreeHeap` at `0x18018b1b1`
- `ntdll!RtlFreeHeap` at `0x18018b1d0`
- `ntdll!RtlFreeHeap` at `0x1800b5d16`
- `ntdll!RtlFreeHeap` at `0x1800b5d33`
- `ntdll!RtlFreeHeap` at `0x1800b5d63`
- `ntdll!RtlFreeHeap` at `0x18018b1b1`
- `ntdll!RtlFreeHeap` at `0x18018b1d0`
- `ntdll!RtlAllocateHeap` at `0x1800b5b0e`
- `ntdll!RtlAllocateHeap` at `0x1800b5b99`
- `ntdll!RtlAllocateHeap` at `0x1800b5b0e`
- `ntdll!RtlAllocateHeap` at `0x1800b5b99`

## pseudocode

```c

```
