# CMsiPath::IsFileModified(ushort const *,Bool &)

- ea: `0x180112250`
- end: `0x180112622`
- name: `?IsFileModified@CMsiPath@@UEAAPEAVIMsiRecord@@PEBGAEAW4Bool@@@Z`
- size: `978`
- prototype: `struct IMsiRecord *__fastcall(CMsiPath *__hidden this, const unsigned __int16 *, enum Bool *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callees

- `0x18000c4bc`
- `0x18001e254`
- `0x180097608`
- `0x180097c78`
- `0x18009cdb8`
- `0x18009d06c`
- `0x180112250`
- `0x18014676c`
- `0x180153e68`
- `0x180266010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801124c2`
- `KERNEL32!CloseHandle` at `0x18011255b`
- `KERNEL32!CloseHandle` at `0x180112598`
- `KERNEL32!CloseHandle` at `0x1801124c2`
- `KERNEL32!CloseHandle` at `0x18011255b`
- `KERNEL32!CloseHandle` at `0x180112598`
- `KERNEL32!GetLastError` at `0x180112360`
- `KERNEL32!GetLastError` at `0x1801124df`
- `KERNEL32!GetLastError` at `0x180112540`
- `KERNEL32!GetLastError` at `0x180112360`
- `KERNEL32!GetLastError` at `0x1801124df`
- `KERNEL32!GetLastError` at `0x180112540`
- `KERNEL32!SetLastError` at `0x1801124d3`
- `KERNEL32!SetLastError` at `0x1801124d3`
- `KERNEL32!CreateFileW` at `0x180112430`
- `KERNEL32!CreateFileW` at `0x180112430`
- `KERNEL32!GetFileType` at `0x18011244c`
- `KERNEL32!GetFileType` at `0x18011244c`
- `KERNEL32!GetFileTime` at `0x180112530`
- `KERNEL32!GetFileTime` at `0x180112530`

## string_xrefs

- `0x18011248b`: `Error: This is not a valid file, hence failing to create: %s`

## pseudocode

```c

```
