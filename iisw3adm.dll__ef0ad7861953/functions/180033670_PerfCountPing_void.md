# PerfCountPing(void *)

- ea: `0x180033670`
- end: `0x1800337e4`
- name: `?PerfCountPing@@YAKPEAX@Z`
- size: `372`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800073fc`
- `0x180033670`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180033690`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180033690`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800336e7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800336e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800336fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800336fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800336ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033747`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800336ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033747`
- `iisutil!PuDbgPrint` at `0x1800336dd`
- `iisutil!PuDbgPrint` at `0x1800337ab`
- `iisutil!PuDbgPrint` at `0x1800336dd`
- `iisutil!PuDbgPrint` at `0x1800337ab`
- `iisutil!PuDbgPrintError` at `0x180033737`
- `iisutil!PuDbgPrintError` at `0x180033737`

## string_xrefs

- `0x180033799`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\perf_manager.cxx`
- `0x1800336c4`: `servercommon\inetsrv\iis\iisrearc\core\prfshmem\perf_sm.cxx`
- `0x18003372c`: `servercommon\inetsrv\iis\iisrearc\core\prfshmem\perf_sm.cxx`

## pseudocode

```c

```
