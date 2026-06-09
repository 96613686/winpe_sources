# PERF_MANAGER::Terminate(void)

- ea: `0x180034510`
- end: `0x18003466f`
- name: `?Terminate@PERF_MANAGER@@QEAAXXZ`
- size: `351`
- prototype: `void __fastcall(PERF_MANAGER *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006798`
- `0x18001cee8`

## callees

- `0x180004290`
- `0x1800058e4`
- `0x180032bd4`
- `0x180034510`
- `0x18005dd18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800345f3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800345f3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180034668`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180034605`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180034605`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003460f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003460f`
- `iisutil!PuDbgPrint` at `0x180034579`
- `iisutil!PuDbgPrint` at `0x180034579`
- `iisutil!PuDbgPrintError` at `0x1800345dc`
- `iisutil!PuDbgPrintError` at `0x1800345dc`

## string_xrefs

- `0x180034572`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\perf_manager.cxx`
- `0x1800345d5`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\perf_manager.cxx`

## pseudocode

```c

```
