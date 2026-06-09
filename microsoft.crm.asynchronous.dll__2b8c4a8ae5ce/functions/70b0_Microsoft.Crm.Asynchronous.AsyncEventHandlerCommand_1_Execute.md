# Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand`1::Execute

- ea: `0x70b0`
- end: `0x71e2`
- name: `Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand`1::Execute`
- size: `306`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x7040`
- `0x70b0`
- `0x121d0`
- `0x121e0`
- `0x121f0`
- `0x12200`
- `0x12980`
- `0x129d0`
- `0x12a40`

## string_xrefs

- `0x70ba`: `Executing AsyncOperationId: {0} AsyncOperationType: {1} Command: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x70b0  ldnull
0x70b1  stloc.0
0x70b2  ldarg.1
0x70b3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x70b8  ldc.i4.s 0x15
0x70ba  ldstr    aExecutingAsync// "Executing AsyncOperationId: {0} AsyncOp"...
0x70bf  ldc.i4.3
0x70c0  newarr   [mscorlib]System.Object
0x70c5  dup
0x70c6  ldc.i4.0
0x70c7  ldarg.1
0x70c8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x70cd  box      [mscorlib]System.Guid
0x70d2  stelem.ref
0x70d3  dup
0x70d4  ldc.i4.1
0x70d5  ldarg.1
0x70d6  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x70db  box      [mscorlib]System.Int32
0x70e0  stelem.ref
0x70e1  dup
0x70e2  ldc.i4.2
0x70e3  ldarg.0
0x70e4  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x70e9  callvirt instance string [mscorlib]System.Type::get_FullName()
0x70ee  stelem.ref
0x70ef  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x70f4  ldarg.1
0x70f5  isinst   var<u1>
0x70fa  unbox.any var<u1>
0x70ff  stloc.1
0x7100  ldloc.1
0x7101  box      var<u1>
0x7106  brtrue.s loc_7144
0x7108  ldc.i4   0x80044303
0x710d  ldstr    aTheAsyncOperat// "The async operation type '{0}' was not "...
0x7112  ldc.i4.2
0x7113  newarr   [mscorlib]System.Object
0x7118  dup
0x7119  ldc.i4.0
0x711a  ldarg.1
0x711b  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x7120  box      [mscorlib]System.Int32
0x7125  stelem.ref
0x7126  dup
0x7127  ldc.i4.1
0x7128  ldarg.0
0x7129  call     instance class Microsoft.Crm.Asynchronous.IAsyncService Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_AsyncService()
0x712e  callvirt instance valuetype Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.IAsyncService::get_Context()
0x7133  box      Microsoft.Crm.Asynchronous.AsyncServiceContext
0x7138  stelem.ref
0x7139  newobj   instance void Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(int32 errorCode, string errorFormat, object[] args)
0x713e  stloc.2
0x713f  leave    loc_71E0
0x7144  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager::get_Instance()
0x7149  ldarg.1
0x714a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_TelemetryActivityId()
0x714f  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryManager::set_CurrentThreadActivityId(valuetype [mscorlib]System.Guid)
0x7154  ldarg.1
0x7155  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x715a  ldarg.1
0x715b  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x7160  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DisableBackgroundProcessingUtility::ShouldSkipExecution(valuetype [mscorlib]System.Guid, int32)
0x7165  brfalse.s loc_717A
0x7167  ldarg.1
0x7168  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x716d  call     string class Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand`1<var<u1>>::GetAsyncOperationSkippedMessage(valuetype [mscorlib]System.Guid)
0x7172  newobj   instance void Microsoft.Crm.Asynchronous.AsyncSkippedResult::.ctor(string message)
0x7177  stloc.0
0x7178  br.s     loc_7182
0x717a  ldarg.0
0x717b  ldloc.1
0x717c  callvirt instance class Microsoft.Crm.Asynchronous.AsyncHandlerResult class Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand`1<var<u1>>::InternalExecute(var<u1>)
0x7181  stloc.0
0x7182  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager::get_Instance()
0x7187  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x718c  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryManager::set_CurrentThreadActivityId(valuetype [mscorlib]System.Guid)
0x7191  leave.s  loc_71DE
0x7193  stloc.3
0x7194  ldloc.3
0x7195  ldarg.1
0x7196  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x719b  ldc.i4.s 0x15
0x719d  ldstr    aExceptionWhile_0// "Exception while trying to execute Async"...
0x71a2  ldc.i4.3
0x71a3  newarr   [mscorlib]System.Object
0x71a8  dup
0x71a9  ldc.i4.0
0x71aa  ldarg.1
0x71ab  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x71b0  box      [mscorlib]System.Guid
0x71b5  stelem.ref
0x71b6  dup
0x71b7  ldc.i4.1
0x71b8  ldarg.1
0x71b9  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x71be  box      [mscorlib]System.Int32
0x71c3  stelem.ref
0x71c4  dup
0x71c5  ldc.i4.2
0x71c6  ldloc.3
0x71c7  stelem.ref
0x71c8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x71cd  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager::get_Instance()
0x71d2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x71d7  callvirt instance void [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryManager::set_CurrentThreadActivityId(valuetype [mscorlib]System.Guid)
0x71dc  rethrow
0x71de  ldloc.0
0x71df  ret
0x71e0  ldloc.2
0x71e1  ret
```
