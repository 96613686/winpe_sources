# GetFullPathNameA

- ea: `0x1800e6ff0`
- end: `0x1800e727e`
- name: `GetFullPathNameA`
- size: `654`
- prototype: `DWORD __stdcall(LPCSTR lpFileName, DWORD nBufferLength, LPSTR lpBuffer, LPSTR *lpFilePart)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18013e9a0`

## callees

- `0x1800134a0`
- `0x1800e6ff0`
- `0x180188eb9`
- `0x180197010`

## import_xrefs

- `ntdll!RtlFreeAnsiString` at `0x1800e7185`
- `ntdll!RtlFreeAnsiString` at `0x1800e7185`
- `ntdll!RtlFreeUnicodeString` at `0x1800e710a`
- `ntdll!RtlFreeUnicodeString` at `0x1800e71b1`
- `ntdll!RtlFreeUnicodeString` at `0x1800e720c`
- `ntdll!RtlFreeUnicodeString` at `0x1800e710a`
- `ntdll!RtlFreeUnicodeString` at `0x1800e71b1`
- `ntdll!RtlFreeUnicodeString` at `0x1800e720c`
- `ntdll!RtlInitUnicodeString` at `0x1800e7149`
- `ntdll!RtlInitUnicodeString` at `0x1800e7149`
- `ntdll!RtlSetLastWin32Error` at `0x1800e7231`
- `ntdll!RtlSetLastWin32Error` at `0x1800e7273`
- `ntdll!RtlSetLastWin32Error` at `0x1800e7231`
- `ntdll!RtlSetLastWin32Error` at `0x1800e7273`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800e70e0`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800e71d8`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800e70e0`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800e71d8`
- `ntdll!RtlInitAnsiStringEx` at `0x1800e703d`
- `ntdll!RtlInitAnsiStringEx` at `0x1800e703d`
- `ntdll!RtlFreeHeap` at `0x1800e7122`
- `ntdll!RtlFreeHeap` at `0x1800e7224`
- `ntdll!RtlFreeHeap` at `0x1800e7122`
- `ntdll!RtlFreeHeap` at `0x1800e7224`
- `ntdll!RtlGetFullPathName_UEx` at `0x1800e70ba`
- `ntdll!RtlGetFullPathName_UEx` at `0x1800e70ba`
- `ntdll!RtlAllocateHeap` at `0x1800e7083`
- `ntdll!RtlAllocateHeap` at `0x1800e7083`

## pseudocode

```c

```
