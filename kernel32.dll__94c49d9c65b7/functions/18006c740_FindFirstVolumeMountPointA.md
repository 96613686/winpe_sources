# FindFirstVolumeMountPointA

- ea: `0x18006c740`
- end: `0x18006c894`
- name: `FindFirstVolumeMountPointA`
- size: `340`
- prototype: `HANDLE __stdcall(LPCSTR lpszRootPathName, LPSTR lpszVolumeMountPoint, DWORD cchBufferLength)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callees

- `0x18000d6c0`
- `0x18000f920`
- `0x180038550`
- `0x18006c740`
- `0x18006ca50`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18006c886`
- `ntdll!RtlFreeUnicodeString` at `0x18006c886`
- `ntdll!RtlSetLastWin32Error` at `0x18006c7d8`
- `ntdll!RtlSetLastWin32Error` at `0x18006c7d8`
- `ntdll!RtlInitUnicodeString` at `0x18006c816`
- `ntdll!RtlInitUnicodeString` at `0x18006c816`
- `ntdll!RtlFreeHeap` at `0x18006c87b`
- `ntdll!RtlFreeHeap` at `0x18006c87b`
- `ntdll!RtlAllocateHeap` at `0x18006c7c5`
- `ntdll!RtlAllocateHeap` at `0x18006c7c5`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006c7ad`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006c7ad`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18006c81c`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18006c81c`

## pseudocode

```c

```
