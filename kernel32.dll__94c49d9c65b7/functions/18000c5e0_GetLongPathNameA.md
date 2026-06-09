# GetLongPathNameA

- ea: `0x18000c5e0`
- end: `0x18000c7e5`
- name: `GetLongPathNameA`
- size: `517`
- prototype: `DWORD __stdcall(LPCSTR lpszShortPath, LPSTR lpszLongPath, DWORD cchBuffer)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180060bb0`

## callees

- `0x18000c5e0`
- `0x18000c7f0`
- `0x18000d6c0`
- `0x18000f920`
- `0x18005c390`
- `0x18007a840`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlFreeAnsiString` at `0x18000c7b9`
- `ntdll!RtlFreeAnsiString` at `0x18007ab72`
- `ntdll!RtlFreeAnsiString` at `0x18000c7b9`
- `ntdll!RtlFreeAnsiString` at `0x18007ab72`
- `ntdll!RtlFreeUnicodeString` at `0x18000c7ac`
- `ntdll!RtlFreeUnicodeString` at `0x18007ab60`
- `ntdll!RtlFreeUnicodeString` at `0x18000c7ac`
- `ntdll!RtlFreeUnicodeString` at `0x18007ab60`
- `ntdll!RtlSetLastWin32Error` at `0x18000c71c`
- `ntdll!RtlSetLastWin32Error` at `0x18000c79d`
- `ntdll!RtlSetLastWin32Error` at `0x18000c71c`
- `ntdll!RtlSetLastWin32Error` at `0x18000c79d`
- `ntdll!RtlFreeHeap` at `0x18000c7dd`
- `ntdll!RtlFreeHeap` at `0x18007ab9a`
- `ntdll!RtlFreeHeap` at `0x18000c7dd`
- `ntdll!RtlFreeHeap` at `0x18007ab9a`
- `ntdll!RtlAllocateHeap` at `0x18000c6ed`
- `ntdll!RtlAllocateHeap` at `0x18000c6ed`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000c6cc`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000c6cc`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18000c69e`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x18000c69e`

## pseudocode

```c

```
