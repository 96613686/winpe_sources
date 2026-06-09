# WEB_ADMIN_SERVICE::DetermineCurrentDirectory(void)

- ea: `0x1800049a4`
- end: `0x180004b78`
- name: `?DetermineCurrentDirectory@WEB_ADMIN_SERVICE@@AEAAJXZ`
- size: `468`
- prototype: `__int64 __fastcall(WEB_ADMIN_SERVICE *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000512c`

## callees

- `0x1800049a4`
- `0x180061060`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180004a8d`
- `msvcrt!wcsrchr` at `0x180004a8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004a3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004a3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800049cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800049cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a52`
- `iisutil!PuDbgPrint` at `0x180004b4f`
- `iisutil!PuDbgPrint` at `0x180004b4f`
- `iisutil!PuDbgPrintError` at `0x180004a25`
- `iisutil!PuDbgPrintError` at `0x180004a25`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004ade`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004ade`

## string_xrefs

- `0x1800049c6`: `iisw3adm.dll`
- `0x180004a1e`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180004b31`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180004a17`: `WEB_ADMIN_SERVICE::DetermineCurrentDirectory`
- `0x180004b23`: `WEB_ADMIN_SERVICE::DetermineCurrentDirectory`
- `0x180004b43`: `Current directory: %S\n`

## pseudocode

```c

```
