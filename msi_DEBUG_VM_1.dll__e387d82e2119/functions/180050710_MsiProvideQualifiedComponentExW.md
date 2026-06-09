# MsiProvideQualifiedComponentExW

- ea: `0x180050710`
- end: `0x180050cdb`
- name: `MsiProvideQualifiedComponentExW`
- size: `1483`
- prototype: `UINT __stdcall(LPCWSTR szCategory, LPCWSTR szQualifier, DWORD dwInstallMode, LPCWSTR szProduct, DWORD dwUnused1, DWORD dwUnused2, LPWSTR lpPathBuf, LPDWORD pcchPathBuf)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18016bcd0`
- `0x180199dd0`

## callees

- `0x180015950`
- `0x18001cab0`
- `0x18001d960`
- `0x1800227d0`
- `0x180025a18`
- `0x18004b560`
- `0x18004c654`
- `0x18004cf08`
- `0x18004fa38`
- `0x180050710`
- `0x180050cf0`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18005081d`
- `KERNEL32!InitializeCriticalSection` at `0x18005081d`
- `KERNEL32!lstrlenW` at `0x1800507d2`
- `KERNEL32!lstrlenW` at `0x18005091b`
- `KERNEL32!lstrlenW` at `0x180050b03`
- `KERNEL32!lstrlenW` at `0x1800507d2`
- `KERNEL32!lstrlenW` at `0x18005091b`
- `KERNEL32!lstrlenW` at `0x180050b03`
- `KERNEL32!GlobalFree` at `0x1800509a8`
- `KERNEL32!GlobalFree` at `0x180050a16`
- `KERNEL32!GlobalFree` at `0x180050a76`
- `KERNEL32!GlobalFree` at `0x180050af5`
- `KERNEL32!GlobalFree` at `0x180050b27`
- `KERNEL32!GlobalFree` at `0x180050b85`
- `KERNEL32!GlobalFree` at `0x180050c61`
- `KERNEL32!GlobalFree` at `0x180050c7b`
- `KERNEL32!GlobalFree` at `0x180050c8d`
- `KERNEL32!GlobalFree` at `0x1800509a8`
- `KERNEL32!GlobalFree` at `0x180050a16`
- `KERNEL32!GlobalFree` at `0x180050a76`
- `KERNEL32!GlobalFree` at `0x180050af5`
- `KERNEL32!GlobalFree` at `0x180050b27`
- `KERNEL32!GlobalFree` at `0x180050b85`
- `KERNEL32!GlobalFree` at `0x180050c61`
- `KERNEL32!GlobalFree` at `0x180050c7b`
- `KERNEL32!GlobalFree` at `0x180050c8d`
- `KERNEL32!lstrcmpiW` at `0x1800509fc`
- `KERNEL32!lstrcmpiW` at `0x1800509fc`

## string_xrefs

- `0x180050832`: `Components`
- `0x180050b4c`: `Components`
- `0x180050bdd`: `Entering MsiProvideQualifiedComponentEx. Component: %s, Qualifier: %s, Installmode: %d, Product: %s`
- `0x180050c1f`: `Pathbuf: %X, pcchPathBuf: %X`
- `0x180050c9d`: `MsiProvideQualifiedComponentEx is returning: %u`

## pseudocode

```c

```
