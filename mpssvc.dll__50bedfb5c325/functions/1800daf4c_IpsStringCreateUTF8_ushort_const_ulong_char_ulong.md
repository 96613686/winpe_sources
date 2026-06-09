# IpsStringCreateUTF8(ushort const *,ulong,char * *,ulong *)

- ea: `0x1800daf4c`
- end: `0x1800db0ab`
- name: `?IpsStringCreateUTF8@@YAKPEBGKPEAPEADPEAK@Z`
- size: `351`
- prototype: `unsigned int __fastcall(LPCWCH lpWideCharStr, unsigned int cchWideChar, char **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800e0a28`

## callees

- `0x1800089bc`
- `0x18004b9a0`
- `0x18004f4ac`
- `0x18006e384`
- `0x1800daf4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dafb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db02d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dafb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db02d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800dafa0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800db01b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800dafa0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800db01b`
- `fwbase!FwFree` at `0x1800db05f`
- `fwbase!FwFree` at `0x1800db05f`

## string_xrefs

- `0x1800db048`: `IpsStringCreateUTF8`
- `0x1800db082`: `IpsStringCreateUTF8`

## pseudocode

```c

```
