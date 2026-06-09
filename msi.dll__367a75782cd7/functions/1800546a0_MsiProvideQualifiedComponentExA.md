# MsiProvideQualifiedComponentExA

- ea: `0x1800546a0`
- end: `0x180054bd0`
- name: `MsiProvideQualifiedComponentExA`
- size: `1328`
- prototype: `UINT __stdcall(LPCSTR szCategory, LPCSTR szQualifier, DWORD dwInstallMode, LPCSTR szProduct, DWORD dwUnused1, DWORD dwUnused2, LPSTR lpPathBuf, LPDWORD pcchPathBuf)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180054660`

## callees

- `0x18000a150`
- `0x180015950`
- `0x18001ba40`
- `0x18001cab0`
- `0x18001d960`
- `0x180025a18`
- `0x180051f88`
- `0x18005403c`
- `0x1800546a0`
- `0x18015298c`
- `0x18018ec50`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180054801`
- `KERNEL32!InitializeCriticalSection` at `0x180054801`
- `KERNEL32!lstrlenA` at `0x1800547aa`
- `KERNEL32!lstrlenA` at `0x1800548fb`
- `KERNEL32!lstrlenA` at `0x1800547aa`
- `KERNEL32!lstrlenA` at `0x1800548fb`
- `KERNEL32!GlobalFree` at `0x180054914`
- `KERNEL32!GlobalFree` at `0x180054929`
- `KERNEL32!GlobalFree` at `0x180054956`
- `KERNEL32!GlobalFree` at `0x180054a58`
- `KERNEL32!GlobalFree` at `0x180054a83`
- `KERNEL32!GlobalFree` at `0x180054a93`
- `KERNEL32!GlobalFree` at `0x180054ab2`
- `KERNEL32!GlobalFree` at `0x180054af0`
- `KERNEL32!GlobalFree` at `0x180054b21`
- `KERNEL32!GlobalFree` at `0x180054914`
- `KERNEL32!GlobalFree` at `0x180054929`
- `KERNEL32!GlobalFree` at `0x180054956`
- `KERNEL32!GlobalFree` at `0x180054a58`
- `KERNEL32!GlobalFree` at `0x180054a83`
- `KERNEL32!GlobalFree` at `0x180054a93`
- `KERNEL32!GlobalFree` at `0x180054ab2`
- `KERNEL32!GlobalFree` at `0x180054af0`
- `KERNEL32!GlobalFree` at `0x180054b21`
- `KERNEL32!lstrcmpiA` at `0x1800548ee`
- `KERNEL32!lstrcmpiA` at `0x1800548ee`

## string_xrefs

- `0x180054815`: `Components`
- `0x18005498d`: `Components`
- `0x18005472a`: `Entering MsiProvideQualifiedComponentEx. Component: %s, Qualifier: %s, Installmode: %d, Product: %s`
- `0x180054767`: `Pathbuf: %X, pcchPathBuf: %X`
- `0x180054b72`: `MsiProvideQualifiedComponentEx is returning: %u`

## pseudocode

```c

```
