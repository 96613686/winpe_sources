# WORKER_PROCESS::WorkerProcessRegistrationReceived(ulong)

- ea: `0x180028190`
- end: `0x1800284e5`
- name: `?WorkerProcessRegistrationReceived@WORKER_PROCESS@@AEAAXK@Z`
- size: `853`
- prototype: `void __fastcall(WORKER_PROCESS *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028930`

## callees

- `0x180012f30`
- `0x1800221a8`
- `0x180024d5c`
- `0x1800263a4`
- `0x1800265a0`
- `0x180027bf0`
- `0x180028190`
- `0x18002979c`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180028299`
- `iisutil!PuDbgPrint` at `0x1800282ed`
- `iisutil!PuDbgPrint` at `0x180028392`
- `iisutil!PuDbgPrint` at `0x180028299`
- `iisutil!PuDbgPrint` at `0x1800282ed`
- `iisutil!PuDbgPrint` at `0x180028392`
- `iisutil!PuDbgPrintError` at `0x1800281f3`
- `iisutil!PuDbgPrintError` at `0x18002833d`
- `iisutil!PuDbgPrintError` at `0x180028404`
- `iisutil!PuDbgPrintError` at `0x1800281f3`
- `iisutil!PuDbgPrintError` at `0x18002833d`
- `iisutil!PuDbgPrintError` at `0x180028404`

## string_xrefs

- `0x1800281c4`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x180028247`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x1800281d9`: `Received a new pid after the pid was already set for worker process (ptr: %p; pid: %lu; realpid: %lu)\n`
- `0x1800283e1`: `Sending anonymous token failed\n`
- `0x180028469`: `Sending thread affinity policy failed\n`

## pseudocode

```c

```
