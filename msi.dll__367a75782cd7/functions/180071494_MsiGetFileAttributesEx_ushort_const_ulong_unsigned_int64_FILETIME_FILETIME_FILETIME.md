# MsiGetFileAttributesEx(ushort const *,ulong *,unsigned __int64 *,_FILETIME *,_FILETIME *,_FILETIME *)

- ea: `0x180071494`
- end: `0x1800716b1`
- name: `?MsiGetFileAttributesEx@@YAKPEBGPEAKPEA_KPEAU_FILETIME@@33@Z`
- size: `541`
- prototype: `unsigned int __usercall@<eax>(LPCWSTR lpFileName@<rcx>, unsigned int *@<rdx>, unsigned __int64 *@<r8>, struct _FILETIME *@<r9>, struct _FILETIME *, struct _FILETIME *)`
- caller_count: `27`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x1800523b8`
- `0x180053700`
- `0x18006f490`
- `0x18006f870`
- `0x18006f8d0`
- `0x1800700e0`
- `0x180071130`
- `0x18007125c`
- `0x1800713d0`
- `0x1800716c0`
- `0x180071ab0`
- `0x180071b4c`
- `0x180072660`
- `0x18007f080`
- `0x180081b34`
- `0x1801023c0`
- `0x18013ae34`
- `0x18014ba64`
- `0x18014ddf8`
- `0x18016a110`
- `0x18018f898`
- `0x1801900c8`
- `0x180191114`
- `0x180193914`
- `0x1801a9574`
- `0x1801f99d0`
- `0x180227060`

## callees

- `0x180071494`
- `0x18019358c`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18007161e`
- `msvcrt!_wcsnicmp` at `0x18007161e`
- `KERNEL32!GetLastError` at `0x18007155a`
- `KERNEL32!GetLastError` at `0x180071672`
- `KERNEL32!GetLastError` at `0x18007155a`
- `KERNEL32!GetLastError` at `0x180071672`
- `KERNEL32!SetLastError` at `0x1800716a6`
- `KERNEL32!SetLastError` at `0x1800716a6`
- `KERNEL32!lstrlenW` at `0x1800715b8`
- `KERNEL32!lstrlenW` at `0x1800715fb`
- `KERNEL32!lstrlenW` at `0x1800715b8`
- `KERNEL32!lstrlenW` at `0x1800715fb`
- `KERNEL32!GetFileAttributesW` at `0x180071665`
- `KERNEL32!GetFileAttributesW` at `0x180071665`
- `KERNEL32!GetSystemDirectoryW` at `0x1800715a5`
- `KERNEL32!GetSystemDirectoryW` at `0x1800715a5`

## pseudocode

```c

```
