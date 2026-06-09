# Microsoft.Crm.ServiceBus.ServiceBusOneWayClient::Start

- ea: `0x4980`
- end: `0x4a01`
- name: `Microsoft.Crm.ServiceBus.ServiceBusOneWayClient::Start`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x4500`
- `0x4650`
- `0x4670`
- `0x4690`
- `0x46a0`
- `0x4980`

## pseudocode

```c

```

## disassembly

```asm
0x4980  ldarg.0
0x4981  ldarg.1
0x4982  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::Start(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x4987  ldarg.0
0x4988  ldarg.0
0x4989  call     instance class [System.ServiceModel]System.ServiceModel.Channels.Binding Microsoft.Crm.ServiceBus.ServiceBusClientBase::get_EndpointBinding()
0x498e  ldarg.0
0x498f  call     instance class [System.ServiceModel]System.ServiceModel.EndpointAddress Microsoft.Crm.ServiceBus.ServiceBusClientBase::get_ServiceEndpointAddress()
0x4994  newobj   instance void class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class Microsoft.Crm.ServiceBus.IServiceBusChannel>::.ctor(class [System.ServiceModel]System.ServiceModel.Channels.Binding, class [System.ServiceModel]System.ServiceModel.EndpointAddress)
0x4999  stfld    class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class Microsoft.Crm.ServiceBus.IServiceBusChannel> Microsoft.Crm.ServiceBus.ServiceBusOneWayClient::channelFactory
0x499e  ldarg.0
0x499f  call     instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> Microsoft.Crm.ServiceBus.ServiceBusClientBase::get_EndpointBehaviors()
0x49a4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::GetEnumerator()
0x49a9  stloc.0
0x49aa  br.s     loc_49C9
0x49ac  ldloc.0
0x49ad  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::get_Current()
0x49b2  stloc.1
0x49b3  ldarg.0
0x49b4  ldfld    class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class Microsoft.Crm.ServiceBus.IServiceBusChannel> Microsoft.Crm.ServiceBus.ServiceBusOneWayClient::channelFactory
0x49b9  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint [System.ServiceModel]System.ServiceModel.ChannelFactory::get_Endpoint()
0x49be  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Behaviors()
0x49c3  ldloc.1
0x49c4  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::Add(var<u1>)
0x49c9  ldloc.0
0x49ca  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x49cf  brtrue.s loc_49AC
0x49d1  leave.s  loc_49DD
0x49d3  ldloc.0
0x49d4  brfalse.s loc_49DC
0x49d6  ldloc.0
0x49d7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x49dc  endfinally
0x49dd  ldarg.0
0x49de  ldarg.0
0x49df  ldfld    class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class Microsoft.Crm.ServiceBus.IServiceBusChannel> Microsoft.Crm.ServiceBus.ServiceBusOneWayClient::channelFactory
0x49e4  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class Microsoft.Crm.ServiceBus.IServiceBusChannel>::CreateChannel()
0x49e9  stfld    class Microsoft.Crm.ServiceBus.IServiceBusChannel Microsoft.Crm.ServiceBus.ServiceBusOneWayClient::channel
0x49ee  ldarg.0
0x49ef  ldfld    class Microsoft.Crm.ServiceBus.IServiceBusChannel Microsoft.Crm.ServiceBus.ServiceBusOneWayClient::channel
0x49f4  callvirt instance void [System.ServiceModel]System.ServiceModel.ICommunicationObject::Open()
0x49f9  ldarg.0
0x49fa  ldc.i4.1
0x49fb  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::set_Status(valuetype Microsoft.Crm.ServiceBus.ClientStatus value)
0x4a00  ret
```
