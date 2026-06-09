# Microsoft.Crm.Asynchronous.ProvisionLanguagePackOperation::InternalExecute

- ea: `0xce00`
- end: `0xceb0`
- name: `Microsoft.Crm.Asynchronous.ProvisionLanguagePackOperation::InternalExecute`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x8fd0`
- `0x8fe0`

## string_xrefs

- `0xce1c`: `Attempting to reprovision language {0}`

## pseudocode

```c

```

## disassembly

```asm
0xce00  ldarg.1
0xce01  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xce06  ldc.i4.s 0x2B
0xce08  ceq
0xce0a  ldstr    aOperationTypeM_18// "Operation type must be 'ProvisionLangua"...
0xce0f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xce14  ldarg.1
0xce15  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xce1a  ldc.i4.s 0x15
0xce1c  ldstr    aAttemptingToRe// "Attempting to reprovision language {0}"
0xce21  ldc.i4.1
0xce22  newarr   [mscorlib]System.Object
0xce27  dup
0xce28  ldc.i4.0
0xce29  ldarg.1
0xce2a  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0xce2f  stelem.ref
0xce30  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xce35  ldarg.1
0xce36  ldc.i4.1
0xce37  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent, bool)
0xce3c  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ProvisionLanguageRequest::.ctor()
0xce41  stloc.0
0xce42  ldloc.0
0xce43  ldarg.1
0xce44  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0xce49  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xce4e  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0xce53  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ProvisionLanguageRequest::set_Language(int32)
0xce58  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0xce5d  stloc.1
0xce5e  ldloc.0
0xce5f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0xce64  pop
0xce65  call     class Microsoft.Crm.Asynchronous.ProvisionLanguagePackEventSource Microsoft.Crm.Asynchronous.ProvisionLanguagePackEventSource::get_Instance()
0xce6a  ldarg.1
0xce6b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xce70  ldloc.0
0xce71  callvirt instance int32 [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ProvisionLanguageRequest::get_Language()
0xce76  ldarg.1
0xce77  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_OwnerId()
0xce7c  ldloc.1
0xce7d  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0xce82  callvirt instance void Microsoft.Crm.Asynchronous.ProvisionLanguagePackEventSource::WriteProvisionLanguagePackTelemetryEvent(valuetype [mscorlib]System.Guid organizationId, int32 languagePackId, valuetype [mscorlib]System.Guid ownerId, int64 executionTime)
0xce87  ldarg.1
0xce88  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xce8d  ldc.i4.s 0x15
0xce8f  ldstr    aReprovisioning_1// "Reprovisioning of language {0} was succ"...
0xce94  ldc.i4.1
0xce95  newarr   [mscorlib]System.Object
0xce9a  dup
0xce9b  ldc.i4.0
0xce9c  ldarg.1
0xce9d  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0xcea2  stelem.ref
0xcea3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcea8  ldc.i4.s 0x1E
0xceaa  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRemoveEventResult::.ctor(int32)
0xceaf  ret
```
