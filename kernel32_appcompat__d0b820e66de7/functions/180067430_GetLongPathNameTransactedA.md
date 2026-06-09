# GetLongPathNameTransactedA

- ea: `0x180067430`
- end: `0x1800674bc`
- name: `GetLongPathNameTransactedA`
- size: `140`
- prototype: `DWORD __stdcall(LPCSTR lpszShortPath, LPSTR lpszLongPath, DWORD cchBuffer, HANDLE hTransaction)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180027c90`
- `0x180067430`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x180067454`
- `ntdll!RtlGetCurrentTransaction` at `0x180067454`
- `ntdll!RtlSetCurrentTransaction` at `0x18006746f`
- `ntdll!RtlSetCurrentTransaction` at `0x18006748e`
- `ntdll!RtlSetCurrentTransaction` at `0x18006746f`
- `ntdll!RtlSetCurrentTransaction` at `0x18006748e`
- `ntdll!RtlSetLastWin32Error` at `0x1800674a1`
- `ntdll!RtlSetLastWin32Error` at `0x1800674a1`

## pseudocode

```c

```
