# Microsoft.Crm.Sdk.CrmServiceInternal::ExecuteRequest

- ea: `0x990`
- end: `0x9ca`
- name: `Microsoft.Crm.Sdk.CrmServiceInternal::ExecuteRequest`
- size: `58`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x680`
- `0x700`
- `0x760`
- `0x7d0`
- `0x880`
- `0x920`

## callees

- `0xc60`

## pseudocode

```c

```

## disassembly

```asm
0x990  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ExternalMessageDispatcher [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ExternalMessageDispatcher::get_Instance()
0x995  call     class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory [Microsoft.Crm.Extensibility]Microsoft.Crm.Extensibility.InprocessServiceFactory::get_Instance()
0x99a  call     class [Microsoft.Crm.Extensibility]Microsoft.Crm.Extensibility.MessageDispatcherFactory [Microsoft.Crm.Extensibility]Microsoft.Crm.Extensibility.MessageDispatcherFactory::get_Instance()
0x99f  ldarg.1
0x9a0  ldarg.2
0x9a1  ldarg.3
0x9a2  ldc.i4.0
0x9a3  ldarg.s  4
0x9a5  ldc.i4.0
0x9a6  newarr   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x9ab  ldarg.s  5
0x9ad  call     class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken Microsoft.Crm.Sdk.CrmServiceInternal::FromCrmCorrelationToken(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken correlationToken)
0x9b2  ldarg.s  6
0x9b4  ldarg.s  7
0x9b6  ldarg.s  8
0x9b8  ldarg.0
0x9b9  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.CrmServiceInternal::_transactionContextId
0x9be  ldarg.0
0x9bf  ldfld    class [mscorlib]System.Version Microsoft.Crm.Sdk.CrmServiceInternal::_endpointVersion
0x9c4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ExternalMessageDispatcher::ExecuteLegacyRequest(class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.IPlatformMessageDispatcherFactory, string, string, int32, int32, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[], class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x9c9  ret
```
