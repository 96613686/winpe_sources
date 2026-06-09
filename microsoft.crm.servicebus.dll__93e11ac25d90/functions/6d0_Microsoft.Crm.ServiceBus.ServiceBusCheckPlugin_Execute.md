# Microsoft.Crm.ServiceBus.ServiceBusCheckPlugin::Execute

- ea: `0x6d0`
- end: `0x77f`
- name: `Microsoft.Crm.ServiceBus.ServiceBusCheckPlugin::Execute`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x6d0`
- `0xb00`
- `0x26b0`

## string_xrefs

- `0x6d1`: `serviceProvider`
- `0x740`: `serviceBusService`
- `0x750`: `internalService`
- `0x766`: `serviceendpoint`

## pseudocode

```c

```

## disassembly

```asm
0x6d0  ldarg.1
0x6d1  ldstr    aServiceprovide// "serviceProvider"
0x6d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6db  ldarg.1
0x6dc  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x6e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6e6  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x6eb  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x6f0  stloc.0
0x6f1  ldloc.0
0x6f2  ldstr    aContext// "context"
0x6f7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6fc  ldarg.0
0x6fd  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusCheckPlugin::entityId
0x702  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x707  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x70c  brfalse.s loc_71A
0x70e  ldarg.0
0x70f  ldloc.0
0x710  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PrimaryEntityId()
0x715  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusCheckPlugin::entityId
0x71a  ldarg.0
0x71b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusCheckPlugin::entityId
0x720  ldstr    aEntityid// "entityId"
0x725  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x72a  ldarg.1
0x72b  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IServiceEndpointNotificationService
0x730  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x735  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x73a  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IServiceEndpointNotificationService
0x73f  dup
0x740  ldstr    aServicebusserv// "serviceBusService"
0x745  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x74a  isinst   Microsoft.Crm.ServiceBus.ServiceBusService
0x74f  dup
0x750  ldstr    aInternalservic// "internalService"
0x755  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x75a  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x75f  stloc.1
0x760  ldloc.1
0x761  call     string Microsoft.Crm.ServiceBus.ServiceBusUtility::RetrieveAssemblyName(class [mscorlib]System.Reflection.Assembly assembly)
0x766  ldstr    aServiceendpoin// "serviceendpoint"
0x76b  ldarg.0
0x76c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusCheckPlugin::entityId
0x771  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x776  ldc.i4.1
0x777  ldloc.0
0x778  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusService::PostInternal(string assemblyName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference serviceEndpoint, bool validateOnly, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x77d  pop
0x77e  ret
```
