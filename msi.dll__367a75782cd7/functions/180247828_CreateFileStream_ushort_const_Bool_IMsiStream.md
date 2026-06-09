# CreateFileStream(ushort const *,Bool,IMsiStream * &)

- ea: `0x180247828`
- end: `0x180247a2f`
- name: `?CreateFileStream@@YAPEAVIMsiRecord@@PEBGW4Bool@@AEAPEAVIMsiStream@@@Z`
- size: `519`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x1800437b8`
- `0x18009f870`
- `0x1801593b0`
- `0x1801b3ba0`
- `0x1801cb538`

## callees

- `0x180024f9c`
- `0x180025a18`
- `0x180026ffc`
- `0x18003a9c0`
- `0x180061334`
- `0x180083178`
- `0x1800833ec`
- `0x1801332f0`
- `0x18013a830`
- `0x180247828`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180247930`
- `KERNEL32!CloseHandle` at `0x180247a11`
- `KERNEL32!CloseHandle` at `0x180247930`
- `KERNEL32!CloseHandle` at `0x180247a11`
- `KERNEL32!GetLastError` at `0x180247944`
- `KERNEL32!GetLastError` at `0x180247944`
- `KERNEL32!SetLastError` at `0x18024793e`
- `KERNEL32!SetLastError` at `0x18024793e`
- `KERNEL32!CreateFileW` at `0x1802478c2`
- `KERNEL32!CreateFileW` at `0x1802478c2`
- `KERNEL32!GetFileType` at `0x1802478d3`
- `KERNEL32!GetFileType` at `0x1802478d3`
- `KERNEL32!GetFileSize` at `0x180247975`
- `KERNEL32!GetFileSize` at `0x180247975`

## string_xrefs

- `0x1802478fb`: `Error: This is not a valid file, hence failing to create: %s`

## pseudocode

```c

```
