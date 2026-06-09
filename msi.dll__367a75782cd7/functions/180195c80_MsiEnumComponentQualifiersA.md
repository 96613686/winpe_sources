# MsiEnumComponentQualifiersA

- ea: `0x180195c80`
- end: `0x1801963b8`
- name: `MsiEnumComponentQualifiersA`
- size: `1848`
- prototype: `UINT __stdcall(LPCSTR szComponent, DWORD iIndex, LPSTR lpQualifierBuf, LPDWORD pcchQualifierBuf, LPSTR lpApplicationDataBuf, LPDWORD pcchApplicationDataBuf)`
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180015950`
- `0x18001ba40`
- `0x18001cab0`
- `0x18001d960`
- `0x180025a18`
- `0x18004ec1c`
- `0x18004f7a4`
- `0x18004fc48`
- `0x18005403c`
- `0x180055ee4`
- `0x1800b7874`
- `0x180116644`
- `0x18018ec50`
- `0x180195c80`
- `0x18025ab1e`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!RegEnumValueA` at `0x180195f1b`
- `ADVAPI32!RegEnumValueA` at `0x180195f1b`
- `ADVAPI32!RegQueryValueExA` at `0x18019609b`
- `ADVAPI32!RegQueryValueExA` at `0x18019609b`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180195f97`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180195f97`
- `KERNEL32!InitializeCriticalSection` at `0x180195e41`
- `KERNEL32!InitializeCriticalSection` at `0x180196054`
- `KERNEL32!InitializeCriticalSection` at `0x180195e41`
- `KERNEL32!InitializeCriticalSection` at `0x180196054`
- `KERNEL32!lstrlenA` at `0x180195cf9`
- `KERNEL32!lstrlenA` at `0x18019625a`
- `KERNEL32!lstrlenA` at `0x180195cf9`
- `KERNEL32!lstrlenA` at `0x18019625a`
- `KERNEL32!GlobalFree` at `0x180196215`
- `KERNEL32!GlobalFree` at `0x180196240`
- `KERNEL32!GlobalFree` at `0x1801962d7`
- `KERNEL32!GlobalFree` at `0x1801962f7`
- `KERNEL32!GlobalFree` at `0x180196215`
- `KERNEL32!GlobalFree` at `0x180196240`
- `KERNEL32!GlobalFree` at `0x1801962d7`
- `KERNEL32!GlobalFree` at `0x1801962f7`

## string_xrefs

- `0x180195e63`: `Components`
- `0x18019606a`: `Components`
- `0x18019613f`: `Components`

## pseudocode

```c

```
