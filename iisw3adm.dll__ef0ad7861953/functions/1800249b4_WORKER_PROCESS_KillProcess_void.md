# WORKER_PROCESS::KillProcess(void)

- ea: `0x1800249b4`
- end: `0x180024b0a`
- name: `?KillProcess@WORKER_PROCESS@@AEAAXXZ`
- size: `342`
- prototype: `void __fastcall(WORKER_PROCESS *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027d04`

## callees

- `0x1800249b4`
- `0x180025dec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ab1`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180024aa7`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180024aa7`
- `iisutil!PuDbgPrint` at `0x180024a21`
- `iisutil!PuDbgPrint` at `0x180024a92`
- `iisutil!PuDbgPrint` at `0x180024a21`
- `iisutil!PuDbgPrint` at `0x180024a92`
- `iisutil!PuDbgPrintError` at `0x180024af7`
- `iisutil!PuDbgPrintError` at `0x180024af7`

## string_xrefs

- `0x1800249f8`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x180024a5c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x180024aec`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`

## pseudocode

```c

```
