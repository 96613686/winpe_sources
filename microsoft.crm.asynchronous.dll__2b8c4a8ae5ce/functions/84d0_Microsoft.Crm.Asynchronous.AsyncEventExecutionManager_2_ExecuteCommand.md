# Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2::ExecuteCommand

- ea: `0x84d0`
- end: `0x8567`
- name: `Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2::ExecuteCommand`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x7030`
- `0x7080`
- `0x84d0`
- `0x121d0`
- `0x121e0`
- `0x121f0`
- `0x129b0`
- `0x12c50`

## string_xrefs

- `0x84e2`: `Command retrieval failed for OrgId={0} under ScalegroupId={1} while trying to process an event with the following AsyncOperationId={2} - Operation will be retried shortly. This occurs when the org could not be found in the org. cache`

## pseudocode

```c

```

## disassembly

```asm
0x84d0  ldnull
0x84d1  stloc.0
0x84d2  ldarg.0
0x84d3  ldarg.1
0x84d4  callvirt instance class Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand class Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2<var<u1>, !!T0>::CreateHandler(class Microsoft.Crm.Asynchronous.IAsyncEventHandlerFactory)
0x84d9  stloc.1
0x84da  ldloc.1
0x84db  brtrue.s loc_8551
0x84dd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x84e2  ldstr    aCommandRetriev// "Command retrieval failed for OrgId={0} "...
0x84e7  ldc.i4.3
0x84e8  newarr   [mscorlib]System.Object
0x84ed  dup
0x84ee  ldc.i4.0
0x84ef  ldarg.0
0x84f0  call     instance class Microsoft.Crm.Asynchronous.IAsyncEvent class Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2<var<u1>, !!T0>::get_AsyncEvent()
0x84f5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x84fa  box      [mscorlib]System.Guid
0x84ff  stelem.ref
0x8500  dup
0x8501  ldc.i4.1
0x8502  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0x8507  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0x850c  box      [mscorlib]System.Guid
0x8511  stelem.ref
0x8512  dup
0x8513  ldc.i4.2
0x8514  ldarg.0
0x8515  call     instance class Microsoft.Crm.Asynchronous.IAsyncEvent class Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2<var<u1>, !!T0>::get_AsyncEvent()
0x851a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x851f  box      [mscorlib]System.Guid
0x8524  stelem.ref
0x8525  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x852a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x852f  newobj   instance void Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception ex)
0x8534  stloc.2
0x8535  ldarg.0
0x8536  call     instance class Microsoft.Crm.Asynchronous.IAsyncEvent class Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2<var<u1>, !!T0>::get_AsyncEvent()
0x853b  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x8540  ldc.i4.s 0x1A
0x8542  bne.un.s loc_854D
0x8544  ldloc.2
0x8545  newobj   instance void Microsoft.Crm.Asynchronous.AsyncRetryResult::.ctor(class Microsoft.Crm.Asynchronous.AsyncFailedResult failure)
0x854a  stloc.0
0x854b  br.s     loc_8565
0x854d  ldloc.2
0x854e  stloc.0
0x854f  br.s     loc_8565
0x8551  ldloc.1
0x8552  ldarg.0
0x8553  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::set_ExecutionManager(class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager value)
0x8558  ldloc.1
0x8559  ldarg.0
0x855a  call     instance class Microsoft.Crm.Asynchronous.IAsyncEvent class Microsoft.Crm.Asynchronous.AsyncEventExecutionManager`2<var<u1>, !!T0>::get_AsyncEvent()
0x855f  callvirt instance class Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::Execute(class Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent)
0x8564  stloc.0
0x8565  ldloc.0
0x8566  ret
```
