# GetVolumeInformationA

- ea: `0x1800b54d0`
- end: `0x1800b5769`
- name: `GetVolumeInformationA`
- size: `665`
- prototype: `BOOL __stdcall(LPCSTR lpRootPathName, LPSTR lpVolumeNameBuffer, DWORD nVolumeNameSize, LPDWORD lpVolumeSerialNumber, LPDWORD lpMaximumComponentLength, LPDWORD lpFileSystemFlags, LPSTR lpFileSystemNameBuffer, DWORD nFileSystemNameSize)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800134a0`
- `0x1800b54d0`
- `0x1800b5770`
- `0x180197010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800b572b`
- `ntdll!RtlFreeUnicodeString` at `0x18018b159`
- `ntdll!RtlFreeUnicodeString` at `0x1800b572b`
- `ntdll!RtlFreeUnicodeString` at `0x18018b159`
- `ntdll!RtlInitUnicodeString` at `0x1800b566f`
- `ntdll!RtlInitUnicodeString` at `0x1800b56a4`
- `ntdll!RtlInitUnicodeString` at `0x1800b566f`
- `ntdll!RtlInitUnicodeString` at `0x1800b56a4`
- `ntdll!RtlSetLastWin32Error` at `0x1800b56db`
- `ntdll!RtlSetLastWin32Error` at `0x1800b575d`
- `ntdll!RtlSetLastWin32Error` at `0x1800b56db`
- `ntdll!RtlSetLastWin32Error` at `0x1800b575d`
- `ntdll!RtlInitAnsiStringEx` at `0x1800b551e`
- `ntdll!RtlInitAnsiStringEx` at `0x1800b551e`
- `ntdll!RtlFreeHeap` at `0x1800b56fe`
- `ntdll!RtlFreeHeap` at `0x1800b5720`
- `ntdll!RtlFreeHeap` at `0x18018b12d`
- `ntdll!RtlFreeHeap` at `0x18018b14e`
- `ntdll!RtlFreeHeap` at `0x1800b56fe`
- `ntdll!RtlFreeHeap` at `0x1800b5720`
- `ntdll!RtlFreeHeap` at `0x18018b12d`
- `ntdll!RtlFreeHeap` at `0x18018b14e`
- `ntdll!RtlAllocateHeap` at `0x1800b55bf`
- `ntdll!RtlAllocateHeap` at `0x1800b55fd`
- `ntdll!RtlAllocateHeap` at `0x1800b55bf`
- `ntdll!RtlAllocateHeap` at `0x1800b55fd`

## pseudocode

```c

```
