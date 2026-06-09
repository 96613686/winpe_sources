# Microsoft.Crm.Sdk.Crm2007.CrmService::Create

- ea: `0xaaf0`
- end: `0xab2a`
- name: `Microsoft.Crm.Sdk.Crm2007.CrmService::Create`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x680`
- `0xac50`
- `0xfa30`
- `0xfa50`

## string_xrefs

- `0xab07`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xaaf0  ldarg.1
0xaaf1  ldstr    aEntity_0// "entity"
0xaaf6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xaafb  ldarg.0
0xaafc  call     instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.WebServices.CrmWebServiceBase::CheckUnknownHeaders()
0xab01  ldarg.0
0xab02  call     instance class Microsoft.Crm.Sdk.CrmServiceInternal Microsoft.Crm.Sdk.Crm2007.CrmService::CreateCrmServiceInternal()
0xab07  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0xab0c  ldarg.1
0xab0d  ldarg.0
0xab0e  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken Microsoft.Crm.Sdk.Crm2007.CrmService::_correlationToken
0xab13  ldarg.0
0xab14  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_CallerOriginToken()
0xab19  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetCallerAndBusinessGuids()
0xab1e  ldarg.0
0xab1f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_CurrentCallerId()
0xab24  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.CrmServiceInternal::Create(string namespaceName, class Microsoft.Crm.Sdk.BusinessEntityBase entity, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken originToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth, valuetype [mscorlib]System.Guid callerId)
0xab29  ret
```
