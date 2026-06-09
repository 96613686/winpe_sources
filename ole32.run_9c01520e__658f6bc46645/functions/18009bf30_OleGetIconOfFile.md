# OleGetIconOfFile

- ea: `0x18009bf30`
- end: `0x18009c27f`
- name: `OleGetIconOfFile`
- size: `847`
- prototype: `HGLOBAL __stdcall(LPOLESTR lpszPath, BOOL fUseFileAsLabel)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18007d268`

## callees

- `0x1800077fc`
- `0x18001a630`
- `0x180046460`
- `0x180047484`
- `0x180053814`
- `0x18009ab88`
- `0x18009af0c`
- `0x18009b454`
- `0x18009bf30`
- `0x18009c290`
- `0x1800c8934`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18009c139`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18009c139`
- `USER32!DestroyIcon` at `0x18009c001`
- `USER32!DestroyIcon` at `0x18009c23f`
- `USER32!DestroyIcon` at `0x18009c001`
- `USER32!DestroyIcon` at `0x18009c23f`
- `USER32!LoadIconW` at `0x18009c164`
- `USER32!LoadIconW` at `0x18009c164`
- `SHELL32!ExtractAssociatedIconW` at `0x18009c10b`
- `SHELL32!ExtractAssociatedIconW` at `0x18009c10b`
- `SHELL32!SHGetFileInfoW` at `0x18009bfe1`
- `SHELL32!SHGetFileInfoW` at `0x18009bfe1`

## pseudocode

```c

```
