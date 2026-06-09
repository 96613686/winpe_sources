# CMsiPath::FileDate(ushort const *,MsiDate &)

- ea: `0x180220360`
- end: `0x1802206bc`
- name: `?FileDate@CMsiPath@@UEAAPEAVIMsiRecord@@PEBGAEAW4MsiDate@@@Z`
- size: `860`
- prototype: `struct IMsiRecord *__fastcall(CMsiPath *__hidden this, const unsigned __int16 *, enum MsiDate *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update`

## callees

- `0x18000c4bc`
- `0x180097540`
- `0x180097c78`
- `0x18009cdb8`
- `0x18009d06c`
- `0x18013fa30`
- `0x180153e68`
- `0x180220360`
- `0x180266010`

## import_xrefs

- `KERNEL32!FileTimeToDosDateTime` at `0x180220663`
- `KERNEL32!FileTimeToDosDateTime` at `0x180220663`
- `KERNEL32!CloseHandle` at `0x180220540`
- `KERNEL32!CloseHandle` at `0x1802205cd`
- `KERNEL32!CloseHandle` at `0x180220540`
- `KERNEL32!CloseHandle` at `0x1802205cd`
- `KERNEL32!GetLastError` at `0x18022055d`
- `KERNEL32!GetLastError` at `0x1802205b1`
- `KERNEL32!GetLastError` at `0x180220635`
- `KERNEL32!GetLastError` at `0x18022055d`
- `KERNEL32!GetLastError` at `0x1802205b1`
- `KERNEL32!GetLastError` at `0x180220635`
- `KERNEL32!SetLastError` at `0x180220551`
- `KERNEL32!SetLastError` at `0x180220551`
- `KERNEL32!CreateFileW` at `0x1802204af`
- `KERNEL32!CreateFileW` at `0x1802204af`
- `KERNEL32!GetFileType` at `0x1802204cb`
- `KERNEL32!GetFileType` at `0x1802204cb`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180220612`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180220612`
- `KERNEL32!GetFileTime` at `0x18022059a`
- `KERNEL32!GetFileTime` at `0x18022059a`

## string_xrefs

- `0x180220509`: `Error: This is not a valid file, hence failing to create: %s`

## pseudocode

```c

```
