# GetFinalPathNameByHandleA

- ea: `0x180084ad0`
- end: `0x180084c67`
- name: `GetFinalPathNameByHandleA`
- size: `407`
- prototype: `DWORD __stdcall(HANDLE hFile, LPSTR lpszFilePath, DWORD cchFilePath, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callees

- `0x180083ac0`
- `0x180084ad0`
- `0x180194eb9`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlFreeAnsiString` at `0x180084bd1`
- `ntdll!RtlFreeAnsiString` at `0x180084bd1`
- `ntdll!wcslen` at `0x180084b6f`
- `ntdll!wcslen` at `0x180084b6f`
- `ntdll!RtlSetLastWin32Error` at `0x180084c59`
- `ntdll!RtlSetLastWin32Error` at `0x180084c59`
- `ntdll!RtlFreeHeap` at `0x180084bef`
- `ntdll!RtlFreeHeap` at `0x180084c21`
- `ntdll!RtlFreeHeap` at `0x180084c43`
- `ntdll!RtlFreeHeap` at `0x180084bef`
- `ntdll!RtlFreeHeap` at `0x180084c21`
- `ntdll!RtlFreeHeap` at `0x180084c43`
- `ntdll!RtlAllocateHeap` at `0x180084b2a`
- `ntdll!RtlAllocateHeap` at `0x180084b2a`

## pseudocode

```c

```
