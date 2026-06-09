# GetShortPathNameA

- ea: `0x180028610`
- end: `0x18002884d`
- name: `GetShortPathNameA`
- size: `573`
- prototype: `DWORD __stdcall(LPCSTR lpszLongPath, LPSTR lpszShortPath, DWORD cchBuffer)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000ccf0`
- `0x180028610`
- `0x180028f60`
- `0x180028fe0`
- `0x180061d70`
- `0x1800827c0`
- `0x180084010`

## import_xrefs

- `ntdll!RtlFreeAnsiString` at `0x1800287be`
- `ntdll!RtlFreeAnsiString` at `0x180082c80`
- `ntdll!RtlFreeAnsiString` at `0x1800287be`
- `ntdll!RtlFreeAnsiString` at `0x180082c80`
- `ntdll!RtlFreeUnicodeString` at `0x18002880a`
- `ntdll!RtlFreeUnicodeString` at `0x180082c68`
- `ntdll!RtlFreeUnicodeString` at `0x18002880a`
- `ntdll!RtlFreeUnicodeString` at `0x180082c68`
- `ntdll!RtlSetLastWin32Error` at `0x180028794`
- `ntdll!RtlSetLastWin32Error` at `0x18002881d`
- `ntdll!RtlSetLastWin32Error` at `0x180028794`
- `ntdll!RtlSetLastWin32Error` at `0x18002881d`
- `ntdll!RtlFreeHeap` at `0x18002883f`
- `ntdll!RtlFreeHeap` at `0x180082cae`
- `ntdll!RtlFreeHeap` at `0x18002883f`
- `ntdll!RtlFreeHeap` at `0x180082cae`
- `ntdll!RtlAllocateHeap` at `0x180028750`
- `ntdll!RtlAllocateHeap` at `0x180028750`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180028729`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180028729`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x1800286ce`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x1800286ce`

## pseudocode

```c

```
