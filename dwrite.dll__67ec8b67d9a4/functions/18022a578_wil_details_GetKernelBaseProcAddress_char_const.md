# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18022a578`
- end: `0x18022a5c9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180228280`

## callees

- `0x18022a578`

## import_xrefs

- `kernel32!GetProcAddress` at `0x18022a5b2`
- `kernel32!GetProcAddress` at `0x18022a5b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18022a59a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18022a59a`

## string_xrefs

- `0x18022a591`: `kernelbase.dll`

## pseudocode

```c

```
