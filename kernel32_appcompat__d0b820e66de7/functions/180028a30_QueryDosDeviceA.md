# QueryDosDeviceA

- ea: `0x180028a30`
- end: `0x180028c17`
- name: `QueryDosDeviceA`
- size: `487`
- prototype: `DWORD __stdcall(LPCSTR lpDeviceName, LPSTR lpTargetPath, DWORD ucchMax)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000ccf0`
- `0x180028a30`
- `0x180028f60`
- `0x180084010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180028b3b`
- `ntdll!RtlFreeUnicodeString` at `0x180028bed`
- `ntdll!RtlFreeUnicodeString` at `0x180028b3b`
- `ntdll!RtlFreeUnicodeString` at `0x180028bed`
- `ntdll!RtlSetLastWin32Error` at `0x180028ab2`
- `ntdll!RtlSetLastWin32Error` at `0x180028ab2`
- `ntdll!RtlFreeHeap` at `0x180028b24`
- `ntdll!RtlFreeHeap` at `0x180028b24`
- `ntdll!RtlAllocateHeap` at `0x180028a9b`
- `ntdll!RtlAllocateHeap` at `0x180028a9b`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180028a7a`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180028a7a`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x180028ba2`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x180028ba2`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180028ae8`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180028ae8`

## pseudocode

```c

```
