# Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::ExecuteLegacyHandler

- ea: `0x410`
- end: `0x51d`
- name: `Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::ExecuteLegacyHandler`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x50`

## callees

- `0x410`

## string_xrefs

- `0x497`: `Action card Async Legacy Operation could not complete because of {0} \n Error Details: {1}`
- `0x4dc`: `ExecuteLegacyHandlerCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x410  ldarg.0
0x411  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_cardsTrace
0x416  ldstr    aExecutelegacyh// "ExecuteLegacyHandlerStarted"
0x41b  ldarg.0
0x41c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x421  ldstr    aAsynchandlerEx_0// "AsyncHandler::ExecuteLegacyHandler"
0x426  ldstr    aStartedProcess_0// "Started processing the Action card Asyn"...
0x42b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x430  box      [mscorlib]System.DateTime
0x435  call     string [mscorlib]System.String::Format(string, object)
0x43a  ldsfld   string [mscorlib]System.String::Empty
0x43f  ldarg.0
0x440  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_ownerId
0x445  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardInformational(string, valuetype [mscorlib]System.Guid, string, string, string, valuetype [mscorlib]System.Guid)
0x44a  ldarg.0
0x44b  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x450  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x455  ldc.i4.0
0x456  ldc.i4.0
0x457  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x45c  stloc.0
0x45d  ldloc.0
0x45e  ldc.i4.0
0x45f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0x464  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.LetsGetStartedPlugin::.ctor()
0x469  ldarg.2
0x46a  ldloc.0
0x46b  ldarg.1
0x46c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_OwnerId()
0x471  ldarg.0
0x472  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x477  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.LetsGetStartedPlugin::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x47c  ldloc.0
0x47d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x482  leave.s  loc_4D6
0x484  stloc.1
0x485  ldarg.0
0x486  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_cardsTrace
0x48b  ldarg.0
0x48c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x491  ldstr    aAsynchandlerAc_0// "AsyncHandler::ActionCardAsyncOperation:"...
0x496  ldc.i4.3
0x497  ldstr    aActionCardAsyn_1// "Action card Async Legacy Operation coul"...
0x49c  ldloc.1
0x49d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4a2  ldloc.1
0x4a3  callvirt instance string [mscorlib]System.Object::ToString()
0x4a8  call     string [mscorlib]System.String::Format(string, object, object)
0x4ad  ldsfld   string [mscorlib]System.String::Empty
0x4b2  ldarg.0
0x4b3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_ownerId
0x4b8  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardError(valuetype [mscorlib]System.Guid, string, int32, string, string, valuetype [mscorlib]System.Guid)
0x4bd  ldloc.0
0x4be  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x4c3  ldloc.1
0x4c4  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0x4c9  stloc.2
0x4ca  leave.s  loc_51B
0x4cc  ldloc.0
0x4cd  brfalse.s loc_4D5
0x4cf  ldloc.0
0x4d0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d5  endfinally
0x4d6  ldarg.0
0x4d7  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_cardsTrace
0x4dc  ldstr    aExecutelegacyh_0// "ExecuteLegacyHandlerCompleted"
0x4e1  ldarg.0
0x4e2  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x4e7  ldstr    aAsynchandlerEx_0// "AsyncHandler::ExecuteLegacyHandler"
0x4ec  ldstr    aSuccessfullyEx// "Successfully executed Legacy Action Car"...
0x4f1  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4f6  box      [mscorlib]System.DateTime
0x4fb  call     string [mscorlib]System.String::Format(string, object)
0x500  ldsfld   string [mscorlib]System.String::Empty
0x505  ldarg.0
0x506  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_ownerId
0x50b  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardInformational(string, valuetype [mscorlib]System.Guid, string, string, string, valuetype [mscorlib]System.Guid)
0x510  ldstr    aSuccessfullyEx_0// "Successfully executed Legacy Action Car"...
0x515  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor(string)
0x51a  ret
0x51b  ldloc.2
0x51c  ret
```
