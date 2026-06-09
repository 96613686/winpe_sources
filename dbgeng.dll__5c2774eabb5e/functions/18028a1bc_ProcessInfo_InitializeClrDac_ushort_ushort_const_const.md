# ProcessInfo::InitializeClrDac(ushort *,ushort const * const)

- ea: `0x18028a1bc`
- end: `0x18028a2dd`
- name: `?InitializeClrDac@ProcessInfo@@AEAAJPEAGQEBG@Z`
- size: `289`
- prototype: `int(ProcessInfo *__hidden this, unsigned __int16 *, const unsigned __int16 *const)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800b9c94`
- `0x180286ba4`

## callees

- `0x1800727b8`
- `0x180073230`
- `0x1800793cc`
- `0x18028a1bc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18028a22c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18028a22c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18028a1de`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18028a1de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18028a1f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18028a20a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18028a1f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18028a20a`

## string_xrefs

- `0x18028a1d4`: `CLRDataCreateInstance`
- `0x18028a270`: `CLRDLL: %s\n`
- `0x18028a2c3`: `CLRDLL: %s\n`
- `0x18028a24d`: `ERROR: DLL %s missing entry point`
- `0x18028a2a0`: `Loaded DLL %s`

## pseudocode

```c

```
