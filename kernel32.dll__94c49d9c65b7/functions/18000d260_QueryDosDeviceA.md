# QueryDosDeviceA

- ea: `0x18000d260`
- end: `0x18000d413`
- name: `QueryDosDeviceA`
- size: `435`
- prototype: `DWORD __stdcall(LPCSTR lpDeviceName, LPSTR lpTargetPath, DWORD ucchMax)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000d260`
- `0x18000d6c0`
- `0x18000f920`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18000d34c`
- `ntdll!RtlFreeUnicodeString` at `0x18000d3ef`
- `ntdll!RtlFreeUnicodeString` at `0x18000d34c`
- `ntdll!RtlFreeUnicodeString` at `0x18000d3ef`
- `ntdll!RtlSetLastWin32Error` at `0x18000d2d6`
- `ntdll!RtlSetLastWin32Error` at `0x18000d2d6`
- `ntdll!RtlFreeHeap` at `0x18000d33b`
- `ntdll!RtlFreeHeap` at `0x18000d33b`
- `ntdll!RtlAllocateHeap` at `0x18000d2c5`
- `ntdll!RtlAllocateHeap` at `0x18000d2c5`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000d2aa`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000d2aa`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18000d3aa`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18000d3aa`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18000d305`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18000d305`

## pseudocode

```c

```
