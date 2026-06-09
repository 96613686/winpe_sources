# CMsiPath::IsFileModified(ushort const *,Bool &)

- ea: `0x180072660`
- end: `0x1800729f5`
- name: `?IsFileModified@CMsiPath@@UEAAPEAVIMsiRecord@@PEBGAEAW4Bool@@@Z`
- size: `917`
- prototype: `struct IMsiRecord *__fastcall(CMsiPath *__hidden this, const unsigned __int16 *, enum Bool *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callees

- `0x180025a18`
- `0x180027b54`
- `0x18003a9c0`
- `0x180071494`
- `0x180072660`
- `0x180083178`
- `0x1800833ec`
- `0x18014148c`
- `0x18014e4d4`
- `0x18025c010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800728c0`
- `KERNEL32!CloseHandle` at `0x18007293b`
- `KERNEL32!CloseHandle` at `0x180072972`
- `KERNEL32!CloseHandle` at `0x1800728c0`
- `KERNEL32!CloseHandle` at `0x18007293b`
- `KERNEL32!CloseHandle` at `0x180072972`
- `KERNEL32!GetLastError` at `0x180072770`
- `KERNEL32!GetLastError` at `0x1800728d1`
- `KERNEL32!GetLastError` at `0x180072926`
- `KERNEL32!GetLastError` at `0x180072770`
- `KERNEL32!GetLastError` at `0x1800728d1`
- `KERNEL32!GetLastError` at `0x180072926`
- `KERNEL32!SetLastError` at `0x1800728cb`
- `KERNEL32!SetLastError` at `0x1800728cb`
- `KERNEL32!CreateFileW` at `0x18007283a`
- `KERNEL32!CreateFileW` at `0x18007283a`
- `KERNEL32!GetFileType` at `0x180072850`
- `KERNEL32!GetFileType` at `0x180072850`
- `KERNEL32!GetFileTime` at `0x18007291c`
- `KERNEL32!GetFileTime` at `0x18007291c`

## string_xrefs

- `0x180072889`: `Error: This is not a valid file, hence failing to create: %s`

## pseudocode

```c

```
