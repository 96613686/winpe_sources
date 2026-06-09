# Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2::CompleteEventProcessing

- ea: `0x8a70`
- end: `0x8af3`
- name: `Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2::CompleteEventProcessing`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x8a70`
- `0xa140`
- `0xa3d0`
- `0x12110`
- `0x13010`
- `0x13480`
- `0x14940`
- `0x14bb0`

## pseudocode

```c

```

## disassembly

```asm
0x8a70  ldarg.0
0x8a71  ldc.i4.4
0x8a72  call     instance void class Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2<var<u1>, !!T0>::set_Status(valuetype Microsoft.Crm.Asynchronous.AsyncEventExecutionStatus)
0x8a77  ldarg.0
0x8a78  call     instance void class Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2<var<u1>, !!T0>::SetEndExecutionTime()
0x8a7d  ldarg.0
0x8a7e  ldfld    var<u1> class Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2<var<u1>, !!T0>::_queueManager
0x8a83  box      var<u1>
0x8a88  ldarg.0
0x8a89  callvirt instance void Microsoft.Crm.Asynchronous.QueueManager::TrackCompleteExecutingOperation(class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager asyncEventManager)
0x8a8e  ldarg.1
0x8a8f  brfalse.s loc_8A99
0x8a91  ldarg.1
0x8a92  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncHandlerResult::get_ThreadCompleted()
0x8a97  br.s     loc_8A9A
0x8a99  ldc.i4.0
0x8a9a  stloc.0
0x8a9b  ldarg.0
0x8a9c  ldfld    var<u1> class Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2<var<u1>, !!T0>::_queueManager
0x8aa1  box      var<u1>
0x8aa6  ldarg.0
0x8aa7  ldarg.1
0x8aa8  ldloc.0
0x8aa9  callvirt instance void Microsoft.Crm.Asynchronous.QueueManager::TrackCompleteOutstandingOperation(class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager asyncEventManager, class Microsoft.Crm.Asynchronous.AsyncHandlerResult result, bool startThread)
0x8aae  ldarg.0
0x8aaf  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryOperation class Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2<var<u1>, !!T0>::qualityOfServiceOperation
0x8ab4  brfalse.s loc_8AE7
0x8ab6  ldarg.0
0x8ab7  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryOperation class Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2<var<u1>, !!T0>::qualityOfServiceOperation
0x8abc  stloc.1
0x8abd  ldarg.1
0x8abe  newobj   instance void Microsoft.Crm.Asynchronous.ConstantFieldValueToFieldNameMapper::.ctor()
0x8ac3  newobj   instance void Microsoft.Crm.Asynchronous.JobResultCodeServiceLevelAgreementResultStrategy::.ctor(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult result, class Microsoft.Crm.Asynchronous.IConstantFieldValueToFieldNameMapper fieldValueToFieldNameMapper)
0x8ac8  stloc.2
0x8ac9  ldarg.0
0x8aca  ldfld    class Microsoft.Crm.Asynchronous.IAsyncServiceTelemetryFacade class Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2<var<u1>, !!T0>::asyncServiceTelemetryFacade
0x8acf  ldloc.2
0x8ad0  ldarg.0
0x8ad1  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryOperation class Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2<var<u1>, !!T0>::qualityOfServiceOperation
0x8ad6  callvirt instance void Microsoft.Crm.Asynchronous.IAsyncServiceTelemetryFacade::MarkTelemetryOperationResult(class Microsoft.Crm.Asynchronous.ITelemetryOperationResultStrategy resultStrategy, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryOperation operation)
0x8adb  leave.s  loc_8AE7
0x8add  ldloc.1
0x8ade  brfalse.s loc_8AE6
0x8ae0  ldloc.1
0x8ae1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ae6  endfinally
0x8ae7  ldarg.0
0x8ae8  call     instance class Microsoft.Crm.Asynchronous.IAsyncThrottleSubscriber class Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2<var<u1>, !!T0>::get_ThrottleSubscriber()
0x8aed  callvirt instance void Microsoft.Crm.Asynchronous.IAsyncThrottleSubscriber::ReleaseThrottle()
0x8af2  ret
```
