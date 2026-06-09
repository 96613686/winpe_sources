# Microsoft.Crm.Sdk.Crm2007.CrmService::Fetch

- ea: `0xaab0`
- end: `0xaaea`
- name: `Microsoft.Crm.Sdk.Crm2007.CrmService::Fetch`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x920`
- `0xac50`
- `0xfa30`
- `0xfa50`

## string_xrefs

- `0xaac7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0xaab1`: `fetchXml`

## pseudocode

```c

```

## disassembly

```asm
0xaab0  ldarg.1
0xaab1  ldstr    aFetchxml// "fetchXml"
0xaab6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xaabb  ldarg.0
0xaabc  call     instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.WebServices.CrmWebServiceBase::CheckUnknownHeaders()
0xaac1  ldarg.0
0xaac2  call     instance class Microsoft.Crm.Sdk.CrmServiceInternal Microsoft.Crm.Sdk.Crm2007.CrmService::CreateCrmServiceInternal()
0xaac7  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0xaacc  ldarg.1
0xaacd  ldarg.0
0xaace  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken Microsoft.Crm.Sdk.Crm2007.CrmService::_correlationToken
0xaad3  ldarg.0
0xaad4  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_CallerOriginToken()
0xaad9  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetCallerAndBusinessGuids()
0xaade  ldarg.0
0xaadf  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_CurrentCallerId()
0xaae4  callvirt instance string Microsoft.Crm.Sdk.CrmServiceInternal::Fetch(string namespaceName, string fetchXml, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken originToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth, valuetype [mscorlib]System.Guid callerId)
0xaae9  ret
```
