# SecureLoadModule(ushort const *,bool,HINSTANCE__ * *)

- ea: `0x1800d6134`
- end: `0x1800d62bb`
- name: `?SecureLoadModule@@YAJPEBG_NPEAPEAUHINSTANCE__@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(wchar_t *Source, bool, HINSTANCE *)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18026a9fc`
- `0x180286ba4`
- `0x18039fd70`

## callees

- `0x1800793cc`
- `0x1800d6134`
- `0x1800d62c4`
- `0x1800d6534`
- `0x1800d6560`
- `0x1800f0f40`
- `0x180378284`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1800d61f0`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1800d61f0`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800d6206`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800d6206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d621f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d623f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d621f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d623f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6256`

## string_xrefs

- `0x1800d6233`: `CLRDLL: LoadLibrary(%s) failed, Win32 error %d\n`

## pseudocode

```c

```
