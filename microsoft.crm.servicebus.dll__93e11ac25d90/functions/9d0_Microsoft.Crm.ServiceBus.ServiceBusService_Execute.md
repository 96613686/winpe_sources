# Microsoft.Crm.ServiceBus.ServiceBusService::Execute

- ea: `0x9d0`
- end: `0xa43`
- name: `Microsoft.Crm.ServiceBus.ServiceBusService::Execute`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x9d0`
- `0x1950`
- `0x26b0`

## string_xrefs

- `0x9fc`: `internalService`
- `0xa0c`: `serviceendpoint`
- `0x9d1`: `serviceEndpoint`
- `0x9e1`: `serviceEndpoint.Id`
- `0xa19`: `Entity reference should refer to service endpoint.`
- `0xa1e`: `serviceEndpoint.LogicalName`

## pseudocode

```c

```

## disassembly

```asm
0x9d0  ldarg.1
0x9d1  ldstr    aServiceendpoin_0// "serviceEndpoint"
0x9d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9db  ldarg.1
0x9dc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x9e1  ldstr    aServiceendpoin_1// "serviceEndpoint.Id"
0x9e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x9eb  ldarg.2
0x9ec  ldstr    aContext// "context"
0x9f1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9f6  ldarg.0
0x9f7  ldfld    class Microsoft.Crm.ServiceBus.IInternalServiceEndpointService Microsoft.Crm.ServiceBus.ServiceBusService::internalService
0x9fc  ldstr    aInternalservic// "internalService"
0xa01  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xa06  ldarg.1
0xa07  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0xa0c  ldstr    aServiceendpoin// "serviceendpoint"
0xa11  ldc.i4.5
0xa12  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xa17  brtrue.s loc_A29
0xa19  ldstr    aEntityReferenc// "Entity reference should refer to servic"...
0xa1e  ldstr    aServiceendpoin_2// "serviceEndpoint.LogicalName"
0xa23  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0xa28  throw
0xa29  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetCallingAssembly()
0xa2e  stloc.0
0xa2f  ldarg.0
0xa30  ldfld    class Microsoft.Crm.ServiceBus.IInternalServiceEndpointService Microsoft.Crm.ServiceBus.ServiceBusService::internalService
0xa35  ldloc.0
0xa36  call     string Microsoft.Crm.ServiceBus.ServiceBusUtility::RetrieveAssemblyName(class [mscorlib]System.Reflection.Assembly assembly)
0xa3b  ldarg.1
0xa3c  ldarg.2
0xa3d  callvirt instance string Microsoft.Crm.ServiceBus.IInternalServiceEndpointService::Post(string assemblyName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference serviceEndpoint, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0xa42  ret
```
