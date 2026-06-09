# Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::UpdateLastRunConfiguration

- ea: `0x520`
- end: `0x62e`
- name: `Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::UpdateLastRunConfiguration`
- size: `270`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x150`
- `0x630`

## callees

- `0x520`
- `0x13760`
- `0x13770`
- `0x13790`

## string_xrefs

- `0x5b3`: `UpdateLastRunConfiguration`
- `0x5ee`: `UpdateLastRunConfiguration`
- `0x5be`: `AsyncHandler::ActionCardAsyncOperation::UpdateLastRunConfiguration`
- `0x5f9`: `AsyncHandler::ActionCardAsyncOperation::UpdateLastRunConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x520  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x525  stloc.2
0x526  ldloca.s 2
0x528  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x52d  ldarg.1
0x52e  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig::get_LastRunStartTime()
0x533  stloc.2
0x534  ldloca.s 2
0x536  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x53b  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x540  stloc.3
0x541  ldloca.s 3
0x543  call     instance float64 [mscorlib]System.TimeSpan::get_TotalDays()
0x548  stloc.0
0x549  ldarg.1
0x54a  ldarg.1
0x54b  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig::get_LastRunStartTime()
0x550  stloc.2
0x551  ldloca.s 2
0x553  ldloc.0
0x554  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x559  callvirt instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig::set_LastRunStartTime(valuetype [mscorlib]System.DateTime value)
0x55e  ldarg.1
0x55f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x564  callvirt instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig::set_LastRunEndTime(valuetype [mscorlib]System.DateTime value)
0x569  ldstr    aAsyncoperation// "asyncoperation"
0x56e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x573  stloc.1
0x574  ldloc.1
0x575  ldstr    aAsyncoperation_0// "asyncoperationid"
0x57a  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardConstants::ActionCardRecurringJobId
0x57f  box      [mscorlib]System.Guid
0x584  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x589  ldloc.1
0x58a  ldstr    aData// "data"
0x58f  ldarg.1
0x590  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0x595  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x59a  ldarg.2
0x59b  ldloc.1
0x59c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x5a1  ldloc.0
0x5a2  ldc.r8   1.0
0x5ab  ble.un.s loc_5E8
0x5ad  ldarg.0
0x5ae  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_cardsTrace
0x5b3  ldstr    aUpdatelastrunc// "UpdateLastRunConfiguration"
0x5b8  ldarg.0
0x5b9  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x5be  ldstr    aAsynchandlerAc_1// "AsyncHandler::ActionCardAsyncOperation:"...
0x5c3  ldstr    aTotalDaysQueri// "Total Days Queried in this run: {0} at "...
0x5c8  ldloc.0
0x5c9  box      [mscorlib]System.Double
0x5ce  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x5d3  box      [mscorlib]System.DateTime
0x5d8  call     string [mscorlib]System.String::Format(string, object, object)
0x5dd  ldarg.0
0x5de  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_ownerId
0x5e3  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardWarning(string, valuetype [mscorlib]System.Guid, string, string, valuetype [mscorlib]System.Guid)
0x5e8  ldarg.0
0x5e9  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_cardsTrace
0x5ee  ldstr    aUpdatelastrunc// "UpdateLastRunConfiguration"
0x5f3  ldarg.0
0x5f4  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x5f9  ldstr    aAsynchandlerAc_1// "AsyncHandler::ActionCardAsyncOperation:"...
0x5fe  ldstr    aSuccessfullyUp// "Successfully Upadated StartTime: {0} at"...
0x603  ldarg.1
0x604  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig::get_LastRunStartTime()
0x609  box      [mscorlib]System.DateTime
0x60e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x613  box      [mscorlib]System.DateTime
0x618  call     string [mscorlib]System.String::Format(string, object, object)
0x61d  ldsfld   string [mscorlib]System.String::Empty
0x622  ldarg.0
0x623  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_ownerId
0x628  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardInformational(string, valuetype [mscorlib]System.Guid, string, string, string, valuetype [mscorlib]System.Guid)
0x62d  ret
```
