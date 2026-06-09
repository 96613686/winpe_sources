# CMsiFileCopy::OpenSource(bool)

- ea: `0x18007ec4c`
- end: `0x18007f00c`
- name: `?OpenSource@CMsiFileCopy@@IEAAPEAVIMsiRecord@@_N@Z`
- size: `960`
- prototype: `struct IMsiRecord *__fastcall(CMsiFileCopy *__hidden this, bool)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, installer_update`

## callers

- `0x18007de60`
- `0x18007ec4c`

## callees

- `0x18000c4bc`
- `0x180016154`
- `0x18007dd00`
- `0x18007ec4c`
- `0x18007f0c0`
- `0x18009ca0c`
- `0x18009cdb8`
- `0x18009d06c`
- `0x180128db0`
- `0x18013fa30`
- `0x18014676c`
- `0x180153e68`
- `0x180266010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18007ee25`
- `KERNEL32!CloseHandle` at `0x18007eebc`
- `KERNEL32!CloseHandle` at `0x18007ee25`
- `KERNEL32!CloseHandle` at `0x18007eebc`
- `KERNEL32!GetLastError` at `0x18007edba`
- `KERNEL32!GetLastError` at `0x18007eedd`
- `KERNEL32!GetLastError` at `0x18007edba`
- `KERNEL32!GetLastError` at `0x18007eedd`
- `KERNEL32!SetLastError` at `0x18007ee37`
- `KERNEL32!SetLastError` at `0x18007eed1`
- `KERNEL32!SetLastError` at `0x18007ee37`
- `KERNEL32!SetLastError` at `0x18007eed1`
- `KERNEL32!CreateFileW` at `0x18007ed87`
- `KERNEL32!CreateFileW` at `0x18007ed87`
- `KERNEL32!GetFileType` at `0x18007ee50`
- `KERNEL32!GetFileType` at `0x18007ee50`

## string_xrefs

- `0x18007ee7f`: `Error: This is not a valid file, hence failing to create: %s`
- `0x18007ede8`: `Error: This file path is updated, hence failing to create: %s`

## pseudocode

```c

```
