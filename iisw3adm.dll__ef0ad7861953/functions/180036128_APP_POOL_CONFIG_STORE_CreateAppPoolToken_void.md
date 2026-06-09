# APP_POOL_CONFIG_STORE::CreateAppPoolToken(void)

- ea: `0x180036128`
- end: `0x1800362d2`
- name: `?CreateAppPoolToken@APP_POOL_CONFIG_STORE@@QEAAJXZ`
- size: `426`
- prototype: `__int64 __fastcall(APP_POOL_CONFIG_STORE *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017040`

## callees

- `0x180036128`
- `0x180037234`
- `0x180061060`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800361e9`
- `msvcrt!memcpy_s` at `0x1800361e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003617d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003617d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036202`
- `iisutil!PuDbgPrintError` at `0x1800361ca`
- `iisutil!PuDbgPrintError` at `0x1800361ca`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800362b2`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800362b2`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180036173`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180036173`
- `CRYPT32!CryptUnprotectMemory` at `0x1800361f8`
- `CRYPT32!CryptUnprotectMemory` at `0x1800361f8`

## string_xrefs

- `0x1800361bf`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool_config_store.cxx`
- `0x18003619f`: `Failed to allocate temporary buffer for password.\n`
- `0x1800361b3`: `APP_POOL_CONFIG_STORE::CreateAppPoolToken`

## pseudocode

```c

```
