# SITE_DATA_OBJECT_TABLE_APPHOST::InsertData(IAppHostSite *,APPLICATION_DATA_OBJECT_TABLE_APPHOST *,BINDING_INFO_WRITER *,CONFIG_DATA_INSERT *,MULTISZ *)

- ea: `0x18004e444`
- end: `0x18004e88c`
- name: `?InsertData@SITE_DATA_OBJECT_TABLE_APPHOST@@QEAAJPEAUIAppHostSite@@PEAVAPPLICATION_DATA_OBJECT_TABLE_APPHOST@@PEAVBINDING_INFO_WRITER@@PEAUCONFIG_DATA_INSERT@@PEAVMULTISZ@@@Z`
- size: `1096`
- prototype: `int(SITE_DATA_OBJECT_TABLE_APPHOST *__hidden this, struct IAppHostSite *, struct APPLICATION_DATA_OBJECT_TABLE_APPHOST *, struct BINDING_INFO_WRITER *, struct CONFIG_DATA_INSERT *, struct MULTISZ *)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004ed00`
- `0x18004edc0`
- `0x18005a76c`

## callees

- `0x180001234`
- `0x180039738`
- `0x18003a0a8`
- `0x18004e094`
- `0x18004e444`
- `0x18004eecc`
- `0x18004f27c`
- `0x18004f468`
- `0x18004f680`
- `0x18004fdf0`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e77f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e77f`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18004e7c5`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18004e7c5`
- `iisutil!PuDbgPrint` at `0x18004e549`
- `iisutil!PuDbgPrint` at `0x18004e549`
- `iisutil!PuDbgPrintError` at `0x18004e4e8`
- `iisutil!PuDbgPrintError` at `0x18004e64a`
- `iisutil!PuDbgPrintError` at `0x18004e4e8`
- `iisutil!PuDbgPrintError` at `0x18004e64a`
- `iisutil!?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z` at `0x18004e759`
- `iisutil!?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z` at `0x18004e759`
- `iisutil!?FastAppend@MULTISZ@@QEAAHPEBG@Z` at `0x18004e76a`
- `iisutil!?FastAppend@MULTISZ@@QEAAHPEBG@Z` at `0x18004e76a`

## string_xrefs

- `0x18004e4e1`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_apphost.cxx`
- `0x18004e511`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_apphost.cxx`

## pseudocode

```c

```
