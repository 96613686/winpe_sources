# Microsoft.Crm.ServiceBus.WebhookPlugin::Execute

- ea: `0x870`
- end: `0x8f1`
- name: `Microsoft.Crm.ServiceBus.WebhookPlugin::Execute`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xb00`
- `0x26b0`

## string_xrefs

- `0x871`: `serviceProvider`
- `0x8c2`: `internalService`
- `0x8d8`: `serviceendpoint`
- `0x8b2`: `webhookService`

## pseudocode

```c

```

## disassembly

```asm
0x870  ldarg.1
0x871  ldstr    aServiceprovide// "serviceProvider"
0x876  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x87b  ldarg.1
0x87c  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x881  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x886  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x88b  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x890  stloc.0
0x891  ldloc.0
0x892  ldstr    aContext// "context"
0x897  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x89c  ldarg.1
0x89d  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IServiceEndpointNotificationService
0x8a2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8a7  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x8ac  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IServiceEndpointNotificationService
0x8b1  dup
0x8b2  ldstr    aWebhookservice// "webhookService"
0x8b7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8bc  isinst   Microsoft.Crm.ServiceBus.ServiceBusService
0x8c1  dup
0x8c2  ldstr    aInternalservic// "internalService"
0x8c7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8cc  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x8d1  stloc.1
0x8d2  ldloc.1
0x8d3  call     string Microsoft.Crm.ServiceBus.ServiceBusUtility::RetrieveAssemblyName(class [mscorlib]System.Reflection.Assembly assembly)
0x8d8  ldstr    aServiceendpoin// "serviceendpoint"
0x8dd  ldarg.0
0x8de  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.WebhookPlugin::entityId
0x8e3  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x8e8  ldc.i4.0
0x8e9  ldloc.0
0x8ea  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusService::PostInternal(string assemblyName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference serviceEndpoint, bool validateOnly, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x8ef  pop
0x8f0  ret
```
