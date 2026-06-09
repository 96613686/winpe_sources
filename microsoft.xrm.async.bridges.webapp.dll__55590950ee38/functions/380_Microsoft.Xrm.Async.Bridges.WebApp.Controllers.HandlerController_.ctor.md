# Microsoft.Xrm.Async.Bridges.WebApp.Controllers.HandlerController::.ctor

- ea: `0x380`
- end: `0x395`
- name: `Microsoft.Xrm.Async.Bridges.WebApp.Controllers.HandlerController::.ctor`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x380  ldarg.0
0x381  call     instance void [System.Web.Http]System.Web.Http.ApiController::.ctor()
0x386  ldarg.0
0x387  ldarg.1
0x388  stfld    class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerHost Microsoft.Xrm.Async.Bridges.WebApp.Controllers.HandlerController::asyncHandlerHost
0x38d  ldarg.0
0x38e  ldarg.2
0x38f  stfld    class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.IAsyncHandlerResultResponseMapper Microsoft.Xrm.Async.Bridges.WebApp.Controllers.HandlerController::responseMapper
0x394  ret
```
