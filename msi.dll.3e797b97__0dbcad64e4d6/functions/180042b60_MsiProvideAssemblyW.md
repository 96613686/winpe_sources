# MsiProvideAssemblyW

- ea: `0x180042b60`
- end: `0x1800433b5`
- name: `MsiProvideAssemblyW`
- size: `2133`
- prototype: `UINT __stdcall(LPCWSTR szAssemblyName, LPCWSTR szAppContext, DWORD dwInstallMode, DWORD dwAssemblyInfo, LPWSTR lpPathBuf, LPDWORD pcchPathBuf)`
- caller_count: `3`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x180112b0c`
- `0x1801725a0`
- `0x1801b4fd0`

## callees

- `0x180005af8`
- `0x18000c4bc`
- `0x180042b60`
- `0x1800433c0`
- `0x1800434d0`
- `0x180044960`
- `0x1800459c0`
- `0x180049774`
- `0x18006dc80`
- `0x18009fdf0`
- `0x1802651d2`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x1800431eb`
- `KERNEL32!GlobalAlloc` at `0x1800431eb`
- `KERNEL32!lstrlenW` at `0x180042e96`
- `KERNEL32!lstrlenW` at `0x180043323`
- `KERNEL32!lstrlenW` at `0x180042e96`
- `KERNEL32!lstrlenW` at `0x180043323`
- `KERNEL32!GlobalFree` at `0x180042efe`
- `KERNEL32!GlobalFree` at `0x180042f2d`
- `KERNEL32!GlobalFree` at `0x180042f5c`
- `KERNEL32!GlobalFree` at `0x180042fed`
- `KERNEL32!GlobalFree` at `0x180043032`
- `KERNEL32!GlobalFree` at `0x180043061`
- `KERNEL32!GlobalFree` at `0x180043090`
- `KERNEL32!GlobalFree` at `0x18004312a`
- `KERNEL32!GlobalFree` at `0x1800431b6`
- `KERNEL32!GlobalFree` at `0x180043218`
- `KERNEL32!GlobalFree` at `0x180042efe`
- `KERNEL32!GlobalFree` at `0x180042f2d`
- `KERNEL32!GlobalFree` at `0x180042f5c`
- `KERNEL32!GlobalFree` at `0x180042fed`
- `KERNEL32!GlobalFree` at `0x180043032`
- `KERNEL32!GlobalFree` at `0x180043061`
- `KERNEL32!GlobalFree` at `0x180043090`
- `KERNEL32!GlobalFree` at `0x18004312a`
- `KERNEL32!GlobalFree` at `0x1800431b6`
- `KERNEL32!GlobalFree` at `0x180043218`

## string_xrefs

- `0x1800432bd`: `Pathbuf: %X, pcchPathBuf: %X`
- `0x18004327a`: `Entering MsiProvideAssembly. AssemblyName: %s, AppContext: %s, InstallMode: %d`
- `0x180042fb0`: `MsiProvideAssembly is returning: %u`

## pseudocode

```c

```
