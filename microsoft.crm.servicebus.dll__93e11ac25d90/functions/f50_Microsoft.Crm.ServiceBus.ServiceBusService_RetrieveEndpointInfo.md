# Microsoft.Crm.ServiceBus.ServiceBusService::RetrieveEndpointInfo

- ea: `0xf50`
- end: `0xfd2`
- name: `Microsoft.Crm.ServiceBus.ServiceBusService::RetrieveEndpointInfo`
- size: `130`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xb00`
- `0xb60`

## callees

- `0xf50`
- `0x19d0`

## string_xrefs

- `0xf61`: `serviceendpoint`
- `0xf51`: `serviceEndpoint`
- `0xf6e`: `Entity reference should refer to service endpoint.`
- `0xf73`: `serviceEndpoint.LogicalName`
- `0xf84`: `internalOrgServiceFactory`

## pseudocode

```c

```

## disassembly

```asm
0xf50  ldarg.2
0xf51  ldstr    aServiceendpoin_0// "serviceEndpoint"
0xf56  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xf5b  ldarg.2
0xf5c  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0xf61  ldstr    aServiceendpoin// "serviceendpoint"
0xf66  ldc.i4.5
0xf67  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xf6c  brtrue.s loc_F7E
0xf6e  ldstr    aEntityReferenc// "Entity reference should refer to servic"...
0xf73  ldstr    aServiceendpoin_2// "serviceEndpoint.LogicalName"
0xf78  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0xf7d  throw
0xf7e  ldarg.0
0xf7f  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory Microsoft.Crm.ServiceBus.ServiceBusService::internalOrgServiceFactory
0xf84  ldstr    aInternalorgser// "internalOrgServiceFactory"
0xf89  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xf8e  ldarg.0
0xf8f  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.ServiceBus.ServiceBusService::internalContext
0xf94  ldstr    aInternalcontex// "internalContext"
0xf99  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xf9e  ldarg.1
0xf9f  ldarg.0
0xfa0  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.ServiceBus.ServiceBusService::internalContext
0xfa5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0xfaa  ldarg.0
0xfab  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.ServiceBus.ServiceBusService::internalContext
0xfb0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_UserId()
0xfb5  ldarg.0
0xfb6  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.ServiceBus.ServiceBusService::internalContext
0xfbb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InitiatingUserId()
0xfc0  ldarg.2
0xfc1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xfc6  ldarg.0
0xfc7  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory Microsoft.Crm.ServiceBus.ServiceBusService::internalOrgServiceFactory
0xfcc  newobj   instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::.ctor(string assemblyName, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid initiatingUserId, valuetype [mscorlib]System.Guid configurationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory orgServiceFactory)
0xfd1  ret
```
