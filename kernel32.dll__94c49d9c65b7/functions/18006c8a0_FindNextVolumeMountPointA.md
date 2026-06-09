# FindNextVolumeMountPointA

- ea: `0x18006c8a0`
- end: `0x18006c9cb`
- name: `FindNextVolumeMountPointA`
- size: `299`
- prototype: `BOOL __stdcall(HANDLE hFindVolumeMountPoint, LPSTR lpszVolumeMountPoint, DWORD cchBufferLength)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callees

- `0x18000f920`
- `0x180038774`
- `0x18006c8a0`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18006c916`
- `ntdll!RtlSetLastWin32Error` at `0x18006c916`
- `ntdll!RtlInitUnicodeString` at `0x18006c94e`
- `ntdll!RtlInitUnicodeString` at `0x18006c94e`
- `ntdll!RtlFreeHeap` at `0x18006c9b3`
- `ntdll!RtlFreeHeap` at `0x18007bac5`
- `ntdll!RtlFreeHeap` at `0x18006c9b3`
- `ntdll!RtlFreeHeap` at `0x18007bac5`
- `ntdll!RtlAllocateHeap` at `0x18006c903`
- `ntdll!RtlAllocateHeap` at `0x18006c903`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006c8eb`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006c8eb`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18006c954`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18006c954`

## pseudocode

```c

```
