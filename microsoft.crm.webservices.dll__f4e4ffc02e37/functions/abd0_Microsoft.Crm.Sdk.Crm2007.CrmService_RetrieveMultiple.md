# Microsoft.Crm.Sdk.Crm2007.CrmService::RetrieveMultiple

- ea: `0xabd0`
- end: `0xac10`
- name: `Microsoft.Crm.Sdk.Crm2007.CrmService::RetrieveMultiple`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x880`
- `0xa970`
- `0xac50`
- `0xfa30`
- `0xfa50`

## string_xrefs

- `0xabe7`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xabd0  ldarg.1
0xabd1  ldstr    aQuery_0// "query"
0xabd6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xabdb  ldarg.0
0xabdc  call     instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.WebServices.CrmWebServiceBase::CheckUnknownHeaders()
0xabe1  ldarg.0
0xabe2  call     instance class Microsoft.Crm.Sdk.CrmServiceInternal Microsoft.Crm.Sdk.Crm2007.CrmService::CreateCrmServiceInternal()
0xabe7  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0xabec  ldarg.1
0xabed  ldarg.0
0xabee  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken Microsoft.Crm.Sdk.Crm2007.CrmService::_correlationToken
0xabf3  ldarg.0
0xabf4  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_CallerOriginToken()
0xabf9  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetCallerAndBusinessGuids()
0xabfe  ldarg.0
0xabff  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_CurrentCallerId()
0xac04  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection Microsoft.Crm.Sdk.CrmServiceInternal::RetrieveMultiple(string namespaceName, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase query, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken originToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth, valuetype [mscorlib]System.Guid callerId)
0xac09  ldc.i4.1
0xac0a  newobj   instance void Microsoft.Crm.Sdk.Crm2007.BusinessEntityCollection::.ctor(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection entityCollection, bool skipOuterNode)
0xac0f  ret
```
