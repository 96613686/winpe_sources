# FindNextVolumeMountPointA

- ea: `0x180073ed0`
- end: `0x180074020`
- name: `FindNextVolumeMountPointA`
- size: `336`
- prototype: `BOOL __stdcall(HANDLE hFindVolumeMountPoint, LPSTR lpszVolumeMountPoint, DWORD cchBufferLength)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callees

- `0x18000ccf0`
- `0x18003b544`
- `0x180073ed0`
- `0x180084010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180073f52`
- `ntdll!RtlSetLastWin32Error` at `0x180073f52`
- `ntdll!RtlInitUnicodeString` at `0x180073f90`
- `ntdll!RtlInitUnicodeString` at `0x180073f90`
- `ntdll!RtlFreeHeap` at `0x180074001`
- `ntdll!RtlFreeHeap` at `0x180083c5a`
- `ntdll!RtlFreeHeap` at `0x180074001`
- `ntdll!RtlFreeHeap` at `0x180083c5a`
- `ntdll!RtlAllocateHeap` at `0x180073f39`
- `ntdll!RtlAllocateHeap` at `0x180073f39`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180073f1b`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180073f1b`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x180073f9c`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x180073f9c`

## pseudocode

```c

```
