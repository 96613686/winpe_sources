# WORKER_PROCESS::Initialize(REQUEST_QUEUE_DATA *)

- ea: `0x180023c8c`
- end: `0x18002415b`
- name: `?Initialize@WORKER_PROCESS@@QEAAXPEAVREQUEST_QUEUE_DATA@@@Z`
- size: `1231`
- prototype: `void __fastcall(WORKER_PROCESS *__hidden this, struct REQUEST_QUEUE_DATA *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017040`

## callees

- `0x180001234`
- `0x1800041f4`
- `0x180005878`
- `0x180023064`
- `0x180023268`
- `0x180023c8c`
- `0x180024d5c`
- `0x1800256ec`
- `0x180026da4`
- `0x180027008`
- `0x180029280`
- `0x18005f32c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180024075`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180024075`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180023feb`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180023feb`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180024021`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180024021`
- `iisutil!PuDbgPrint` at `0x180023cea`
- `iisutil!PuDbgPrint` at `0x180023eb2`
- `iisutil!PuDbgPrint` at `0x180023f6e`
- `iisutil!PuDbgPrint` at `0x18002405b`
- `iisutil!PuDbgPrint` at `0x180023cea`
- `iisutil!PuDbgPrint` at `0x180023eb2`
- `iisutil!PuDbgPrint` at `0x180023f6e`
- `iisutil!PuDbgPrint` at `0x18002405b`
- `iisutil!PuDbgPrintError` at `0x180023d99`
- `iisutil!PuDbgPrintError` at `0x180023fb2`
- `iisutil!PuDbgPrintError` at `0x180024106`
- `iisutil!PuDbgPrintError` at `0x180024138`
- `iisutil!PuDbgPrintError` at `0x180023d99`
- `iisutil!PuDbgPrintError` at `0x180023fb2`
- `iisutil!PuDbgPrintError` at `0x180024106`
- `iisutil!PuDbgPrintError` at `0x180024138`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180023e1c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180023e1c`
- `iisutil!?IsValid@CLKRHashTable@@QEBA_NXZ` at `0x180023cf7`
- `iisutil!?IsValid@CLKRHashTable@@QEBA_NXZ` at `0x180023cf7`

## string_xrefs

- `0x180023cad`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x180023d79`: `No configured identity to run worker process under.\n`
- `0x180023f0f`: `Failed to create a new request queue instance for the worker process\n`

## pseudocode

```c

```
