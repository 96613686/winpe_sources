# MsiGetSystemDirectory(ushort *,uint,int)

- ea: `0x18006e6a8`
- end: `0x18006e759`
- name: `?MsiGetSystemDirectory@@YAIPEAGIH@Z`
- size: `177`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned int, int)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18006cc60`
- `0x18006e53c`
- `0x1801435cc`
- `0x180154314`

## callees

- `0x18006e484`
- `0x18006e6a8`
- `0x18025c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18006e706`
- `KERNEL32!GetLastError` at `0x18006e72e`
- `KERNEL32!GetLastError` at `0x18006e706`
- `KERNEL32!GetLastError` at `0x18006e72e`
- `KERNEL32!GetProcAddress` at `0x18006e6fb`
- `KERNEL32!GetProcAddress` at `0x18006e6fb`
- `KERNEL32!SetLastError` at `0x18006e741`
- `KERNEL32!SetLastError` at `0x18006e741`
- `KERNEL32!FreeLibrary` at `0x18006e739`
- `KERNEL32!FreeLibrary` at `0x18006e739`
- `KERNEL32!GetSystemDirectoryW` at `0x18006e6e9`
- `KERNEL32!GetSystemDirectoryW` at `0x18006e6e9`

## string_xrefs

- `0x18006e6f1`: `GetSystemWow64DirectoryW`
- `0x18006e6ce`: `kernel32.dll`

## pseudocode

```c

```
