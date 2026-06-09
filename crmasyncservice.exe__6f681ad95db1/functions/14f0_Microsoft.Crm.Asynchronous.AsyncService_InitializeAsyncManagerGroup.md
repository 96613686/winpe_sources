# Microsoft.Crm.Asynchronous.AsyncService::InitializeAsyncManagerGroup

- ea: `0x14f0`
- end: `0x1563`
- name: `Microsoft.Crm.Asynchronous.AsyncService::InitializeAsyncManagerGroup`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x13d0`

## callees

- `0xc0`
- `0x460`
- `0x1910`
- `0x4e90`
- `0x4ef0`
- `0x4ff0`

## pseudocode

```c

```

## disassembly

```asm
0x14f0  ldarg.0
0x14f1  newobj   instance void Microsoft.Crm.Asynchronous.AsyncHandlerHost::.ctor(class Microsoft.Crm.Asynchronous.AsyncService asyncService)
0x14f6  stloc.0
0x14f7  ldarg.0
0x14f8  ldarg.0
0x14f9  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServiceTelemetryFacade Microsoft.Crm.Asynchronous.AsyncService::telemetryFacade
0x14fe  newobj   instance void Microsoft.Crm.Asynchronous.AsyncManagerFactory::.ctor(class Microsoft.Crm.Asynchronous.AsyncService asyncService, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServiceTelemetryFacade asyncServiceTelemetryFacade)
0x1503  stloc.1
0x1504  ldarg.0
0x1505  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServicePeriodicWorker Microsoft.Crm.Asynchronous.AsyncService::heartbeatWorker
0x150a  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServicePeriodicWorker::Start()
0x150f  ldarg.0
0x1510  ldloc.1
0x1511  ldarg.0
0x1512  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncService::get_OperationsFactory()
0x1517  newobj   instance void Microsoft.Crm.Asynchronous.QueueManagerExecutionEngine::.ctor(class Microsoft.Crm.Asynchronous.IAsyncManagerFactory queueManagerFactory, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory operationsFactory)
0x151c  stfld    class Microsoft.Crm.Asynchronous.QueueManagerExecutionEngine Microsoft.Crm.Asynchronous.AsyncService::_asyncManagerGroup
0x1521  ldarg.0
0x1522  ldfld    class Microsoft.Crm.Asynchronous.QueueManagerExecutionEngine Microsoft.Crm.Asynchronous.AsyncService::_asyncManagerGroup
0x1527  ldloc.0
0x1528  ldftn    instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.AsyncHandlerHost::Handle(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager asyncEventManager)
0x152e  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandler::.ctor(object, native int)
0x1533  ldarg.0
0x1534  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServiceTelemetryFacade Microsoft.Crm.Asynchronous.AsyncService::telemetryFacade
0x1539  callvirt instance void Microsoft.Crm.Asynchronous.QueueManagerExecutionEngine::RegisterEventHandler(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandler handler, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServiceTelemetryFacade telemetryFacade)
0x153e  ldarg.0
0x153f  ldfld    class Microsoft.Crm.Asynchronous.QueueManagerExecutionEngine Microsoft.Crm.Asynchronous.AsyncService::_asyncManagerGroup
0x1544  ldarg.0
0x1545  ldftn    instance void Microsoft.Crm.Asynchronous.AsyncService::OnAsyncOperationStatusChanged(object sender, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationStatusChangedEventArgs e)
0x154b  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationStatusChangedEventArgs>::.ctor(object, native int)
0x1550  callvirt instance void Microsoft.Crm.Asynchronous.QueueManagerExecutionEngine::add_AsyncOperationStatusChanged(class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationStatusChangedEventArgs> value)
0x1555  ldarg.1
0x1556  ldloc.0
0x1557  call     T0x2B000005
0x155c  callvirt T0x2B000006
0x1561  pop
0x1562  ret
```
