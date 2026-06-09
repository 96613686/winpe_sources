# SITE_DATA_OBJECT_TABLE_DYNAMIC::QueryContainsNonHttpProtocol(IAppHostSite *,int *)

- ea: `0x18004eaf8`
- end: `0x18004ecef`
- name: `?QueryContainsNonHttpProtocol@SITE_DATA_OBJECT_TABLE_DYNAMIC@@AEAAJPEAUIAppHostSite@@PEAH@Z`
- size: `503`
- prototype: `__int64 __fastcall(SITE_DATA_OBJECT_TABLE_DYNAMIC *__hidden this, struct IAppHostSite *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004edc0`

## callees

- `0x18004eaf8`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004ec52`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ec85`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ec52`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ec85`
- `iisutil!PuDbgPrint` at `0x18004ec1e`
- `iisutil!PuDbgPrint` at `0x18004ec1e`
- `iisutil!PuDbgPrintError` at `0x18004eb78`
- `iisutil!PuDbgPrintError` at `0x18004eb78`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18004ec2f`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18004ec44`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18004ec2f`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18004ec44`

## string_xrefs

- `0x18004ecdd`: ` Failed getting the protocol string \n`
- `0x18004ec06`: ` Protocol '%S' \n`
- `0x18004eb6d`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_apphost.cxx`
- `0x18004ebfb`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_apphost.cxx`
- `0x18004eb61`: `SITE_DATA_OBJECT_TABLE_DYNAMIC::QueryContainsNonHttpProtocol`
- `0x18004ebee`: `SITE_DATA_OBJECT_TABLE_DYNAMIC::QueryContainsNonHttpProtocol`

## pseudocode

```c

```
