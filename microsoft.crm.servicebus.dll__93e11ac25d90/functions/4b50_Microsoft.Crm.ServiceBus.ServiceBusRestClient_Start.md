# Microsoft.Crm.ServiceBus.ServiceBusRestClient::Start

- ea: `0x4b50`
- end: `0x4bf0`
- name: `Microsoft.Crm.ServiceBus.ServiceBusRestClient::Start`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x4500`
- `0x4650`
- `0x4670`
- `0x4690`
- `0x46a0`
- `0x4b50`
- `0x6860`

## pseudocode

```c

```

## disassembly

```asm
0x4b50  ldarg.0
0x4b51  ldarg.1
0x4b52  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::Start(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x4b57  ldarg.0
0x4b58  ldarg.0
0x4b59  call     instance class [System.ServiceModel]System.ServiceModel.Channels.Binding Microsoft.Crm.ServiceBus.ServiceBusClientBase::get_EndpointBinding()
0x4b5e  ldarg.0
0x4b5f  call     instance class [System.ServiceModel]System.ServiceModel.EndpointAddress Microsoft.Crm.ServiceBus.ServiceBusClientBase::get_ServiceEndpointAddress()
0x4b64  callvirt instance class [System]System.Uri [System.ServiceModel]System.ServiceModel.EndpointAddress::get_Uri()
0x4b69  newobj   instance void class [System.ServiceModel.Web]System.ServiceModel.Web.WebChannelFactory`1<class Microsoft.Crm.ServiceBus.IWebHttpServiceBusChannel>::.ctor(class [System.ServiceModel]System.ServiceModel.Channels.Binding, class [System]System.Uri)
0x4b6e  stfld    class [System.ServiceModel.Web]System.ServiceModel.Web.WebChannelFactory`1<class Microsoft.Crm.ServiceBus.IWebHttpServiceBusChannel> Microsoft.Crm.ServiceBus.ServiceBusRestClient::channelFactory
0x4b73  ldarg.0
0x4b74  call     instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> Microsoft.Crm.ServiceBus.ServiceBusClientBase::get_EndpointBehaviors()
0x4b79  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::GetEnumerator()
0x4b7e  stloc.0
0x4b7f  br.s     loc_4B9E
0x4b81  ldloc.0
0x4b82  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::get_Current()
0x4b87  stloc.1
0x4b88  ldarg.0
0x4b89  ldfld    class [System.ServiceModel.Web]System.ServiceModel.Web.WebChannelFactory`1<class Microsoft.Crm.ServiceBus.IWebHttpServiceBusChannel> Microsoft.Crm.ServiceBus.ServiceBusRestClient::channelFactory
0x4b8e  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint [System.ServiceModel]System.ServiceModel.ChannelFactory::get_Endpoint()
0x4b93  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Behaviors()
0x4b98  ldloc.1
0x4b99  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::Add(var<u1>)
0x4b9e  ldloc.0
0x4b9f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4ba4  brtrue.s loc_4B81
0x4ba6  leave.s  loc_4BB2
0x4ba8  ldloc.0
0x4ba9  brfalse.s loc_4BB1
0x4bab  ldloc.0
0x4bac  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4bb1  endfinally
0x4bb2  ldarg.0
0x4bb3  ldfld    class [System.ServiceModel.Web]System.ServiceModel.Web.WebChannelFactory`1<class Microsoft.Crm.ServiceBus.IWebHttpServiceBusChannel> Microsoft.Crm.ServiceBus.ServiceBusRestClient::channelFactory
0x4bb8  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint [System.ServiceModel]System.ServiceModel.ChannelFactory::get_Endpoint()
0x4bbd  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Behaviors()
0x4bc2  newobj   instance void FaultingWebHttpBehavior::.ctor()
0x4bc7  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::Add(var<u1>)
0x4bcc  ldarg.0
0x4bcd  ldarg.0
0x4bce  ldfld    class [System.ServiceModel.Web]System.ServiceModel.Web.WebChannelFactory`1<class Microsoft.Crm.ServiceBus.IWebHttpServiceBusChannel> Microsoft.Crm.ServiceBus.ServiceBusRestClient::channelFactory
0x4bd3  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class Microsoft.Crm.ServiceBus.IWebHttpServiceBusChannel>::CreateChannel()
0x4bd8  stfld    class Microsoft.Crm.ServiceBus.IWebHttpServiceBusChannel Microsoft.Crm.ServiceBus.ServiceBusRestClient::channel
0x4bdd  ldarg.0
0x4bde  ldfld    class Microsoft.Crm.ServiceBus.IWebHttpServiceBusChannel Microsoft.Crm.ServiceBus.ServiceBusRestClient::channel
0x4be3  callvirt instance void [System.ServiceModel]System.ServiceModel.ICommunicationObject::Open()
0x4be8  ldarg.0
0x4be9  ldc.i4.1
0x4bea  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::set_Status(valuetype Microsoft.Crm.ServiceBus.ClientStatus value)
0x4bef  ret
```
