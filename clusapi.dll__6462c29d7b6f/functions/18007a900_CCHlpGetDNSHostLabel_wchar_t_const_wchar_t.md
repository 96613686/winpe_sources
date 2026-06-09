# CCHlpGetDNSHostLabel(wchar_t const *,wchar_t * *)

- ea: `0x18007a900`
- end: `0x18007aa79`
- name: `?CCHlpGetDNSHostLabel@@YAJPEB_WPEAPEA_W@Z`
- size: `377`
- prototype: `__int64 __fastcall(const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003aff4`

## callees

- `0x1800395ec`
- `0x18006f910`
- `0x18007a900`
- `0x18009ef90`
- `0x1800b5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007aa50`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007aa50`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007a930`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007a930`
- `OLEAUT32!__imp_SysFreeString` at `0x18007aa2e`
- `OLEAUT32!__imp_SysFreeString` at `0x18007aa2e`

## string_xrefs

- `0x18007a96d`: `Unable to obtain the setup interface from cprep.dll. Error %d.`

## pseudocode

```c

```
