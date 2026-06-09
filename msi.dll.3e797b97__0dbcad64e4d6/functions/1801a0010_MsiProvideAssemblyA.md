# MsiProvideAssemblyA

- ea: `0x1801a0010`
- end: `0x1801a06a7`
- name: `MsiProvideAssemblyA`
- size: `1687`
- prototype: `UINT __stdcall(LPCSTR szAssemblyName, LPCSTR szAppContext, DWORD dwInstallMode, DWORD dwAssemblyInfo, LPSTR lpPathBuf, LPDWORD pcchPathBuf)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x180027634`
- `0x1800433c0`
- `0x180044960`
- `0x1800459c0`
- `0x1800b1958`
- `0x18011cdf0`
- `0x18015850c`
- `0x1801973b0`
- `0x1801a0010`
- `0x1802651d2`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x1801a0206`
- `KERNEL32!lstrlenA` at `0x1801a054f`
- `KERNEL32!lstrlenA` at `0x1801a0206`
- `KERNEL32!lstrlenA` at `0x1801a054f`
- `KERNEL32!GlobalFree` at `0x1801a01d4`
- `KERNEL32!GlobalFree` at `0x1801a03ec`
- `KERNEL32!GlobalFree` at `0x1801a045d`
- `KERNEL32!GlobalFree` at `0x1801a048c`
- `KERNEL32!GlobalFree` at `0x1801a04b5`
- `KERNEL32!GlobalFree` at `0x1801a05b4`
- `KERNEL32!GlobalFree` at `0x1801a05e3`
- `KERNEL32!GlobalFree` at `0x1801a060c`
- `KERNEL32!GlobalFree` at `0x1801a01d4`
- `KERNEL32!GlobalFree` at `0x1801a03ec`
- `KERNEL32!GlobalFree` at `0x1801a045d`
- `KERNEL32!GlobalFree` at `0x1801a048c`
- `KERNEL32!GlobalFree` at `0x1801a04b5`
- `KERNEL32!GlobalFree` at `0x1801a05b4`
- `KERNEL32!GlobalFree` at `0x1801a05e3`
- `KERNEL32!GlobalFree` at `0x1801a060c`
- `USER32!CharNextA` at `0x1801a024b`
- `USER32!CharNextA` at `0x1801a024b`

## string_xrefs

- `0x1801a00df`: `Pathbuf: %X, pcchPathBuf: %X`
- `0x1801a00a5`: `Entering MsiProvideAssembly. AssemblyName: %s, AppContext: %s, InstallMode: %d`
- `0x1801a064b`: `MsiProvideAssembly is returning: %u`

## pseudocode

```c

```
