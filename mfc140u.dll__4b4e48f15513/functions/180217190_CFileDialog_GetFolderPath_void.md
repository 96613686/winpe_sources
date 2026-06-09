# CFileDialog::GetFolderPath(void)

- ea: `0x180217190`
- end: `0x18021740a`
- name: `?GetFolderPath@CFileDialog@@QEBA?AV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@XZ`
- size: `634`
- prototype: `ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *__fastcall(CFileDialog *this, ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *result)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x180003230`
- `0x1800033dc`
- `0x180003450`
- `0x180217190`
- `0x180296d00`
- `0x1802c7020`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x1802172cc`
- `VCRUNTIME140!memmove` at `0x1802172cc`
- `VCRUNTIME140!memset` at `0x1802172fa`
- `VCRUNTIME140!memset` at `0x1802172fa`
- `VCRUNTIME140!memcpy` at `0x1802172f0`
- `VCRUNTIME140!memcpy` at `0x1802172f0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18021730c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18021730c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802172aa`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180217300`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802172aa`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180217300`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18021724f`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18021724f`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1802173c3`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1802173c3`
- `USER32!SendMessageW` at `0x18021739d`
- `USER32!SendMessageW` at `0x18021739d`
- `USER32!GetParent` at `0x18021735f`
- `USER32!GetParent` at `0x18021735f`
- `ole32!CoTaskMemFree` at `0x18021733b`
- `ole32!CoTaskMemFree` at `0x18021733b`

## pseudocode

```c

```
