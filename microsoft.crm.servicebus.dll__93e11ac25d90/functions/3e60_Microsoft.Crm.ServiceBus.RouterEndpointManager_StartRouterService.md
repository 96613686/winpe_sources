# Microsoft.Crm.ServiceBus.RouterEndpointManager::StartRouterService

- ea: `0x3e60`
- end: `0x3f2f`
- name: `Microsoft.Crm.ServiceBus.RouterEndpointManager::StartRouterService`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x3e50`

## callees

- `0x2b30`
- `0x2f90`
- `0x36c0`
- `0x3e60`

## string_xrefs

- `0x3ea9`: `CrmRouterService`

## pseudocode

```c

```

## disassembly

```asm
0x3e60  newobj   instance void [System]System.UriBuilder::.ctor()
0x3e65  stloc.0
0x3e66  ldloc.0
0x3e67  ldstr    aNetTcp// "net.tcp"
0x3e6c  callvirt instance void [System]System.UriBuilder::set_Scheme(string)
0x3e71  ldloc.0
0x3e72  ldstr    aLocalhost// "localhost"
0x3e77  callvirt instance void [System]System.UriBuilder::set_Host(string)
0x3e7c  ldc.i4.0
0x3e7d  box      Microsoft.Crm.ServiceBus.ServiceBusPropertyPrefix
0x3e82  ldstr    aRouterport// "RouterPort"
0x3e87  call     string [mscorlib]System.String::Concat(object, object)
0x3e8c  ldc.i4.0
0x3e8d  box      [mscorlib]System.Int32
0x3e92  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x3e97  unbox.any [mscorlib]System.Int32
0x3e9c  stloc.1
0x3e9d  ldloc.1
0x3e9e  ldc.i4.0
0x3e9f  ble.s    loc_3EA8
0x3ea1  ldloc.0
0x3ea2  ldloc.1
0x3ea3  callvirt instance void [System]System.UriBuilder::set_Port(int32)
0x3ea8  ldloc.0
0x3ea9  ldstr    aCrmrouterservi// "CrmRouterService"
0x3eae  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x3eb3  ldloc.0
0x3eb4  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x3eb9  stloc.2
0x3eba  newobj   instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::.ctor()
0x3ebf  stloc.3
0x3ec0  ldc.i4.2
0x3ec1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3ec6  newobj   instance void Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::.ctor(valuetype Microsoft.Crm.ServiceBus.ServiceBusPropertyPrefix propertyPrefix, valuetype [mscorlib]System.Guid orgId)
0x3ecb  ldloc.3
0x3ecc  castclass [System.ServiceModel]System.ServiceModel.NetTcpBinding
0x3ed1  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::Apply(class [System.ServiceModel]System.ServiceModel.NetTcpBinding binding)
0x3ed6  ldarg.0
0x3ed7  ldtoken  Microsoft.Crm.ServiceBus.RouterService
0x3edc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3ee1  ldc.i4.1
0x3ee2  newarr   [System]System.Uri
0x3ee7  dup
0x3ee8  ldc.i4.0
0x3ee9  ldloc.2
0x3eea  stelem.ref
0x3eeb  newobj   instance void [System.ServiceModel]System.ServiceModel.ServiceHost::.ctor(class [mscorlib]System.Type, class [System]System.Uri[])
0x3ef0  stfld    class [System.ServiceModel]System.ServiceModel.ServiceHost Microsoft.Crm.ServiceBus.RouterEndpointManager::host
0x3ef5  ldarg.0
0x3ef6  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost Microsoft.Crm.ServiceBus.RouterEndpointManager::host
0x3efb  ldtoken  Microsoft.Crm.ServiceBus.IRouterContract
0x3f00  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3f05  ldloc.3
0x3f06  ldloc.2
0x3f07  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint [System.ServiceModel]System.ServiceModel.ServiceHost::AddServiceEndpoint(class [mscorlib]System.Type, class [System.ServiceModel]System.ServiceModel.Channels.Binding, class [System]System.Uri)
0x3f0c  pop
0x3f0d  ldc.i4.0
0x3f0e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3f13  newobj   instance void Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::.ctor(valuetype Microsoft.Crm.ServiceBus.ServiceBusPropertyPrefix propertyPrefix, valuetype [mscorlib]System.Guid orgId)
0x3f18  ldarg.0
0x3f19  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost Microsoft.Crm.ServiceBus.RouterEndpointManager::host
0x3f1e  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::Apply(class [System.ServiceModel]System.ServiceModel.ServiceHost host)
0x3f23  ldarg.0
0x3f24  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost Microsoft.Crm.ServiceBus.RouterEndpointManager::host
0x3f29  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.CommunicationObject::Open()
0x3f2e  ret
```
