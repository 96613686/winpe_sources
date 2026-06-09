# Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::InternalExecute

- ea: `0x50`
- end: `0x145`
- name: `Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::InternalExecute`
- size: `245`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x50`
- `0x150`
- `0x410`
- `0x630`
- `0x6d0`

## string_xrefs

- `0x11a`: `Action card Async Operation could not complete. \n Error Details: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x50  ldarg.1
0x51  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x56  ldc.i4.s 0x45
0x58  ceq
0x5a  ldstr    aOperationTypeM// "Operation type must be 'ActionCardAsync"...
0x5f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x64  ldarg.1
0x65  ldc.i4.1
0x66  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent, bool)
0x6b  stloc.0
0x6c  ldarg.1
0x6d  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0x72  stloc.1
0x73  ldarg.0
0x74  ldarg.1
0x75  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_OwnerId()
0x7a  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_ownerId
0x7f  ldarg.0
0x80  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x85  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.SolutionHelper::IsCRMOrg(valuetype [mscorlib]System.Guid)
0x8a  brtrue.s loc_C4
0x8c  ldarg.0
0x8d  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_cardsTrace
0x92  ldstr    aInternalexecut// "InternalExecute"
0x97  ldarg.0
0x98  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x9d  ldstr    aAsynchandlerIn// "AsyncHandler::InternalExecute"
0xa2  ldstr    aNotACoreCrmOrg// "Not a Core CRM org"
0xa7  ldsfld   string [mscorlib]System.String::Empty
0xac  ldarg.0
0xad  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_ownerId
0xb2  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardInformational(string, valuetype [mscorlib]System.Guid, string, string, string, valuetype [mscorlib]System.Guid)
0xb7  ldstr    aNoActionCanBeP// "No action Can be  performed from Action"...
0xbc  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor(string)
0xc1  stloc.2
0xc2  leave.s  loc_143
0xc4  ldloc.1
0xc5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xca  brtrue.s loc_E9
0xcc  ldloc.1
0xcd  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0xd2  ldstr    aLegacyactionca// "legacyactioncards"
0xd7  callvirt instance bool [mscorlib]System.String::Equals(string)
0xdc  brfalse.s loc_E9
0xde  ldarg.0
0xdf  ldarg.1
0xe0  ldloc.0
0xe1  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::ExecuteLegacyHandler(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService)
0xe6  stloc.2
0xe7  leave.s  loc_143
0xe9  ldarg.0
0xea  call     instance bool Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::IsActionCardAsyncFeatureEnabled()
0xef  brfalse.s loc_FC
0xf1  ldarg.0
0xf2  ldloc.0
0xf3  ldloc.1
0xf4  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::ExecuteActionCardHandlers(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService, string data)
0xf9  stloc.2
0xfa  leave.s  loc_143
0xfc  ldarg.0
0xfd  ldloc.0
0xfe  ldloc.1
0xff  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::UpdateLastRunConfigurationOnIdle(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService, string data)
0x104  stloc.2
0x105  leave.s  loc_143
0x107  stloc.3
0x108  ldarg.0
0x109  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_cardsTrace
0x10e  ldarg.0
0x10f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x114  ldstr    aAsynchandlerIn// "AsyncHandler::InternalExecute"
0x119  ldc.i4.2
0x11a  ldstr    aActionCardAsyn// "Action card Async Operation could not c"...
0x11f  ldloc.3
0x120  callvirt instance string [mscorlib]System.Object::ToString()
0x125  call     string [mscorlib]System.String::Format(string, object)
0x12a  ldsfld   string [mscorlib]System.String::Empty
0x12f  ldarg.0
0x130  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_ownerId
0x135  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardError(valuetype [mscorlib]System.Guid, string, int32, string, string, valuetype [mscorlib]System.Guid)
0x13a  ldloc.3
0x13b  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0x140  stloc.2
0x141  leave.s  loc_143
0x143  ldloc.2
0x144  ret
```
