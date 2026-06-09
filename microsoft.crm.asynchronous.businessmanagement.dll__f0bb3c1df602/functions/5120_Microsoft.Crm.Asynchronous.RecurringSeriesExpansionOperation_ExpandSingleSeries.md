# Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::ExpandSingleSeries

- ea: `0x5120`
- end: `0x5765`
- name: `Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::ExpandSingleSeries`
- size: `1605`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x4ad0`
- `0x4b30`

## callees

- `0x4ab0`
- `0x5120`
- `0x5800`
- `0x59b0`

## string_xrefs

- `0x512f`: `seriesId must not be null.`
- `0x5144`: `seriesId must not be empty.`
- `0x51b3`: `AsyncHandler::RecurringSeriesExpansionOperation::ExpandSingleSeries() - Series with ActivityId {0} is Deleted. - Detail: {1}`
- `0x51ed`: `AsyncHandler::RecurringSeriesExpansionOperation::ExpandSingleSeries() - Series with ActivityId {0} is Deleted. - Detail: {1}`
- `0x5455`: `Total record created: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5120  ldc.i4.1
0x5121  stloc.0
0x5122  ldnull
0x5123  stloc.1
0x5124  ldarg.0
0x5125  call     instance bool Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::HasJobBeenAbortedOrPaused()
0x512a  brfalse.s loc_512E
0x512c  ldloc.0
0x512d  ret
0x512e  ldc.i4.1
0x512f  ldstr    aSeriesidMustNo// "seriesId must not be null."
0x5134  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x5139  ldarg.1
0x513a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x513f  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5144  ldstr    aSeriesidMustNo_0// "seriesId must not be empty."
0x5149  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x514e  ldnull
0x514f  stloc.2
0x5150  ldc.i4.7
0x5151  newarr   [mscorlib]System.String
0x5156  dup
0x5157  ldc.i4.0
0x5158  ldstr    aActivityid// "activityid"
0x515d  stelem.ref
0x515e  dup
0x515f  ldc.i4.1
0x5160  ldstr    aStatecode// "statecode"
0x5165  stelem.ref
0x5166  dup
0x5167  ldc.i4.2
0x5168  ldstr    aSeriesstatus// "seriesstatus"
0x516d  stelem.ref
0x516e  dup
0x516f  ldc.i4.3
0x5170  ldstr    aExpansionstate// "expansionstatecode"
0x5175  stelem.ref
0x5176  dup
0x5177  ldc.i4.4
0x5178  ldstr    aNextexpansioni// "nextexpansioninstancedate"
0x517d  stelem.ref
0x517e  dup
0x517f  ldc.i4.5
0x5180  ldstr    aInstancetypeco// "instancetypecode"
0x5185  stelem.ref
0x5186  dup
0x5187  ldc.i4.6
0x5188  ldstr    aOwnerid// "ownerid"
0x518d  stelem.ref
0x518e  stloc.s  6
0x5190  ldarg.0
0x5191  ldstr    aRecurringappoi// "recurringappointmentmaster"
0x5196  ldarg.1
0x5197  ldloc.s  6
0x5199  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, string[] columnSetAttributes)
0x519e  stloc.2
0x519f  leave    loc_5252
0x51a4  stloc.s  7
0x51a6  ldarg.0
0x51a7  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x51ac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x51b1  ldc.i4.s 0x15
0x51b3  ldstr    aAsynchandlerRe_2// "AsyncHandler::RecurringSeriesExpansionO"...
0x51b8  ldc.i4.2
0x51b9  newarr   [mscorlib]System.Object
0x51be  dup
0x51bf  ldc.i4.0
0x51c0  ldarg.1
0x51c1  box      [mscorlib]System.Guid
0x51c6  stelem.ref
0x51c7  dup
0x51c8  ldc.i4.1
0x51c9  ldloc.s  7
0x51cb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x51d0  stelem.ref
0x51d1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x51d6  ldloc.0
0x51d7  stloc.s  8
0x51d9  leave    loc_5762
0x51de  stloc.s  9
0x51e0  ldarg.0
0x51e1  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x51e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x51eb  ldc.i4.s 0x15
0x51ed  ldstr    aAsynchandlerRe_2// "AsyncHandler::RecurringSeriesExpansionO"...
0x51f2  ldc.i4.2
0x51f3  newarr   [mscorlib]System.Object
0x51f8  dup
0x51f9  ldc.i4.0
0x51fa  ldarg.1
0x51fb  box      [mscorlib]System.Guid
0x5200  stelem.ref
0x5201  dup
0x5202  ldc.i4.1
0x5203  ldloc.s  9
0x5205  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x520a  stelem.ref
0x520b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5210  ldloc.0
0x5211  stloc.s  8
0x5213  leave    loc_5762
0x5218  stloc.s  0xA
0x521a  ldarg.0
0x521b  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x5220  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x5225  ldc.i4.s 0x15
0x5227  ldstr    aAsynchandlerRe_3// "AsyncHandler::RecurringSeriesExpansionO"...
0x522c  ldc.i4.2
0x522d  newarr   [mscorlib]System.Object
0x5232  dup
0x5233  ldc.i4.0
0x5234  ldarg.1
0x5235  box      [mscorlib]System.Guid
0x523a  stelem.ref
0x523b  dup
0x523c  ldc.i4.1
0x523d  ldloc.s  0xA
0x523f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x5244  stelem.ref
0x5245  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x524a  ldloc.0
0x524b  stloc.s  8
0x524d  leave    loc_5762
0x5252  ldloc.2
0x5253  ldnull
0x5254  cgt.un
0x5256  ldstr    aMasterapptMust// "masterAppt must not be null."
0x525b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x5260  ldloc.2
0x5261  ldstr    aInstancetypeco// "instancetypecode"
0x5266  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x526b  brfalse.s loc_5285
0x526d  ldloc.2
0x526e  ldstr    aInstancetypeco// "instancetypecode"
0x5273  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x5278  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x527d  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x5282  ldc.i4.1
0x5283  beq.s    loc_5287
0x5285  ldloc.0
0x5286  ret
0x5287  ldloc.2
0x5288  ldstr    aStatecode// "statecode"
0x528d  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x5292  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x5297  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x529c  stloc.3
0x529d  ldloc.3
0x529e  brfalse.s loc_52A6
0x52a0  ldloc.3
0x52a1  ldc.i4.3
0x52a2  beq.s    loc_52A6
0x52a4  ldloc.0
0x52a5  ret
0x52a6  ldloc.2
0x52a7  ldstr    aSeriesstatus// "seriesstatus"
0x52ac  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x52b1  unbox.any [mscorlib]System.Boolean
0x52b6  brtrue.s loc_52BA
0x52b8  ldloc.0
0x52b9  ret
0x52ba  ldloc.2
0x52bb  ldstr    aExpansionstate// "expansionstatecode"
0x52c0  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x52c5  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x52ca  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x52cf  ldc.i4.2
0x52d0  bne.un.s loc_52D4
0x52d2  ldloc.0
0x52d3  ret
0x52d4  ldloc.2
0x52d5  ldstr    aNextexpansioni// "nextexpansioninstancedate"
0x52da  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x52df  brfalse.s loc_5306
0x52e1  ldarg.0
0x52e2  ldloc.2
0x52e3  ldstr    aNextexpansioni// "nextexpansioninstancedate"
0x52e8  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x52ed  unbox.any [mscorlib]System.DateTime
0x52f2  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::GetUniversalDateTime(valuetype [mscorlib]System.DateTime dt)
0x52f7  ldarg.0
0x52f8  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_futureCutOffDate
0x52fd  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5302  brfalse.s loc_5306
0x5304  ldloc.0
0x5305  ret
0x5306  ldarg.0
0x5307  call     instance bool Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::HasJobBeenAbortedOrPaused()
0x530c  brfalse.s loc_5310
0x530e  ldloc.0
0x530f  ret
0x5310  ldloc.2
0x5311  ldstr    aOwnerid// "ownerid"
0x5316  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x531b  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x5320  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x5325  ldstr    aTeam// "team"
0x532a  callvirt instance bool [mscorlib]System.String::Equals(string)
0x532f  brfalse.s loc_538E
0x5331  ldc.i4.1
0x5332  newarr   [mscorlib]System.String
0x5337  dup
0x5338  ldc.i4.0
0x5339  ldstr    aAdministratori// "administratorid"
0x533e  stelem.ref
0x533f  stloc.s  0xB
0x5341  ldarg.0
0x5342  ldstr    aTeam// "team"
0x5347  ldloc.2
0x5348  ldstr    aOwnerid// "ownerid"
0x534d  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x5352  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x5357  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x535c  ldloc.s  0xB
0x535e  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, string[] columnSetAttributes)
0x5363  stloc.s  0xC
0x5365  ldarg.0
0x5366  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x536b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x5370  ldloc.s  0xC
0x5372  ldstr    aAdministratori// "administratorid"
0x5377  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x537c  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x5381  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x5386  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x538b  stloc.1
0x538c  br.s     loc_53B4
0x538e  ldarg.0
0x538f  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x5394  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x5399  ldloc.2
0x539a  ldstr    aOwnerid// "ownerid"
0x539f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x53a4  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x53a9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x53ae  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x53b3  stloc.1
0x53b4  ldarg.0
0x53b5  call     instance bool Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::HasJobBeenAbortedOrPaused()
0x53ba  brfalse.s loc_53BE
0x53bc  ldloc.0
0x53bd  ret
0x53be  ldc.i4.0
0x53bf  stloc.s  4
0x53c1  ldc.i4.0
0x53c2  stloc.s  5
0x53c4  nop
0x53c5  ldarg.0
0x53c6  call     instance bool Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::HasJobBeenAbortedOrPaused()
0x53cb  brfalse.s loc_53D5
0x53cd  ldloc.0
0x53ce  stloc.s  8
0x53d0  leave    loc_5762
0x53d5  ldstr    aRecurringappoi// "recurringappointmentmaster"
0x53da  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x53df  stloc.s  0xD
0x53e1  ldloc.s  0xD
0x53e3  ldstr    aActivityid// "activityid"
0x53e8  ldarg.1
0x53e9  box      [mscorlib]System.Guid
0x53ee  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x53f3  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateInstanceRequest::.ctor()
0x53f8  stloc.s  0xE
0x53fa  ldloc.s  0xE
0x53fc  ldloc.s  0xD
0x53fe  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateInstanceRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x5403  ldloc.s  0xE
0x5405  ldarg.0
0x5406  ldfld    int32 Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_expandNextChunkSize
0x540b  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateInstanceRequest::set_Count(int32)
0x5410  ldarg.2
0x5411  brfalse.s loc_543C
0x5413  ldarg.0
0x5414  ldfld    int32 Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_onDemandExpansionJobBatchSize
0x5419  brfalse.s loc_543C
0x541b  ldloc.s  5
0x541d  ldarg.0
0x541e  ldfld    int32 Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_expandNextChunkSize
0x5423  add
0x5424  ldarg.0
0x5425  ldfld    int32 Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_onDemandExpansionJobBatchSize
0x542a  ble.s    loc_543C
0x542c  ldloc.s  0xE
0x542e  ldarg.0
0x542f  ldfld    int32 Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_onDemandExpansionJobBatchSize
0x5434  ldloc.s  5
0x5436  sub
0x5437  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateInstanceRequest::set_Count(int32)
0x543c  ldloc.s  5
0x543e  ldloc.s  0xE
0x5440  callvirt instance int32 [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CreateInstanceRequest::get_Count()
0x5445  add
0x5446  stloc.s  5
0x5448  ldarg.0
0x5449  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x544e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x5453  ldc.i4.s 0x15
0x5455  ldstr    aTotalRecordCre// "Total record created: {0}"
0x545a  ldc.i4.1
0x545b  newarr   [mscorlib]System.Object
  ... truncated ...
```
