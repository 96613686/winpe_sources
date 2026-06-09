# GetLongPathNameA

- ea: `0x180027c90`
- end: `0x180027ec9`
- name: `GetLongPathNameA`
- size: `569`
- prototype: `DWORD __stdcall(LPCSTR lpszShortPath, LPSTR lpszLongPath, DWORD cchBuffer)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180067430`

## callees

- `0x18000ccf0`
- `0x180027c90`
- `0x180027ed0`
- `0x180028f60`
- `0x180061d70`
- `0x1800827c0`
- `0x180084010`

## import_xrefs

- `ntdll!RtlFreeAnsiString` at `0x180027e8e`
- `ntdll!RtlFreeAnsiString` at `0x180082bac`
- `ntdll!RtlFreeAnsiString` at `0x180027e8e`
- `ntdll!RtlFreeAnsiString` at `0x180082bac`
- `ntdll!RtlFreeUnicodeString` at `0x180027e7b`
- `ntdll!RtlFreeUnicodeString` at `0x180082b94`
- `ntdll!RtlFreeUnicodeString` at `0x180027e7b`
- `ntdll!RtlFreeUnicodeString` at `0x180082b94`
- `ntdll!RtlSetLastWin32Error` at `0x180027dde`
- `ntdll!RtlSetLastWin32Error` at `0x180027e66`
- `ntdll!RtlSetLastWin32Error` at `0x180027dde`
- `ntdll!RtlSetLastWin32Error` at `0x180027e66`
- `ntdll!RtlFreeHeap` at `0x180027eb8`
- `ntdll!RtlFreeHeap` at `0x180082bda`
- `ntdll!RtlFreeHeap` at `0x180027eb8`
- `ntdll!RtlFreeHeap` at `0x180082bda`
- `ntdll!RtlAllocateHeap` at `0x180027da9`
- `ntdll!RtlAllocateHeap` at `0x180027da9`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180027d82`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180027d82`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x180027d4e`
- `KERNELBASE!GetUnicodeStringToEightBitStringRoutine` at `0x180027d4e`

## pseudocode

```c

```
