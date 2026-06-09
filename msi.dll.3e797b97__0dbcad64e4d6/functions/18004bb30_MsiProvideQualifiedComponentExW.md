# MsiProvideQualifiedComponentExW

- ea: `0x18004bb30`
- end: `0x18004c150`
- name: `MsiProvideQualifiedComponentExW`
- size: `1568`
- prototype: `UINT __stdcall(LPCWSTR szCategory, LPCWSTR szQualifier, DWORD dwInstallMode, LPCWSTR szProduct, DWORD dwUnused1, DWORD dwUnused2, LPWSTR lpPathBuf, LPDWORD pcchPathBuf)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180171d50`
- `0x1801a0c80`

## callees

- `0x18000c4bc`
- `0x180011280`
- `0x1800399d0`
- `0x18003c030`
- `0x180044960`
- `0x1800459c0`
- `0x1800491f0`
- `0x180049774`
- `0x18004a07c`
- `0x18004bb30`
- `0x18004c158`
- `0x180265240`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18004bc44`
- `KERNEL32!InitializeCriticalSection` at `0x18004bc44`
- `KERNEL32!lstrlenW` at `0x18004bbf3`
- `KERNEL32!lstrlenW` at `0x18004bd48`
- `KERNEL32!lstrlenW` at `0x18004bf54`
- `KERNEL32!lstrlenW` at `0x18004bbf3`
- `KERNEL32!lstrlenW` at `0x18004bd48`
- `KERNEL32!lstrlenW` at `0x18004bf54`
- `KERNEL32!GlobalFree` at `0x18004bddb`
- `KERNEL32!GlobalFree` at `0x18004be55`
- `KERNEL32!GlobalFree` at `0x18004bebb`
- `KERNEL32!GlobalFree` at `0x18004bf40`
- `KERNEL32!GlobalFree` at `0x18004bf7e`
- `KERNEL32!GlobalFree` at `0x18004bfe2`
- `KERNEL32!GlobalFree` at `0x18004c0c4`
- `KERNEL32!GlobalFree` at `0x18004c0e4`
- `KERNEL32!GlobalFree` at `0x18004c0fc`
- `KERNEL32!GlobalFree` at `0x18004bddb`
- `KERNEL32!GlobalFree` at `0x18004be55`
- `KERNEL32!GlobalFree` at `0x18004bebb`
- `KERNEL32!GlobalFree` at `0x18004bf40`
- `KERNEL32!GlobalFree` at `0x18004bf7e`
- `KERNEL32!GlobalFree` at `0x18004bfe2`
- `KERNEL32!GlobalFree` at `0x18004c0c4`
- `KERNEL32!GlobalFree` at `0x18004c0e4`
- `KERNEL32!GlobalFree` at `0x18004c0fc`
- `KERNEL32!lstrcmpiW` at `0x18004be35`
- `KERNEL32!lstrcmpiW` at `0x18004be35`

## string_xrefs

- `0x18004bc5f`: `Components`
- `0x18004bfa9`: `Components`
- `0x18004c040`: `Entering MsiProvideQualifiedComponentEx. Component: %s, Qualifier: %s, Installmode: %d, Product: %s`
- `0x18004c082`: `Pathbuf: %X, pcchPathBuf: %X`
- `0x18004c112`: `MsiProvideQualifiedComponentEx is returning: %u`

## pseudocode

```c

```
