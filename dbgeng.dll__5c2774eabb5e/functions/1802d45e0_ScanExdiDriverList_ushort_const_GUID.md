# ScanExdiDriverList(ushort const *,_GUID *)

- ea: `0x1802d45e0`
- end: `0x1802d47a7`
- name: `?ScanExdiDriverList@@YAJPEBGPEAU_GUID@@@Z`
- size: `455`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1802c7380`

## callees

- `0x18007cf9c`
- `0x1800830a0`
- `0x18008d550`
- `0x1800f0f40`
- `0x1802d45e0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsupr` at `0x1802d4656`
- `api-ms-win-crt-string-l1-1-0!_wcsupr` at `0x1802d4656`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x1802d468c`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x1802d468c`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1802d476b`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1802d476b`
- `api-ms-win-core-localregistry-l1-1-0!RegEnumValueW` at `0x1802d46fe`
- `api-ms-win-core-localregistry-l1-1-0!RegEnumValueW` at `0x1802d46fe`
- `dbghelp!SymMatchStringW` at `0x1802d4733`
- `dbghelp!SymMatchStringW` at `0x1802d4733`

## pseudocode

```c

```
