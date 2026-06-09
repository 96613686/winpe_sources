# CreateFileStream(ushort const *,Bool,IMsiStream * &)

- ea: `0x180251a18`
- end: `0x180251c4e`
- name: `?CreateFileStream@@YAPEAVIMsiRecord@@PEBGW4Bool@@AEAPEAVIMsiStream@@@Z`
- size: `566`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x18008d67c`
- `0x1800a7b14`
- `0x18015ef70`
- `0x1801bb990`
- `0x1801d3df8`

## callees

- `0x18000c4bc`
- `0x180013fe4`
- `0x180016154`
- `0x180018ee0`
- `0x18001e254`
- `0x18009cdb8`
- `0x18009d06c`
- `0x1800a570c`
- `0x18013fa30`
- `0x180251a18`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180251b30`
- `KERNEL32!CloseHandle` at `0x180251c29`
- `KERNEL32!CloseHandle` at `0x180251b30`
- `KERNEL32!CloseHandle` at `0x180251c29`
- `KERNEL32!GetLastError` at `0x180251b50`
- `KERNEL32!GetLastError` at `0x180251b50`
- `KERNEL32!SetLastError` at `0x180251b44`
- `KERNEL32!SetLastError` at `0x180251b44`
- `KERNEL32!CreateFileW` at `0x180251ab2`
- `KERNEL32!CreateFileW` at `0x180251ab2`
- `KERNEL32!GetFileType` at `0x180251acd`
- `KERNEL32!GetFileType` at `0x180251acd`
- `KERNEL32!GetFileSize` at `0x180251b87`
- `KERNEL32!GetFileSize` at `0x180251b87`

## string_xrefs

- `0x180251afb`: `Error: This is not a valid file, hence failing to create: %s`

## pseudocode

```c

```
