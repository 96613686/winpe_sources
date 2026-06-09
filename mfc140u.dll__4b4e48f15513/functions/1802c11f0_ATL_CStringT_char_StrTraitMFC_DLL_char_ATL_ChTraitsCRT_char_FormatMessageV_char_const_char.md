# ATL::CStringT<char,StrTraitMFC_DLL<char,ATL::ChTraitsCRT<char>>>::FormatMessageV(char const *,char * *)

- ea: `0x1802c11f0`
- end: `0x1802c137d`
- name: `?FormatMessageV@?$CStringT@DV?$StrTraitMFC_DLL@DV?$ChTraitsCRT@D@ATL@@@@@ATL@@QEAAXPEBDPEAPEAD@Z`
- size: `397`
- prototype: `void __fastcall(ATL::CStringT<char,StrTraitMFC_DLL<char,ATL::ChTraitsCRT<char> > > *this, const char *pszFormat, char **pArgList)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1802c3f60`
- `0x1802c4070`

## callees

- `0x1800031d0`
- `0x1800033dc`
- `0x1801d5fa0`
- `0x1801d6090`
- `0x1802c11f0`

## import_xrefs

- `KERNEL32!FormatMessageA` at `0x1802c1248`
- `KERNEL32!FormatMessageA` at `0x1802c1248`
- `KERNEL32!GetLastError` at `0x1802c1216`
- `KERNEL32!GetLastError` at `0x1802c1252`
- `KERNEL32!GetLastError` at `0x1802c1216`
- `KERNEL32!GetLastError` at `0x1802c1252`
- `KERNEL32!SetLastError` at `0x1802c1220`
- `KERNEL32!SetLastError` at `0x1802c1262`
- `KERNEL32!SetLastError` at `0x1802c1220`
- `KERNEL32!SetLastError` at `0x1802c1262`
- `KERNEL32!LocalFree` at `0x1802c134d`
- `KERNEL32!LocalFree` at `0x1802c134d`
- `VCRUNTIME140!memmove` at `0x1802c12ed`
- `VCRUNTIME140!memmove` at `0x1802c12ed`
- `VCRUNTIME140!memset` at `0x1802c1313`
- `VCRUNTIME140!memset` at `0x1802c1313`
- `VCRUNTIME140!memcpy` at `0x1802c1309`
- `VCRUNTIME140!memcpy` at `0x1802c1309`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1802c1325`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1802c1325`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802c12ce`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802c1319`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802c12ce`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802c1319`
- `api-ms-win-crt-string-l1-1-0!strlen` at `0x1802c1279`
- `api-ms-win-crt-string-l1-1-0!strlen` at `0x1802c1279`

## pseudocode

```c

```
