# GetVolumeInformationByHandleW

- ea: `0x1800c0710`
- end: `0x1800c0a19`
- name: `GetVolumeInformationByHandleW`
- size: `777`
- prototype: `BOOL __stdcall(HANDLE hFile, LPWSTR lpVolumeNameBuffer, DWORD nVolumeNameSize, LPDWORD lpVolumeSerialNumber, LPDWORD lpMaximumComponentLength, LPDWORD lpFileSystemFlags, LPWSTR lpFileSystemNameBuffer, DWORD nFileSystemNameSize)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800c0370`

## callees

- `0x18004b9d0`
- `0x1800c0710`
- `0x180194eb9`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x1800c0843`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800c0946`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800c0843`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800c0946`
- `ntdll!RtlSetLastWin32Error` at `0x1800c08fa`
- `ntdll!RtlSetLastWin32Error` at `0x1800c08fa`
- `ntdll!RtlFreeHeap` at `0x1800c0987`
- `ntdll!RtlFreeHeap` at `0x1800c09aa`
- `ntdll!RtlFreeHeap` at `0x1800c09e1`
- `ntdll!RtlFreeHeap` at `0x180197321`
- `ntdll!RtlFreeHeap` at `0x180197346`
- `ntdll!RtlFreeHeap` at `0x1800c0987`
- `ntdll!RtlFreeHeap` at `0x1800c09aa`
- `ntdll!RtlFreeHeap` at `0x1800c09e1`
- `ntdll!RtlFreeHeap` at `0x180197321`
- `ntdll!RtlFreeHeap` at `0x180197346`
- `ntdll!RtlAllocateHeap` at `0x1800c076e`
- `ntdll!RtlAllocateHeap` at `0x1800c07ff`
- `ntdll!RtlAllocateHeap` at `0x1800c076e`
- `ntdll!RtlAllocateHeap` at `0x1800c07ff`

## pseudocode

```c

```
