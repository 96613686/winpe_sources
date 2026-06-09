# Microsoft.Crm.Sdk.Crm2007.CrmService::Delete

- ea: `0xab30`
- end: `0xab76`
- name: `Microsoft.Crm.Sdk.Crm2007.CrmService::Delete`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x700`
- `0xac50`
- `0xfa30`
- `0xfa50`

## string_xrefs

- `0xab52`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xab30  ldarg.1
0xab31  ldstr    aEntityname_0// "entityName"
0xab36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xab3b  ldarg.2
0xab3c  ldstr    aId// "id"
0xab41  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xab46  ldarg.0
0xab47  call     instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.WebServices.CrmWebServiceBase::CheckUnknownHeaders()
0xab4c  ldarg.0
0xab4d  call     instance class Microsoft.Crm.Sdk.CrmServiceInternal Microsoft.Crm.Sdk.Crm2007.CrmService::CreateCrmServiceInternal()
0xab52  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0xab57  ldarg.1
0xab58  ldarg.2
0xab59  ldarg.0
0xab5a  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken Microsoft.Crm.Sdk.Crm2007.CrmService::_correlationToken
0xab5f  ldarg.0
0xab60  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_CallerOriginToken()
0xab65  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetCallerAndBusinessGuids()
0xab6a  ldarg.0
0xab6b  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_CurrentCallerId()
0xab70  callvirt instance void Microsoft.Crm.Sdk.CrmServiceInternal::Delete(string namespaceName, string entityName, valuetype [mscorlib]System.Guid id, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken originToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth, valuetype [mscorlib]System.Guid callerId)
0xab75  ret
```
