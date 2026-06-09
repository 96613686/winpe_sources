# SITE_DATA_OBJECT_APPHOST::SetBindings(IAppHostSite *,BINDING_INFO_WRITER *)

- ea: `0x18004eecc`
- end: `0x18004f273`
- name: `?SetBindings@SITE_DATA_OBJECT_APPHOST@@QEAAJPEAUIAppHostSite@@PEAVBINDING_INFO_WRITER@@@Z`
- size: `935`
- prototype: `__int64 __fastcall(SITE_DATA_OBJECT_APPHOST *__hidden this, struct IAppHostSite *, struct BINDING_INFO_WRITER *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004e444`

## callees

- `0x18004eecc`
- `0x180051254`
- `0x1800515b0`
- `0x1800570f4`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004f11b`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f129`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f204`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f21e`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f11b`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f129`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f204`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f21e`
- `iisutil!PuDbgPrint` at `0x18004efde`
- `iisutil!PuDbgPrint` at `0x18004f04c`
- `iisutil!PuDbgPrint` at `0x18004f0dc`
- `iisutil!PuDbgPrint` at `0x18004efde`
- `iisutil!PuDbgPrint` at `0x18004f04c`
- `iisutil!PuDbgPrint` at `0x18004f0dc`
- `iisutil!PuDbgPrintError` at `0x18004f1dc`
- `iisutil!PuDbgPrintError` at `0x18004f1dc`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18004f076`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18004f076`

## string_xrefs

- `0x18004f1b9`: ` Failed getting the protocol string \n`
- `0x18004efc6`: ` Protocol '%S' \n`
- `0x18004f159`: ` Failed adding the binding info to BINDING_INFO_WRITER \n`
- `0x18004ef37`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_apphost.cxx`
- `0x18004ef4a`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_apphost.cxx`

## pseudocode

```c

```
