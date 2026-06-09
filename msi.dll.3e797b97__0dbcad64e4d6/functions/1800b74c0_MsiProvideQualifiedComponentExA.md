# MsiProvideQualifiedComponentExA

- ea: `0x1800b74c0`
- end: `0x1800b7a43`
- name: `MsiProvideQualifiedComponentExA`
- size: `1411`
- prototype: `UINT __stdcall(LPCSTR szCategory, LPCSTR szQualifier, DWORD dwInstallMode, LPCSTR szProduct, DWORD dwUnused1, DWORD dwUnused2, LPSTR lpPathBuf, LPDWORD pcchPathBuf)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800b7480`

## callees

- `0x18000c4bc`
- `0x180027634`
- `0x18003c030`
- `0x1800433c0`
- `0x180044960`
- `0x1800459c0`
- `0x1800b5ff8`
- `0x1800b71c8`
- `0x1800b74c0`
- `0x18015850c`
- `0x1801954e0`
- `0x180265240`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800b7627`
- `KERNEL32!InitializeCriticalSection` at `0x1800b7627`
- `KERNEL32!lstrlenA` at `0x1800b75ca`
- `KERNEL32!lstrlenA` at `0x1800b772d`
- `KERNEL32!lstrlenA` at `0x1800b75ca`
- `KERNEL32!lstrlenA` at `0x1800b772d`
- `KERNEL32!GlobalFree` at `0x1800b7750`
- `KERNEL32!GlobalFree` at `0x1800b776b`
- `KERNEL32!GlobalFree` at `0x1800b779e`
- `KERNEL32!GlobalFree` at `0x1800b78a6`
- `KERNEL32!GlobalFree` at `0x1800b78d7`
- `KERNEL32!GlobalFree` at `0x1800b78ed`
- `KERNEL32!GlobalFree` at `0x1800b7912`
- `KERNEL32!GlobalFree` at `0x1800b7956`
- `KERNEL32!GlobalFree` at `0x1800b798d`
- `KERNEL32!GlobalFree` at `0x1800b7750`
- `KERNEL32!GlobalFree` at `0x1800b776b`
- `KERNEL32!GlobalFree` at `0x1800b779e`
- `KERNEL32!GlobalFree` at `0x1800b78a6`
- `KERNEL32!GlobalFree` at `0x1800b78d7`
- `KERNEL32!GlobalFree` at `0x1800b78ed`
- `KERNEL32!GlobalFree` at `0x1800b7912`
- `KERNEL32!GlobalFree` at `0x1800b7956`
- `KERNEL32!GlobalFree` at `0x1800b798d`
- `KERNEL32!lstrcmpiA` at `0x1800b771a`
- `KERNEL32!lstrcmpiA` at `0x1800b771a`

## string_xrefs

- `0x1800b7641`: `Components`
- `0x1800b77db`: `Components`
- `0x1800b754a`: `Entering MsiProvideQualifiedComponentEx. Component: %s, Qualifier: %s, Installmode: %d, Product: %s`
- `0x1800b7587`: `Pathbuf: %X, pcchPathBuf: %X`
- `0x1800b79e4`: `MsiProvideQualifiedComponentEx is returning: %u`

## pseudocode

```c

```
