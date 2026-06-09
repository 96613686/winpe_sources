# Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::InternalExecute

- ea: `0x48b0`
- end: `0x4aa6`
- name: `Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::InternalExecute`
- size: `502`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x48b0`
- `0x4ad0`
- `0x5810`
- `0x5870`

## string_xrefs

- `0x4a01`: `Async Handler for Recurring Series Expansion Operation could not complete because of exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x48b0  ldarg.1
0x48b1  ldstr    aAsyncevent// "asyncEvent"
0x48b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x48bb  ldarg.1
0x48bc  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x48c1  ldc.i4.s 0x23
0x48c3  ceq
0x48c5  ldstr    aOperationTypeM_3// "Operation type must be 'RecurringSeries"...
0x48ca  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x48cf  ldarg.0
0x48d0  ldarg.1
0x48d1  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x48d6  ldarg.0
0x48d7  ldarg.1
0x48d8  ldc.i4.0
0x48d9  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent, bool)
0x48de  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_crmService
0x48e3  ldarg.0
0x48e4  ldarg.0
0x48e5  ldflda   int32 Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_futureCutOffMonths
0x48ea  ldarg.0
0x48eb  ldflda   int32 Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_expandNextChunkSize
0x48f0  ldarg.0
0x48f1  ldflda   int32 Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_onDemandExpansionJobBatchInterval
0x48f6  ldarg.0
0x48f7  ldflda   int32 Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_onDemandExpansionJobBatchSize
0x48fc  call     instance void Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::LoadPartialExpansionSettings([out] int32& futureCutOffMonths, [out] int32& expandNextChunkSize, [out] int32& onDemandExpansionJobBatchInterval, [out] int32& onDemandExpansionJobBatchSize)
0x4901  ldarg.0
0x4902  ldarg.0
0x4903  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::recurringSeriesExpansionId
0x4908  call     instance int32 Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::GetSeriesExpansionFreqInDays(valuetype [mscorlib]System.Guid jobId)
0x490d  stfld    int32 Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_expansionFreqInDays
0x4912  ldarg.0
0x4913  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4918  stloc.1
0x4919  ldloca.s 1
0x491b  ldarg.0
0x491c  ldfld    int32 Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_futureCutOffMonths
0x4921  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMonths(int32)
0x4926  stloc.1
0x4927  ldloca.s 1
0x4929  ldarg.0
0x492a  ldfld    int32 Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_expansionFreqInDays
0x492f  conv.r8
0x4930  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x4935  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_futureCutOffDate
0x493a  ldarg.0
0x493b  ldc.i4.0
0x493c  stfld    bool Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_errorOccurred
0x4941  ldc.i4.0
0x4942  stloc.0
0x4943  ldarg.0
0x4944  call     instance valuetype RecurringSeriesExpansionResult Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::DoRecurringSeriesExpansionOperation()
0x4949  stloc.0
0x494a  ldarg.0
0x494b  ldfld    bool Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_errorOccurred
0x4950  brfalse.s loc_495D
0x4952  ldstr    aAsyncHandlerFo// "Async Handler for Recurring Series Expa"...
0x4957  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x495c  throw
0x495d  leave    loc_4A1C
0x4962  stloc.2
0x4963  ldarg.0
0x4964  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x4969  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_OrganizationConfiguration()
0x496e  stloc.3
0x496f  ldstr    aMscrmplatform// "MSCRMPlatform"
0x4974  ldc.i4   0xC0004410
0x4979  conv.u8
0x497a  ldc.i4.6
0x497b  newarr   [mscorlib]System.String
0x4980  dup
0x4981  ldc.i4.0
0x4982  call     string [mscorlib]System.Environment::get_MachineName()
0x4987  stelem.ref
0x4988  dup
0x4989  ldc.i4.1
0x498a  ldarg.0
0x498b  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x4990  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x4995  stloc.s  4
0x4997  ldloca.s 4
0x4999  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x499e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x49a3  stelem.ref
0x49a4  dup
0x49a5  ldc.i4.2
0x49a6  ldarg.0
0x49a7  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x49ac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x49b1  stloc.s  5
0x49b3  ldloca.s 5
0x49b5  constrained. [mscorlib]System.Guid
0x49bb  callvirt instance string [mscorlib]System.Object::ToString()
0x49c0  stelem.ref
0x49c1  dup
0x49c2  ldc.i4.3
0x49c3  ldloc.3
0x49c4  callvirt instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationName()
0x49c9  stelem.ref
0x49ca  dup
0x49cb  ldc.i4.4
0x49cc  ldc.i4   0x80040216
0x49d1  stloc.s  4
0x49d3  ldloca.s 4
0x49d5  ldstr    aX// "x"
0x49da  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x49df  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x49e4  stelem.ref
0x49e5  dup
0x49e6  ldc.i4.5
0x49e7  ldloc.2
0x49e8  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x49ed  stelem.ref
0x49ee  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::WriteEventError(string, int64, string[])
0x49f3  ldloc.2
0x49f4  ldarg.0
0x49f5  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x49fa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x49ff  ldc.i4.s 0x15
0x4a01  ldstr    aAsyncHandlerFo_0// "Async Handler for Recurring Series Expa"...
0x4a06  ldc.i4.1
0x4a07  newarr   [mscorlib]System.Object
0x4a0c  dup
0x4a0d  ldc.i4.0
0x4a0e  ldloc.2
0x4a0f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x4a14  stelem.ref
0x4a15  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4a1a  rethrow
0x4a1c  ldarg.0
0x4a1d  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x4a22  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::QueryForEarlyExitRequest()
0x4a27  stloc.s  6
0x4a29  ldloc.s  6
0x4a2b  ldc.i4.1
0x4a2c  beq.s    loc_4A35
0x4a2e  ldloc.s  6
0x4a30  ldc.i4.2
0x4a31  beq.s    loc_4A3B
0x4a33  br.s     loc_4A41
0x4a35  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncPausedResult::.ctor()
0x4a3a  ret
0x4a3b  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncCanceledResult::.ctor()
0x4a40  ret
0x4a41  ldloc.0
0x4a42  ldc.i4.2
0x4a43  bne.un.s loc_4A9D
0x4a45  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4a4a  stloc.1
0x4a4b  ldloca.s 1
0x4a4d  ldarg.0
0x4a4e  ldfld    int32 Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_onDemandExpansionJobBatchInterval
0x4a53  conv.r8
0x4a54  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddSeconds(float64)
0x4a59  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncPausedResult::.ctor(valuetype [mscorlib]System.DateTime)
0x4a5e  stloc.s  7
0x4a60  leave.s  loc_4AA3
0x4a62  stloc.s  8
0x4a64  ldloc.s  8
0x4a66  ldarg.0
0x4a67  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x4a6c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x4a71  ldc.i4.s 0x15
0x4a73  ldstr    aValueOfOndeman// "Value of OnDemandExpansionJobBatchInter"...
0x4a78  ldc.i4.2
0x4a79  newarr   [mscorlib]System.Object
0x4a7e  dup
0x4a7f  ldc.i4.0
0x4a80  ldarg.0
0x4a81  ldfld    int32 Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_onDemandExpansionJobBatchInterval
0x4a86  box      [mscorlib]System.Int32
0x4a8b  stelem.ref
0x4a8c  dup
0x4a8d  ldc.i4.1
0x4a8e  ldloc.s  8
0x4a90  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x4a95  stelem.ref
0x4a96  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4a9b  leave.s  loc_4A9D
0x4a9d  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0x4aa2  ret
0x4aa3  ldloc.s  7
0x4aa5  ret
```
