# IsPortAlink

- ea: `0x1800e0b94`
- end: `0x1800e0d71`
- name: `IsPortAlink`
- size: `477`
- prototype: `__int64 __fastcall(const wchar_t *, void *)`
- caller_count: `3`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callers

- `0x180074780`
- `0x18008be6c`
- `0x1800deab0`

## callees

- `0x180046650`
- `0x180047330`
- `0x1800df3e0`
- `0x1800df488`
- `0x1800e0a14`
- `0x1800e0b94`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800e0c88`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800e0c99`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800e0caf`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800e0c88`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800e0c99`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800e0caf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800e0c65`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800e0cc0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800e0c65`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800e0cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0d34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0d34`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800e0c44`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800e0c44`
- `SPOOLSS!DllFreeSplMem` at `0x1800e0d2c`
- `SPOOLSS!DllFreeSplMem` at `0x1800e0d2c`
- `KERNEL32!GetFileInformationByHandle` at `0x1800e0cf4`
- `KERNEL32!GetFileInformationByHandle` at `0x1800e0cf4`

## string_xrefs

- `0x1800e0c06`: `IsPortAlink`
- `0x1800e0cd9`: `IsPortAlink`
- `0x1800e0d0f`: `IsPortAlink`
- `0x1800e0d08`: `The requested file port is a hardlink and hence it is an invalid request. Requested file port: %ws`
- `0x1800e0cd2`: `The requested file port is a symlink and hence it is an invalid request. Requested file port: %ws, Actual file port: %ws`

## pseudocode

```c

```
