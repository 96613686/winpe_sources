# WORK_QUEUE::Terminate(void)

- ea: `0x180007890`
- end: `0x180007a6c`
- name: `?Terminate@WORK_QUEUE@@QEAAXXZ`
- size: `476`
- prototype: `void __fastcall(WORK_QUEUE *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006880`
- `0x18002d250`
- `0x18003c6dc`

## callees

- `0x1800071d4`
- `0x1800073a0`
- `0x180007890`
- `0x180007af8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800078c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800078c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800078b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800078b0`
- `iisutil!PuDbgPrint` at `0x18000798a`
- `iisutil!PuDbgPrint` at `0x180007a58`
- `iisutil!PuDbgPrint` at `0x18000798a`
- `iisutil!PuDbgPrint` at `0x180007a58`
- `iisutil!PuDbgPrintError` at `0x18000791f`
- `iisutil!PuDbgPrintError` at `0x1800079be`
- `iisutil!PuDbgPrintError` at `0x180007a06`
- `iisutil!PuDbgPrintError` at `0x18000791f`
- `iisutil!PuDbgPrintError` at `0x1800079be`
- `iisutil!PuDbgPrintError` at `0x180007a06`

## string_xrefs

- `0x1800078d9`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\work_queue.cxx`

## pseudocode

```c

```
