# Microsoft.Crm.ServiceBus.ServiceBusTwoWayClient::Start

- ea: `0x4d10`
- end: `0x4d91`
- name: `Microsoft.Crm.ServiceBus.ServiceBusTwoWayClient::Start`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x4500`
- `0x4650`
- `0x4670`
- `0x4690`
- `0x46a0`
- `0x4d10`

## pseudocode

```c

```

## disassembly

```asm
0x4d10  ldarg.0
0x4d11  ldarg.1
0x4d12  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::Start(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x4d17  ldarg.0
0x4d18  ldarg.0
0x4d19  call     instance class [System.ServiceModel]System.ServiceModel.Channels.Binding Microsoft.Crm.ServiceBus.ServiceBusClientBase::get_EndpointBinding()
0x4d1e  ldarg.0
0x4d1f  call     instance class [System.ServiceModel]System.ServiceModel.EndpointAddress Microsoft.Crm.ServiceBus.ServiceBusClientBase::get_ServiceEndpointAddress()
0x4d24  newobj   instance void class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class Microsoft.Crm.ServiceBus.ITwoWayServiceBusChannel>::.ctor(class [System.ServiceModel]System.ServiceModel.Channels.Binding, class [System.ServiceModel]System.ServiceModel.EndpointAddress)
0x4d29  stfld    class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class Microsoft.Crm.ServiceBus.ITwoWayServiceBusChannel> Microsoft.Crm.ServiceBus.ServiceBusTwoWayClient::channelFactory
0x4d2e  ldarg.0
0x4d2f  call     instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> Microsoft.Crm.ServiceBus.ServiceBusClientBase::get_EndpointBehaviors()
0x4d34  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::GetEnumerator()
0x4d39  stloc.0
0x4d3a  br.s     loc_4D59
0x4d3c  ldloc.0
0x4d3d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::get_Current()
0x4d42  stloc.1
0x4d43  ldarg.0
0x4d44  ldfld    class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class Microsoft.Crm.ServiceBus.ITwoWayServiceBusChannel> Microsoft.Crm.ServiceBus.ServiceBusTwoWayClient::channelFactory
0x4d49  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint [System.ServiceModel]System.ServiceModel.ChannelFactory::get_Endpoint()
0x4d4e  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Behaviors()
0x4d53  ldloc.1
0x4d54  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::Add(var<u1>)
0x4d59  ldloc.0
0x4d5a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4d5f  brtrue.s loc_4D3C
0x4d61  leave.s  loc_4D6D
0x4d63  ldloc.0
0x4d64  brfalse.s loc_4D6C
0x4d66  ldloc.0
0x4d67  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d6c  endfinally
0x4d6d  ldarg.0
0x4d6e  ldarg.0
0x4d6f  ldfld    class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class Microsoft.Crm.ServiceBus.ITwoWayServiceBusChannel> Microsoft.Crm.ServiceBus.ServiceBusTwoWayClient::channelFactory
0x4d74  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class Microsoft.Crm.ServiceBus.ITwoWayServiceBusChannel>::CreateChannel()
0x4d79  stfld    class Microsoft.Crm.ServiceBus.ITwoWayServiceBusChannel Microsoft.Crm.ServiceBus.ServiceBusTwoWayClient::channel
0x4d7e  ldarg.0
0x4d7f  ldfld    class Microsoft.Crm.ServiceBus.ITwoWayServiceBusChannel Microsoft.Crm.ServiceBus.ServiceBusTwoWayClient::channel
0x4d84  callvirt instance void [System.ServiceModel]System.ServiceModel.ICommunicationObject::Open()
0x4d89  ldarg.0
0x4d8a  ldc.i4.1
0x4d8b  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::set_Status(valuetype Microsoft.Crm.ServiceBus.ClientStatus value)
0x4d90  ret
```
