# DsrCmdRecovery::LoadResString(uint,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800a8cc0`
- end: `0x1800a8d8f`
- name: `?LoadResString@DsrCmdRecovery@@CAJIAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `207`
- prototype: `__int64 __fastcall(UINT uID)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800a8fe8`

## callees

- `0x18001327c`
- `0x180016b90`
- `0x18002b9b4`
- `0x180044300`
- `0x1800a8cc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8d0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8d0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a8cee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a8cee`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a8d01`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800a8d01`

## string_xrefs

- `0x1800a8ce4`: `dsreg.dll`

## pseudocode

```c

```
