# Microsoft.Crm.Sdk.Crm2007.CrmService::Retrieve

- ea: `0xab80`
- end: `0xabcd`
- name: `Microsoft.Crm.Sdk.Crm2007.CrmService::Retrieve`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x7d0`
- `0xa940`
- `0xac50`
- `0xfa30`
- `0xfa50`

## string_xrefs

- `0xaba2`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xab80  ldarg.1
0xab81  ldstr    aEntityname_0// "entityName"
0xab86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xab8b  ldarg.2
0xab8c  ldstr    aId// "id"
0xab91  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xab96  ldarg.0
0xab97  call     instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.WebServices.CrmWebServiceBase::CheckUnknownHeaders()
0xab9c  ldarg.0
0xab9d  call     instance class Microsoft.Crm.Sdk.CrmServiceInternal Microsoft.Crm.Sdk.Crm2007.CrmService::CreateCrmServiceInternal()
0xaba2  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0xaba7  ldarg.1
0xaba8  ldarg.2
0xaba9  ldarg.3
0xabaa  ldarg.0
0xabab  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken Microsoft.Crm.Sdk.Crm2007.CrmService::_correlationToken
0xabb0  ldarg.0
0xabb1  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_CallerOriginToken()
0xabb6  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetCallerAndBusinessGuids()
0xabbb  ldarg.0
0xabbc  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_CurrentCallerId()
0xabc1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Sdk.CrmServiceInternal::Retrieve(string namespaceName, string entityName, valuetype [mscorlib]System.Guid id, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase columnSet, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken originToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth, valuetype [mscorlib]System.Guid callerId)
0xabc6  ldc.i4.1
0xabc7  newobj   instance void Microsoft.Crm.Sdk.Crm2007.BusinessEntity::.ctor(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity entity, bool skipOuterNode)
0xabcc  ret
```
