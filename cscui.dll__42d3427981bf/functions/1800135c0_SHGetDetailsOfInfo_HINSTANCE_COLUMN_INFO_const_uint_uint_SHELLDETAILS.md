# SHGetDetailsOfInfo(HINSTANCE__ *,COLUMN_INFO const *,uint,uint,_SHELLDETAILS *)

- ea: `0x1800135c0`
- end: `0x180013726`
- name: `?SHGetDetailsOfInfo@@YAJPEAUHINSTANCE__@@PEBUCOLUMN_INFO@@IIPEAU_SHELLDETAILS@@@Z`
- size: `358`
- prototype: `__int64 __fastcall(HINSTANCE, const struct COLUMN_INFO *, unsigned int, unsigned int, struct _SHELLDETAILS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012e20`

## callees

- `0x1800135c0`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x180013632`
- `SHLWAPI!SHStrDupW` at `0x1800136b9`
- `SHLWAPI!SHStrDupW` at `0x1800136f2`
- `SHLWAPI!SHStrDupW` at `0x180013632`
- `SHLWAPI!SHStrDupW` at `0x1800136b9`
- `SHLWAPI!SHStrDupW` at `0x1800136f2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180013623`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180013623`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013666`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013666`

## pseudocode

```c

```
