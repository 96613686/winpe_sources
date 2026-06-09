# Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::PreponeRecurringSeriesExpansionJobNextRunDate

- ea: `0x4da0`
- end: `0x4f9c`
- name: `Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::PreponeRecurringSeriesExpansionJobNextRunDate`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x4ad0`

## callees

- `0x4da0`
- `0x5800`
- `0x59b0`
- `0x5b80`
- `0x5bb0`

## string_xrefs

- `0x4df2`: `AsyncHandler::RecurringSeriesExpansionOperation::PreponeRecurringSeriesExpansionJobNextRunDate() - Series with ActivityId {0} is already fully expanded.`

## pseudocode

```c

```

## disassembly

```asm
0x4da0  ldc.i4.3
0x4da1  newarr   [mscorlib]System.String
0x4da6  dup
0x4da7  ldc.i4.0
0x4da8  ldstr    aActivityid// "activityid"
0x4dad  stelem.ref
0x4dae  dup
0x4daf  ldc.i4.1
0x4db0  ldstr    aExpansionstate// "expansionstatecode"
0x4db5  stelem.ref
0x4db6  dup
0x4db7  ldc.i4.2
0x4db8  ldstr    aNextexpansioni// "nextexpansioninstancedate"
0x4dbd  stelem.ref
0x4dbe  stloc.0
0x4dbf  ldarg.0
0x4dc0  ldstr    aRecurringappoi// "recurringappointmentmaster"
0x4dc5  ldarg.1
0x4dc6  ldloc.0
0x4dc7  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, string[] columnSetAttributes)
0x4dcc  stloc.1
0x4dcd  ldloc.1
0x4dce  ldstr    aExpansionstate// "expansionstatecode"
0x4dd3  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x4dd8  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x4ddd  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x4de2  ldc.i4.2
0x4de3  bne.un.s loc_4E10
0x4de5  ldarg.0
0x4de6  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x4deb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x4df0  ldc.i4.s 0x15
0x4df2  ldstr    aAsynchandlerRe// "AsyncHandler::RecurringSeriesExpansionO"...
0x4df7  ldc.i4.1
0x4df8  newarr   [mscorlib]System.Object
0x4dfd  dup
0x4dfe  ldc.i4.0
0x4dff  ldarg.1
0x4e00  box      [mscorlib]System.Guid
0x4e05  stelem.ref
0x4e06  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4e0b  leave    loc_4F9B
0x4e10  ldloc.1
0x4e11  ldstr    aNextexpansioni// "nextexpansioninstancedate"
0x4e16  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x4e1b  brtrue.s loc_4E48
0x4e1d  ldarg.0
0x4e1e  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x4e23  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x4e28  ldc.i4.s 0x15
0x4e2a  ldstr    aAsynchandlerRe_0// "AsyncHandler::RecurringSeriesExpansionO"...
0x4e2f  ldc.i4.1
0x4e30  newarr   [mscorlib]System.Object
0x4e35  dup
0x4e36  ldc.i4.0
0x4e37  ldarg.1
0x4e38  box      [mscorlib]System.Guid
0x4e3d  stelem.ref
0x4e3e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4e43  leave    loc_4F9B
0x4e48  ldarg.0
0x4e49  ldloc.1
0x4e4a  ldstr    aNextexpansioni// "nextexpansioninstancedate"
0x4e4f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x4e54  unbox.any [mscorlib]System.DateTime
0x4e59  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::GetUniversalDateTime(valuetype [mscorlib]System.DateTime dt)
0x4e5e  stloc.2
0x4e5f  ldloc.2
0x4e60  ldarg.0
0x4e61  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_futureCutOffDate
0x4e66  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x4e6b  brfalse.s loc_4EB8
0x4e6d  ldloca.s 2
0x4e6f  ldarg.0
0x4e70  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_futureCutOffDate
0x4e75  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0x4e7a  stloc.3
0x4e7b  ldloca.s 3
0x4e7d  call     instance int32 [mscorlib]System.TimeSpan::get_Days()
0x4e82  ldarg.0
0x4e83  ldfld    int32 Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_expansionFreqInDays
0x4e88  blt.s    loc_4E93
0x4e8a  ldloca.s 3
0x4e8c  call     instance int32 [mscorlib]System.TimeSpan::get_Days()
0x4e91  br.s     loc_4E99
0x4e93  ldarg.0
0x4e94  ldfld    int32 Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_expansionFreqInDays
0x4e99  stloc.s  4
0x4e9b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4ea0  stloc.s  5
0x4ea2  ldloca.s 5
0x4ea4  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x4ea9  stloc.s  5
0x4eab  ldloca.s 5
0x4ead  ldloc.s  4
0x4eaf  conv.r8
0x4eb0  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x4eb5  stloc.2
0x4eb6  br.s     loc_4F14
0x4eb8  ldarg.0
0x4eb9  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x4ebe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x4ec3  ldc.i4.s 0x15
0x4ec5  ldstr    aAsynchandlerRe_1// "AsyncHandler::RecurringSeriesExpansionO"...
0x4eca  ldc.i4.3
0x4ecb  newarr   [mscorlib]System.Object
0x4ed0  dup
0x4ed1  ldc.i4.0
0x4ed2  ldarg.1
0x4ed3  box      [mscorlib]System.Guid
0x4ed8  stelem.ref
0x4ed9  dup
0x4eda  ldc.i4.1
0x4edb  ldloc.2
0x4edc  box      [mscorlib]System.DateTime
0x4ee1  stelem.ref
0x4ee2  dup
0x4ee3  ldc.i4.2
0x4ee4  ldarg.0
0x4ee5  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_futureCutOffDate
0x4eea  box      [mscorlib]System.DateTime
0x4eef  stelem.ref
0x4ef0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4ef5  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4efa  stloc.s  5
0x4efc  ldloca.s 5
0x4efe  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x4f03  stloc.s  5
0x4f05  ldloca.s 5
0x4f07  ldarg.0
0x4f08  ldfld    int32 Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_expansionFreqInDays
0x4f0d  conv.r8
0x4f0e  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x4f13  stloc.2
0x4f14  ldarg.0
0x4f15  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_orgConfig
0x4f1a  ldarg.0
0x4f1b  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_crmService
0x4f20  newobj   instance void Microsoft.Crm.Asynchronous.RecurringSeriesExpansionDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService)
0x4f25  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::recurringSeriesExpansionId
0x4f2a  ldloc.2
0x4f2b  ldc.i4.1
0x4f2c  callvirt instance void Microsoft.Crm.Asynchronous.RecurringSeriesExpansionDataAccess::PostponeOrPreponeRecurringSeriesExpansionJob(valuetype [mscorlib]System.Guid jobId, valuetype [mscorlib]System.DateTime postPoneUntil, bool isPrepone)
0x4f31  leave.s  loc_4F9B
0x4f33  stloc.s  6
0x4f35  ldarg.0
0x4f36  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x4f3b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x4f40  ldc.i4.s 0x15
0x4f42  ldstr    aErrorInAsyncha_0// "Error in AsyncHandler::RecurringSeriesE"...
0x4f47  ldc.i4.2
0x4f48  newarr   [mscorlib]System.Object
0x4f4d  dup
0x4f4e  ldc.i4.0
0x4f4f  ldarg.1
0x4f50  box      [mscorlib]System.Guid
0x4f55  stelem.ref
0x4f56  dup
0x4f57  ldc.i4.1
0x4f58  ldloc.s  6
0x4f5a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x4f5f  stelem.ref
0x4f60  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4f65  leave.s  loc_4F9B
0x4f67  stloc.s  7
0x4f69  ldarg.0
0x4f6a  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x4f6f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x4f74  ldc.i4.s 0x15
0x4f76  ldstr    aErrorInAsyncha_0// "Error in AsyncHandler::RecurringSeriesE"...
0x4f7b  ldc.i4.2
0x4f7c  newarr   [mscorlib]System.Object
0x4f81  dup
0x4f82  ldc.i4.0
0x4f83  ldarg.1
0x4f84  box      [mscorlib]System.Guid
0x4f89  stelem.ref
0x4f8a  dup
0x4f8b  ldc.i4.1
0x4f8c  ldloc.s  7
0x4f8e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x4f93  stelem.ref
0x4f94  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4f99  leave.s  loc_4F9B
0x4f9b  ret
```
