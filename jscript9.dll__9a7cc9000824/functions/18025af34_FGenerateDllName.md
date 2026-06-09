# FGenerateDllName

- ea: `0x18025af34`
- end: `0x18025b02f`
- name: `FGenerateDllName`
- size: `251`
- prototype: `int __fastcall(wchar_t *Destination, __int64, LCID)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18025b0f4`

## callees

- `0x18025af34`
- `0x1803481f0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18025afee`
- `msvcrt!wcscat_s` at `0x18025b006`
- `msvcrt!wcscat_s` at `0x18025afee`
- `msvcrt!wcscat_s` at `0x18025b006`
- `msvcrt!wcscpy_s` at `0x18025afd8`
- `msvcrt!wcscpy_s` at `0x18025afd8`
- `KERNEL32!GetLocaleInfoW` at `0x18025af77`
- `KERNEL32!GetLocaleInfoW` at `0x18025af77`

## pseudocode

```c

```
