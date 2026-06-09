# Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::UpdateLastRunConfigurationOnIdle

- ea: `0x630`
- end: `0x6d0`
- name: `Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::UpdateLastRunConfigurationOnIdle`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x50`

## callees

- `0x520`
- `0x630`
- `0x115b0`
- `0x116f0`

## string_xrefs

- `0x651`: `UpdateLastRunConfigurationOnIdle`
- `0x65c`: `AsyncHandler::ActionCardAsyncOperation::UpdateLastRunConfigurationOnIdle`
- `0x69f`: `AsyncHandler::ActionCardAsyncOperation::UpdateLastRunConfigurationOnIdle`
- `0x661`: `No action is performed from Action Card Async Operation, updated the last run configuration successfully.at UTC: {0}`
- `0x685`: `No action is performed from Action Card Async Operation, updated the last run configuration successfully.`
- `0x6a5`: `UpdateLastRunConfigurationOnIdle ActionCard Last Run Configuration could not complete.\n Error Details: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x630  ldarg.1
0x631  ldarg.0
0x632  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x637  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardHandler::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService, valuetype [mscorlib]System.Guid organizationId)
0x63c  ldarg.2
0x63d  callvirt instance class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardHandler::ParseLastRunConfig(string configData)
0x642  stloc.0
0x643  ldarg.0
0x644  ldloc.0
0x645  ldarg.1
0x646  call     instance void Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::UpdateLastRunConfiguration(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig runConfig, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService)
0x64b  ldarg.0
0x64c  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_cardsTrace
0x651  ldstr    aUpdatelastrunc_0// "UpdateLastRunConfigurationOnIdle"
0x656  ldarg.0
0x657  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x65c  ldstr    aAsynchandlerAc_2// "AsyncHandler::ActionCardAsyncOperation:"...
0x661  ldstr    aNoActionIsPerf// "No action is performed from Action Card"...
0x666  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x66b  box      [mscorlib]System.DateTime
0x670  call     string [mscorlib]System.String::Format(string, object)
0x675  ldsfld   string [mscorlib]System.String::Empty
0x67a  ldarg.0
0x67b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_ownerId
0x680  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardInformational(string, valuetype [mscorlib]System.Guid, string, string, string, valuetype [mscorlib]System.Guid)
0x685  ldstr    aNoActionIsPerf_0// "No action is performed from Action Card"...
0x68a  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor(string)
0x68f  stloc.1
0x690  leave.s  loc_6CE
0x692  stloc.2
0x693  ldarg.0
0x694  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_cardsTrace
0x699  ldarg.0
0x69a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x69f  ldstr    aAsynchandlerAc_2// "AsyncHandler::ActionCardAsyncOperation:"...
0x6a4  ldc.i4.3
0x6a5  ldstr    aUpdatelastrunc_1// "UpdateLastRunConfigurationOnIdle Action"...
0x6aa  ldloc.2
0x6ab  callvirt instance string [mscorlib]System.Object::ToString()
0x6b0  call     string [mscorlib]System.String::Format(string, object)
0x6b5  ldsfld   string [mscorlib]System.String::Empty
0x6ba  ldarg.0
0x6bb  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_ownerId
0x6c0  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardError(valuetype [mscorlib]System.Guid, string, int32, string, string, valuetype [mscorlib]System.Guid)
0x6c5  ldloc.2
0x6c6  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0x6cb  stloc.1
0x6cc  leave.s  loc_6CE
0x6ce  ldloc.1
0x6cf  ret
```
