# MsiGetFileAttributesEx(ushort const *,ulong *,unsigned __int64 *,_FILETIME *,_FILETIME *,_FILETIME *)

- ea: `0x180097608`
- end: `0x18009785a`
- name: `?MsiGetFileAttributesEx@@YAKPEBGPEAKPEA_KPEAU_FILETIME@@33@Z`
- size: `594`
- prototype: `unsigned int __usercall@<eax>(LPCWSTR lpFileName@<rcx>, unsigned int *@<rdx>, unsigned __int64 *@<r8>, struct _FILETIME *@<r9>, struct _FILETIME *, struct _FILETIME *)`
- caller_count: `27`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18006c558`
- `0x18007d29c`
- `0x180095470`
- `0x180095874`
- `0x1800958e0`
- `0x180096164`
- `0x180097290`
- `0x1800973c8`
- `0x180097540`
- `0x180097860`
- `0x18009d8e0`
- `0x1800b3dc8`
- `0x1800b4aac`
- `0x1800fa370`
- `0x18010d5a0`
- `0x180112250`
- `0x180140058`
- `0x180152484`
- `0x180153524`
- `0x1801701d8`
- `0x1801961b8`
- `0x180196a0c`
- `0x180197ac4`
- `0x18019a4c0`
- `0x1801b0708`
- `0x180202b40`
- `0x180230e30`

## callees

- `0x180097608`
- `0x18019a128`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800977af`
- `msvcrt!_wcsnicmp` at `0x1800977af`
- `KERNEL32!GetLastError` at `0x1800976cf`
- `KERNEL32!GetLastError` at `0x18009780f`
- `KERNEL32!GetLastError` at `0x1800976cf`
- `KERNEL32!GetLastError` at `0x18009780f`
- `KERNEL32!SetLastError` at `0x180097849`
- `KERNEL32!SetLastError` at `0x180097849`
- `KERNEL32!lstrlenW` at `0x18009773d`
- `KERNEL32!lstrlenW` at `0x180097786`
- `KERNEL32!lstrlenW` at `0x18009773d`
- `KERNEL32!lstrlenW` at `0x180097786`
- `KERNEL32!GetFileAttributesW` at `0x1800977fc`
- `KERNEL32!GetFileAttributesW` at `0x1800977fc`
- `KERNEL32!GetSystemDirectoryW` at `0x180097724`
- `KERNEL32!GetSystemDirectoryW` at `0x180097724`

## pseudocode

```c

```
