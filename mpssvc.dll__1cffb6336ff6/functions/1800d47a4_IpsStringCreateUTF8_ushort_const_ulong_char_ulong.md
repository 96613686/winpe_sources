# IpsStringCreateUTF8(ushort const *,ulong,char * *,ulong *)

- ea: `0x1800d47a4`
- end: `0x1800d48e4`
- name: `?IpsStringCreateUTF8@@YAKPEBGKPEAPEADPEAK@Z`
- size: `320`
- prototype: `unsigned int __fastcall(LPCWCH lpWideCharStr, unsigned int cchWideChar, char **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800da59c`

## callees

- `0x1800093b0`
- `0x18004983c`
- `0x18004c284`
- `0x18006b2b8`
- `0x1800d47a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4804`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4804`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4873`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800d47f8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800d4867`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800d47f8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800d4867`
- `fwbase!FwFree` at `0x1800d489f`
- `fwbase!FwFree` at `0x1800d489f`

## string_xrefs

- `0x1800d4888`: `IpsStringCreateUTF8`
- `0x1800d48bc`: `IpsStringCreateUTF8`

## pseudocode

```c

```
