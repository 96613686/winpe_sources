# GetWindowsPKeyInfo

- ea: `0x1800bc1b0`
- end: `0x1800bc4c3`
- name: `GetWindowsPKeyInfo`
- size: `787`
- prototype: `__int64 __fastcall(_WORD *, __int64, __int64, _OWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800bc4cc`

## callees

- `0x180003470`
- `0x180003ffc`
- `0x1800ba2dc`
- `0x1800ba518`
- `0x1800ba648`
- `0x1800babac`
- `0x1800bb814`
- `0x1800bbb94`
- `0x1800bbbc0`
- `0x1800bbdb0`
- `0x1800bc1b0`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800bc271`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800bc271`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc2ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc2ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc28e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc28e`
- `KERNEL32!GetFileAttributesW` at `0x1800bc32a`
- `KERNEL32!GetFileAttributesW` at `0x1800bc32a`

## string_xrefs

- `0x1800bc2c4`: `%windir%\system32\spp\tokens\pkeyconfig`

## pseudocode

```c

```
