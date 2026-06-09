# Microsoft.Crm.ServiceBus.ServiceBusPlugin::Execute

- ea: `0x7b0`
- end: `0x831`
- name: `Microsoft.Crm.ServiceBus.ServiceBusPlugin::Execute`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xb00`
- `0x26b0`

## string_xrefs

- `0x7b1`: `serviceProvider`
- `0x7f2`: `serviceBusService`
- `0x802`: `internalService`
- `0x818`: `serviceendpoint`

## pseudocode

```c

```

## disassembly

```asm
0x7b0  ldarg.1
0x7b1  ldstr    aServiceprovide// "serviceProvider"
0x7b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7bb  ldarg.1
0x7bc  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x7c1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7c6  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x7cb  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x7d0  stloc.0
0x7d1  ldloc.0
0x7d2  ldstr    aContext// "context"
0x7d7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7dc  ldarg.1
0x7dd  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IServiceEndpointNotificationService
0x7e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e7  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x7ec  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IServiceEndpointNotificationService
0x7f1  dup
0x7f2  ldstr    aServicebusserv// "serviceBusService"
0x7f7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7fc  isinst   Microsoft.Crm.ServiceBus.ServiceBusService
0x801  dup
0x802  ldstr    aInternalservic// "internalService"
0x807  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x80c  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x811  stloc.1
0x812  ldloc.1
0x813  call     string Microsoft.Crm.ServiceBus.ServiceBusUtility::RetrieveAssemblyName(class [mscorlib]System.Reflection.Assembly assembly)
0x818  ldstr    aServiceendpoin// "serviceendpoint"
0x81d  ldarg.0
0x81e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusPlugin::entityId
0x823  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x828  ldc.i4.0
0x829  ldloc.0
0x82a  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusService::PostInternal(string assemblyName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference serviceEndpoint, bool validateOnly, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x82f  pop
0x830  ret
```
