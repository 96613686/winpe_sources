# Microsoft.Crm.ServiceBus.RouterClient::Start

- ea: `0x230`
- end: `0x348`
- name: `Microsoft.Crm.ServiceBus.RouterClient::Start`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x570`

## callees

- `0x230`
- `0x390`
- `0x2b30`
- `0x2f90`
- `0x3820`

## string_xrefs

- `0x297`: `CrmRouterService`

## pseudocode

```c

```

## disassembly

```asm
0x230  ldarg.0
0x231  ldfld    class Microsoft.Crm.ServiceBus.IRouterChannel Microsoft.Crm.ServiceBus.RouterClient::channel
0x236  brfalse.s loc_243
0x238  ldstr    aCannotCallStar// "Cannot call start on an intialized clie"...
0x23d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x242  throw
0x243  newobj   instance void [System]System.UriBuilder::.ctor()
0x248  stloc.0
0x249  ldloc.0
0x24a  ldstr    aNetTcp// "net.tcp"
0x24f  callvirt instance void [System]System.UriBuilder::set_Scheme(string)
0x254  ldloc.0
0x255  ldarg.1
0x256  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25b  brtrue.s loc_260
0x25d  ldarg.1
0x25e  br.s     loc_265
0x260  ldstr    aLocalhost// "localhost"
0x265  callvirt instance void [System]System.UriBuilder::set_Host(string)
0x26a  ldc.i4.0
0x26b  box      Microsoft.Crm.ServiceBus.ServiceBusPropertyPrefix
0x270  ldstr    aRouterport// "RouterPort"
0x275  call     string [mscorlib]System.String::Concat(object, object)
0x27a  ldc.i4.0
0x27b  box      [mscorlib]System.Int32
0x280  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x285  unbox.any [mscorlib]System.Int32
0x28a  stloc.1
0x28b  ldloc.1
0x28c  ldc.i4.0
0x28d  ble.s    loc_296
0x28f  ldloc.0
0x290  ldloc.1
0x291  callvirt instance void [System]System.UriBuilder::set_Port(int32)
0x296  ldloc.0
0x297  ldstr    aCrmrouterservi// "CrmRouterService"
0x29c  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x2a1  ldloc.0
0x2a2  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x2a7  stloc.2
0x2a8  ldnull
0x2a9  stloc.3
0x2aa  ldarg.0
0x2ab  ldloc.0
0x2ac  callvirt instance string [System]System.UriBuilder::get_Host()
0x2b1  call     instance string Microsoft.Crm.ServiceBus.RouterClient::RetrieveRouterServicePrincipalName(string endpointHostName)
0x2b6  stloc.s  4
0x2b8  ldloc.s  4
0x2ba  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2bf  brfalse.s loc_2D0
0x2c1  ldloc.2
0x2c2  ldc.i4.0
0x2c3  newarr   [System.ServiceModel]System.ServiceModel.Channels.AddressHeader
0x2c8  newobj   instance void [System.ServiceModel]System.ServiceModel.EndpointAddress::.ctor(class [System]System.Uri, class [System.ServiceModel]System.ServiceModel.Channels.AddressHeader[])
0x2cd  stloc.3
0x2ce  br.s     loc_2E4
0x2d0  ldloc.2
0x2d1  ldloc.s  4
0x2d3  call     class [System.ServiceModel]System.ServiceModel.EndpointIdentity [System.ServiceModel]System.ServiceModel.EndpointIdentity::CreateSpnIdentity(string)
0x2d8  ldc.i4.0
0x2d9  newarr   [System.ServiceModel]System.ServiceModel.Channels.AddressHeader
0x2de  newobj   instance void [System.ServiceModel]System.ServiceModel.EndpointAddress::.ctor(class [System]System.Uri, class [System.ServiceModel]System.ServiceModel.EndpointIdentity, class [System.ServiceModel]System.ServiceModel.Channels.AddressHeader[])
0x2e3  stloc.3
0x2e4  ldsfld   class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class Microsoft.Crm.ServiceBus.IRouterChannel> Microsoft.Crm.ServiceBus.RouterClient::channelFactory
0x2e9  brtrue.s loc_315
0x2eb  newobj   instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::.ctor()
0x2f0  stloc.s  5
0x2f2  ldc.i4.2
0x2f3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2f8  newobj   instance void Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::.ctor(valuetype Microsoft.Crm.ServiceBus.ServiceBusPropertyPrefix propertyPrefix, valuetype [mscorlib]System.Guid orgId)
0x2fd  ldloc.s  5
0x2ff  castclass [System.ServiceModel]System.ServiceModel.NetTcpBinding
0x304  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::Apply(class [System.ServiceModel]System.ServiceModel.NetTcpBinding binding)
0x309  ldloc.s  5
0x30b  newobj   instance void class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class Microsoft.Crm.ServiceBus.IRouterChannel>::.ctor(class [System.ServiceModel]System.ServiceModel.Channels.Binding)
0x310  stsfld   class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class Microsoft.Crm.ServiceBus.IRouterChannel> Microsoft.Crm.ServiceBus.RouterClient::channelFactory
0x315  ldarg.0
0x316  ldsfld   class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class Microsoft.Crm.ServiceBus.IRouterChannel> Microsoft.Crm.ServiceBus.RouterClient::channelFactory
0x31b  ldloc.3
0x31c  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class Microsoft.Crm.ServiceBus.IRouterChannel>::CreateChannel(!!T0)
0x321  stfld    class Microsoft.Crm.ServiceBus.IRouterChannel Microsoft.Crm.ServiceBus.RouterClient::channel
0x326  ldarg.0
0x327  ldfld    class Microsoft.Crm.ServiceBus.IRouterChannel Microsoft.Crm.ServiceBus.RouterClient::channel
0x32c  callvirt instance void [System.ServiceModel]System.ServiceModel.ICommunicationObject::Open()
0x331  ldc.i4.2
0x332  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x337  newobj   instance void Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::.ctor(valuetype Microsoft.Crm.ServiceBus.ServiceBusPropertyPrefix propertyPrefix, valuetype [mscorlib]System.Guid orgId)
0x33c  ldarg.0
0x33d  ldfld    class Microsoft.Crm.ServiceBus.IRouterChannel Microsoft.Crm.ServiceBus.RouterClient::channel
0x342  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::Apply(class [System.ServiceModel]System.ServiceModel.IClientChannel channel)
0x347  ret
```
