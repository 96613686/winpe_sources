# Microsoft.Crm.Asynchronous.AsyncEventExceptionCounter::CreateRetryResultWithPostponeUntil

- ea: `0x2950`
- end: `0x2a2d`
- name: `Microsoft.Crm.Asynchronous.AsyncEventExceptionCounter::CreateRetryResultWithPostponeUntil`
- size: `221`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x2950`
- `0x2a30`
- `0x2a50`
- `0x2d60`
- `0x2da0`
- `0x59e0`
- `0x5f20`
- `0x5f40`
- `0x10900`
- `0x11400`
- `0x12c90`

## pseudocode

```c

```

## disassembly

```asm
0x2950  ldarg.3
0x2951  ldnull
0x2952  stind.ref
0x2953  ldarg.s  4
0x2955  ldnull
0x2956  stind.ref
0x2957  ldarg.1
0x2958  brfalse.s loc_2965
0x295a  ldarg.2
0x295b  brfalse.s loc_2965
0x295d  ldarg.1
0x295e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.AsyncEvent::get_OwningExtension()
0x2963  brtrue.s loc_2966
0x2965  ret
0x2966  ldarg.s  4
0x2968  ldc.i4.1
0x2969  ldc.i4   0x80060917
0x296e  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorAction::.ctor(valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorActionType, int32)
0x2973  stind.ref
0x2974  ldarg.s  4
0x2976  ldind.ref
0x2977  ldstr    aThisOperationH// "This operation has been postponed becau"...
0x297c  ldarg.0
0x297d  ldarg.1
0x297e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x2983  call     instance int32 Microsoft.Crm.Asynchronous.AsyncEventExceptionCounter::AsyncMaxExceptionCountInTimeUnit(valuetype [mscorlib]System.Guid organizationId)
0x2988  box      [mscorlib]System.Int32
0x298d  ldarg.0
0x298e  call     instance int32 Microsoft.Crm.Asynchronous.AsyncEventExceptionCounter::get_AsyncMaxExceptionCounterTimeUnitInMinutes()
0x2993  box      [mscorlib]System.Int32
0x2998  call     string [mscorlib]System.String::Format(string, object, object)
0x299d  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorAction::set_ErrorMessage(string)
0x29a2  ldarg.1
0x29a3  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEvent::get_RetryCount()
0x29a8  ldarg.2
0x29a9  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration::get_MaximumRetries()
0x29ae  bge.s    loc_29DB
0x29b0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x29b5  stloc.2
0x29b6  ldloca.s 2
0x29b8  ldarg.0
0x29b9  call     instance int32 Microsoft.Crm.Asynchronous.AsyncEventExceptionCounter::get_AsyncMaxExceptionCounterTimeUnitInMinutes()
0x29be  ldarg.1
0x29bf  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEvent::get_RetryCount()
0x29c4  ldc.i4.1
0x29c5  add
0x29c6  mul
0x29c7  conv.r8
0x29c8  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x29cd  stloc.1
0x29ce  ldarg.3
0x29cf  ldarg.s  4
0x29d1  ldind.ref
0x29d2  ldloc.1
0x29d3  newobj   instance void Microsoft.Crm.Asynchronous.AsyncRetryResultWithPostponeUntil::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorAction errorAction, valuetype [mscorlib]System.DateTime postponeUntil)
0x29d8  stind.ref
0x29d9  br.s     loc_29EC
0x29db  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_MaxValue()
0x29e0  stloc.3
0x29e1  ldarg.3
0x29e2  ldarg.s  4
0x29e4  ldind.ref
0x29e5  ldloc.3
0x29e6  newobj   instance void Microsoft.Crm.Asynchronous.AsyncRetryResultWithPostponeUntil::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorAction errorAction, valuetype [mscorlib]System.DateTime postponeUntil)
0x29eb  stind.ref
0x29ec  ldarg.1
0x29ed  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEvent::get_RetryCount()
0x29f2  ldarg.2
0x29f3  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration::get_MaximumRetries()
0x29f8  clt
0x29fa  ldc.i4.0
0x29fb  ceq
0x29fd  stloc.0
0x29fe  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x2a03  ldarg.1
0x2a04  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x2a09  ldarg.1
0x2a0a  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEvent::get_RetryCount()
0x2a0f  ldarg.0
0x2a10  call     instance int32 Microsoft.Crm.Asynchronous.AsyncEventExceptionCounter::get_AsyncMaxExceptionCounterTimeUnitInMinutes()
0x2a15  ldarg.1
0x2a16  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x2a1b  ldarg.1
0x2a1c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.AsyncEvent::get_OwningExtension()
0x2a21  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_Value()
0x2a26  ldloc.0
0x2a27  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncJobPostponedWithErrorCountCapReached(valuetype [mscorlib]System.Guid organizationId, int32 errorCount, int32 timeUnitInMinutes, int32 operationType, valuetype [mscorlib]System.Guid workflowId, bool isSuspended)
0x2a2c  ret
```
