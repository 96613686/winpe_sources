# MsiGetSystemDirectory(ushort *,uint,int)

- ea: `0x1800945b0`
- end: `0x180094689`
- name: `?MsiGetSystemDirectory@@YAIPEAGIH@Z`
- size: `217`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned int, int)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180092930`
- `0x18009443c`
- `0x180148ae8`
- `0x180159ccc`

## callees

- `0x18009436c`
- `0x1800945b0`
- `0x180266010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18009461d`
- `KERNEL32!GetLastError` at `0x18009464b`
- `KERNEL32!GetLastError` at `0x18009461d`
- `KERNEL32!GetLastError` at `0x18009464b`
- `KERNEL32!GetProcAddress` at `0x18009460c`
- `KERNEL32!GetProcAddress` at `0x18009460c`
- `KERNEL32!SetLastError` at `0x18009466a`
- `KERNEL32!SetLastError` at `0x18009466a`
- `KERNEL32!FreeLibrary` at `0x18009465c`
- `KERNEL32!FreeLibrary` at `0x18009465c`
- `KERNEL32!GetSystemDirectoryW` at `0x1800945f4`
- `KERNEL32!GetSystemDirectoryW` at `0x1800945f4`

## string_xrefs

- `0x180094602`: `GetSystemWow64DirectoryW`
- `0x1800945d6`: `kernel32.dll`

## pseudocode

```c

```
