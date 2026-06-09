# GetLongPathNameA

- ea: `0x1801477a0`
- end: `0x1801479ac`
- name: `GetLongPathNameA`
- size: `524`
- prototype: `DWORD __stdcall(LPCSTR lpszShortPath, LPSTR lpszLongPath, DWORD cchBuffer)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18004b9d0`
- `0x180073120`
- `0x180082020`
- `0x1801477a0`
- `0x180194ec5`
- `0x180194f10`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlFreeAnsiString` at `0x18014796c`
- `ntdll!RtlFreeAnsiString` at `0x180199094`
- `ntdll!RtlFreeAnsiString` at `0x18014796c`
- `ntdll!RtlFreeAnsiString` at `0x180199094`
- `ntdll!RtlFreeUnicodeString` at `0x180147953`
- `ntdll!RtlFreeUnicodeString` at `0x18019907c`
- `ntdll!RtlFreeUnicodeString` at `0x180147953`
- `ntdll!RtlFreeUnicodeString` at `0x18019907c`
- `ntdll!RtlSetLastWin32Error` at `0x1801477f7`
- `ntdll!RtlSetLastWin32Error` at `0x1801478c9`
- `ntdll!RtlSetLastWin32Error` at `0x1801477f7`
- `ntdll!RtlSetLastWin32Error` at `0x1801478c9`
- `ntdll!RtlFreeHeap` at `0x180147999`
- `ntdll!RtlFreeHeap` at `0x1801990c2`
- `ntdll!RtlFreeHeap` at `0x180147999`
- `ntdll!RtlFreeHeap` at `0x1801990c2`
- `ntdll!RtlAllocateHeap` at `0x180147897`
- `ntdll!RtlAllocateHeap` at `0x180147897`

## pseudocode

```c

```
