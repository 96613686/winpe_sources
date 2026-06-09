# ResolveTokenVar(ulong,ushort const *,void *,DbsDynamicString<ushort> *)

- ea: `0x180297c58`
- end: `0x180297d8c`
- name: `?ResolveTokenVar@@YAJKPEBGPEAXPEAV?$DbsDynamicString@G@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(unsigned int, PCWSTR VarName, PVOID Token)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18019d820`

## callees

- `0x18007be30`
- `0x18009543c`
- `0x180297c58`
- `0x180415948`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x180297d6c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180297d6c`
- `api-ms-win-crt-string-l1-1-0!_wcsdup` at `0x180297c84`
- `api-ms-win-crt-string-l1-1-0!_wcsdup` at `0x180297c84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180297d22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180297d39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180297d22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180297d39`
- `dbghelp!SymGetSourceVarFromTokenW` at `0x180297d0e`
- `dbghelp!SymGetSourceVarFromTokenW` at `0x180297d0e`

## pseudocode

```c

```
