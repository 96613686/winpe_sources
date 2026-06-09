# GetFullPathNameA

- ea: `0x1800ef2f0`
- end: `0x1800ef5d3`
- name: `GetFullPathNameA`
- size: `739`
- prototype: `DWORD __stdcall(LPCSTR lpFileName, DWORD nBufferLength, LPSTR lpBuffer, LPSTR *lpFilePart)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180148ad0`

## callees

- `0x18004b9d0`
- `0x1800ef2f0`
- `0x180194eb9`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlFreeAnsiString` at `0x1800ef4b0`
- `ntdll!RtlFreeAnsiString` at `0x1800ef4b0`
- `ntdll!RtlFreeUnicodeString` at `0x1800ef422`
- `ntdll!RtlFreeUnicodeString` at `0x1800ef4e2`
- `ntdll!RtlFreeUnicodeString` at `0x1800ef549`
- `ntdll!RtlFreeUnicodeString` at `0x1800ef422`
- `ntdll!RtlFreeUnicodeString` at `0x1800ef4e2`
- `ntdll!RtlFreeUnicodeString` at `0x1800ef549`
- `ntdll!RtlInitUnicodeString` at `0x1800ef46e`
- `ntdll!RtlInitUnicodeString` at `0x1800ef46e`
- `ntdll!RtlSetLastWin32Error` at `0x1800ef57a`
- `ntdll!RtlSetLastWin32Error` at `0x1800ef5c2`
- `ntdll!RtlSetLastWin32Error` at `0x1800ef57a`
- `ntdll!RtlSetLastWin32Error` at `0x1800ef5c2`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800ef3f2`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800ef50f`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800ef3f2`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800ef50f`
- `ntdll!RtlInitAnsiStringEx` at `0x1800ef33d`
- `ntdll!RtlInitAnsiStringEx` at `0x1800ef33d`
- `ntdll!RtlFreeHeap` at `0x1800ef440`
- `ntdll!RtlFreeHeap` at `0x1800ef567`
- `ntdll!RtlFreeHeap` at `0x1800ef440`
- `ntdll!RtlFreeHeap` at `0x1800ef567`
- `ntdll!RtlGetFullPathName_UEx` at `0x1800ef3c6`
- `ntdll!RtlGetFullPathName_UEx` at `0x1800ef3c6`
- `ntdll!RtlAllocateHeap` at `0x1800ef389`
- `ntdll!RtlAllocateHeap` at `0x1800ef389`

## pseudocode

```c

```
