# Microsoft.Crm.Sdk.Crm2007.CrmService::Execute

- ea: `0xaa70`
- end: `0xaaaa`
- name: `Microsoft.Crm.Sdk.Crm2007.CrmService::Execute`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x5a0`
- `0xac50`
- `0xfa30`
- `0xfa50`

## pseudocode

```c

```

## disassembly

```asm
0xaa70  ldarg.1
0xaa71  ldstr    aRequest_0// "request"
0xaa76  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xaa7b  ldarg.0
0xaa7c  call     instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.WebServices.CrmWebServiceBase::CheckUnknownHeaders()
0xaa81  ldarg.0
0xaa82  call     instance class Microsoft.Crm.Sdk.CrmServiceInternal Microsoft.Crm.Sdk.Crm2007.CrmService::CreateCrmServiceInternal()
0xaa87  ldarg.1
0xaa88  ldarg.0
0xaa89  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken Microsoft.Crm.Sdk.Crm2007.CrmService::_correlationToken
0xaa8e  ldarg.0
0xaa8f  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_CallerOriginToken()
0xaa94  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetCallerAndBusinessGuids()
0xaa99  ldarg.0
0xaa9a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_CurrentCallerId()
0xaa9f  callvirt instance class Microsoft.Crm.Sdk.ResponseBase Microsoft.Crm.Sdk.CrmServiceInternal::Execute(class Microsoft.Crm.Sdk.RequestBase request, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken originToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth, valuetype [mscorlib]System.Guid callerId)
0xaaa4  castclass Microsoft.Crm.Sdk.Crm2007.Response
0xaaa9  ret
```
