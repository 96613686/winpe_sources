# OleGetIconOfFile

- ea: `0x180099e50`
- end: `0x18009a156`
- name: `OleGetIconOfFile`
- size: `774`
- prototype: `HGLOBAL __stdcall(LPOLESTR lpszPath, BOOL fUseFileAsLabel)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180083360`

## callees

- `0x180009374`
- `0x18001b810`
- `0x18004f860`
- `0x180052390`
- `0x180053014`
- `0x180061754`
- `0x180099274`
- `0x180099584`
- `0x180099e50`
- `0x18009a160`
- `0x1800bf6c4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18009a034`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18009a034`
- `USER32!DestroyIcon` at `0x180099f07`
- `USER32!DestroyIcon` at `0x18009a12a`
- `USER32!DestroyIcon` at `0x180099f07`
- `USER32!DestroyIcon` at `0x18009a12a`
- `USER32!LoadIconW` at `0x18009a055`
- `USER32!LoadIconW` at `0x18009a055`
- `SHELL32!ExtractAssociatedIconW` at `0x18009a00a`
- `SHELL32!ExtractAssociatedIconW` at `0x18009a00a`
- `SHELL32!SHGetFileInfoW` at `0x180099eed`
- `SHELL32!SHGetFileInfoW` at `0x180099eed`

## pseudocode

```c

```
