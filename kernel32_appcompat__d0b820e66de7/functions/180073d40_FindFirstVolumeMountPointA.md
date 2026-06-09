# FindFirstVolumeMountPointA

- ea: `0x180073d40`
- end: `0x180073ec2`
- name: `FindFirstVolumeMountPointA`
- size: `386`
- prototype: `HANDLE __stdcall(LPCSTR lpszRootPathName, LPSTR lpszVolumeMountPoint, DWORD cchBufferLength)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callees

- `0x18000ccf0`
- `0x180028f60`
- `0x18003b2c0`
- `0x180073d40`
- `0x1800740c0`
- `0x180084010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180073eae`
- `ntdll!RtlFreeUnicodeString` at `0x180073eae`
- `ntdll!RtlSetLastWin32Error` at `0x180073de5`
- `ntdll!RtlSetLastWin32Error` at `0x180073de5`
- `ntdll!RtlInitUnicodeString` at `0x180073e2c`
- `ntdll!RtlInitUnicodeString` at `0x180073e2c`
- `ntdll!RtlFreeHeap` at `0x180073e9d`
- `ntdll!RtlFreeHeap` at `0x180073e9d`
- `ntdll!RtlAllocateHeap` at `0x180073dcc`
- `ntdll!RtlAllocateHeap` at `0x180073dcc`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180073dae`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180073dae`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x180073e38`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x180073e38`

## pseudocode

```c

```
