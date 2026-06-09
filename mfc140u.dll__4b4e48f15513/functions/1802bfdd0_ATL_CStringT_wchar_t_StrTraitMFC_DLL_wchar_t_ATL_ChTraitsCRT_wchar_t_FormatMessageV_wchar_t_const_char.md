# ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::FormatMessageV(wchar_t const *,char * *)

- ea: `0x1802bfdd0`
- end: `0x1802bff7c`
- name: `?FormatMessageV@?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAAXPEB_WPEAPEAD@Z`
- size: `428`
- prototype: `void __fastcall(ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *this, const wchar_t *pszFormat, char **pArgList)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1802c4480`
- `0x1802c4590`

## callees

- `0x1800031d0`
- `0x180003230`
- `0x1800033dc`
- `0x180003450`
- `0x1802bfdd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1802bfdf7`
- `KERNEL32!GetLastError` at `0x1802bfe36`
- `KERNEL32!GetLastError` at `0x1802bfdf7`
- `KERNEL32!GetLastError` at `0x1802bfe36`
- `KERNEL32!SetLastError` at `0x1802bfe01`
- `KERNEL32!SetLastError` at `0x1802bfe46`
- `KERNEL32!SetLastError` at `0x1802bfe01`
- `KERNEL32!SetLastError` at `0x1802bfe46`
- `KERNEL32!LocalFree` at `0x1802bff4e`
- `KERNEL32!LocalFree` at `0x1802bff4e`
- `KERNEL32!FormatMessageW` at `0x1802bfe2c`
- `KERNEL32!FormatMessageW` at `0x1802bfe2c`
- `VCRUNTIME140!memmove` at `0x1802bfed4`
- `VCRUNTIME140!memmove` at `0x1802bfed4`
- `VCRUNTIME140!memset` at `0x1802bff10`
- `VCRUNTIME140!memset` at `0x1802bff10`
- `VCRUNTIME140!memcpy` at `0x1802bff06`
- `VCRUNTIME140!memcpy` at `0x1802bff06`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1802bff22`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1802bff22`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802bfeed`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802bff16`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802bfeed`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802bff16`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1802bfe60`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1802bfe60`

## pseudocode

```c

```
