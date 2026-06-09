# CMsiPath::FileDate(ushort const *,MsiDate &)

- ea: `0x1802168c0`
- end: `0x180216bd9`
- name: `?FileDate@CMsiPath@@UEAAPEAVIMsiRecord@@PEBGAEAW4MsiDate@@@Z`
- size: `793`
- prototype: `struct IMsiRecord *__fastcall(CMsiPath *__hidden this, const unsigned __int16 *, enum MsiDate *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update`

## callees

- `0x180025a18`
- `0x180027b54`
- `0x1800713d0`
- `0x180083178`
- `0x1800833ec`
- `0x18013a830`
- `0x18014e4d4`
- `0x1802168c0`
- `0x18025c010`

## import_xrefs

- `KERNEL32!FileTimeToDosDateTime` at `0x180216b87`
- `KERNEL32!FileTimeToDosDateTime` at `0x180216b87`
- `KERNEL32!CloseHandle` at `0x180216a94`
- `KERNEL32!CloseHandle` at `0x180216b03`
- `KERNEL32!CloseHandle` at `0x180216a94`
- `KERNEL32!CloseHandle` at `0x180216b03`
- `KERNEL32!GetLastError` at `0x180216aa5`
- `KERNEL32!GetLastError` at `0x180216aed`
- `KERNEL32!GetLastError` at `0x180216b5f`
- `KERNEL32!GetLastError` at `0x180216aa5`
- `KERNEL32!GetLastError` at `0x180216aed`
- `KERNEL32!GetLastError` at `0x180216b5f`
- `KERNEL32!SetLastError` at `0x180216a9f`
- `KERNEL32!SetLastError` at `0x180216a9f`
- `KERNEL32!CreateFileW` at `0x180216a0f`
- `KERNEL32!CreateFileW` at `0x180216a0f`
- `KERNEL32!GetFileType` at `0x180216a25`
- `KERNEL32!GetFileType` at `0x180216a25`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180216b42`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180216b42`
- `KERNEL32!GetFileTime` at `0x180216adc`
- `KERNEL32!GetFileTime` at `0x180216adc`

## string_xrefs

- `0x180216a5d`: `Error: This is not a valid file, hence failing to create: %s`

## pseudocode

```c

```
