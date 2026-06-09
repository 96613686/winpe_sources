# MsiEnumComponentQualifiersA

- ea: `0x18019c920`
- end: `0x18019d09b`
- name: `MsiEnumComponentQualifiersA`
- size: `1915`
- prototype: `UINT __stdcall(LPCSTR szComponent, DWORD iIndex, LPSTR lpQualifierBuf, LPDWORD pcchQualifierBuf, LPSTR lpApplicationDataBuf, LPDWORD pcchApplicationDataBuf)`
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000c4bc`
- `0x18003c030`
- `0x180041c54`
- `0x1800433c0`
- `0x180044960`
- `0x1800459c0`
- `0x180046538`
- `0x180046f50`
- `0x180048588`
- `0x1800b71c8`
- `0x1800c00c8`
- `0x18011cdf0`
- `0x1801954e0`
- `0x18019c920`
- `0x1802651de`
- `0x180265240`

## import_xrefs

- `ADVAPI32!RegEnumValueA` at `0x18019cbc7`
- `ADVAPI32!RegEnumValueA` at `0x18019cbc7`
- `ADVAPI32!RegQueryValueExA` at `0x18019cd59`
- `ADVAPI32!RegQueryValueExA` at `0x18019cd59`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18019cc49`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18019cc49`
- `KERNEL32!InitializeCriticalSection` at `0x18019cae7`
- `KERNEL32!InitializeCriticalSection` at `0x18019cd0c`
- `KERNEL32!InitializeCriticalSection` at `0x18019cae7`
- `KERNEL32!InitializeCriticalSection` at `0x18019cd0c`
- `KERNEL32!lstrlenA` at `0x18019c999`
- `KERNEL32!lstrlenA` at `0x18019cf2a`
- `KERNEL32!lstrlenA` at `0x18019c999`
- `KERNEL32!lstrlenA` at `0x18019cf2a`
- `KERNEL32!GlobalFree` at `0x18019ced9`
- `KERNEL32!GlobalFree` at `0x18019cf0a`
- `KERNEL32!GlobalFree` at `0x18019cfad`
- `KERNEL32!GlobalFree` at `0x18019cfd3`
- `KERNEL32!GlobalFree` at `0x18019ced9`
- `KERNEL32!GlobalFree` at `0x18019cf0a`
- `KERNEL32!GlobalFree` at `0x18019cfad`
- `KERNEL32!GlobalFree` at `0x18019cfd3`

## string_xrefs

- `0x18019cb0f`: `Components`
- `0x18019cd28`: `Components`
- `0x18019ce03`: `Components`

## pseudocode

```c

```
