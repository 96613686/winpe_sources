# MsiProvideAssemblyA

- ea: `0x1801991c0`
- end: `0x180199814`
- name: `MsiProvideAssemblyA`
- size: `1620`
- prototype: `UINT __stdcall(LPCSTR szAssemblyName, LPCSTR szAppContext, DWORD dwInstallMode, DWORD dwAssemblyInfo, LPSTR lpPathBuf, LPDWORD pcchPathBuf)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update`

## callees

- `0x18000a150`
- `0x18001ba40`
- `0x18001cab0`
- `0x18001d960`
- `0x180035a8c`
- `0x180066074`
- `0x1800ae2ec`
- `0x180116644`
- `0x18015298c`
- `0x180190a48`
- `0x1801991c0`
- `0x18025ab12`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x1801993b0`
- `KERNEL32!lstrlenA` at `0x1801996d5`
- `KERNEL32!lstrlenA` at `0x1801993b0`
- `KERNEL32!lstrlenA` at `0x1801996d5`
- `KERNEL32!GlobalFree` at `0x180199384`
- `KERNEL32!GlobalFree` at `0x18019958a`
- `KERNEL32!GlobalFree` at `0x1801995f5`
- `KERNEL32!GlobalFree` at `0x18019961e`
- `KERNEL32!GlobalFree` at `0x180199641`
- `KERNEL32!GlobalFree` at `0x180199734`
- `KERNEL32!GlobalFree` at `0x18019975d`
- `KERNEL32!GlobalFree` at `0x180199780`
- `KERNEL32!GlobalFree` at `0x180199384`
- `KERNEL32!GlobalFree` at `0x18019958a`
- `KERNEL32!GlobalFree` at `0x1801995f5`
- `KERNEL32!GlobalFree` at `0x18019961e`
- `KERNEL32!GlobalFree` at `0x180199641`
- `KERNEL32!GlobalFree` at `0x180199734`
- `KERNEL32!GlobalFree` at `0x18019975d`
- `KERNEL32!GlobalFree` at `0x180199780`
- `USER32!CharNextA` at `0x1801993ef`
- `USER32!CharNextA` at `0x1801993ef`

## string_xrefs

- `0x18019928f`: `Pathbuf: %X, pcchPathBuf: %X`
- `0x180199255`: `Entering MsiProvideAssembly. AssemblyName: %s, AppContext: %s, InstallMode: %d`
- `0x1801997b9`: `MsiProvideAssembly is returning: %u`

## pseudocode

```c

```
