# Microsoft.Crm.ServiceBus.TokenClientBehaviorStrategy::RetrieveClientBehavior

- ea: `0x3a60`
- end: `0x3abc`
- name: `Microsoft.Crm.ServiceBus.TokenClientBehaviorStrategy::RetrieveClientBehavior`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1430`
- `0x3a30`
- `0x3a60`
- `0x3ac0`
- `0x5590`
- `0x5d30`

## pseudocode

```c

```

## disassembly

```asm
0x3a60  newobj   instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.TransportClientEndpointBehavior::.ctor()
0x3a65  dup
0x3a66  ldarg.0
0x3a67  call     instance class [Microsoft.ServiceBus]Microsoft.ServiceBus.TokenProvider Microsoft.Crm.ServiceBus.TokenClientBehaviorStrategy::GetTokenProvider()
0x3a6c  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.TransportClientEndpointBehavior::set_TokenProvider(class [Microsoft.ServiceBus]Microsoft.ServiceBus.TokenProvider)
0x3a71  stloc.0
0x3a72  ldarg.0
0x3a73  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.AuthClientBehaviorStrategy::get_EndpointInfo()
0x3a78  callvirt instance bool Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_IsFederatedMode()
0x3a7d  brfalse.s loc_3AAA
0x3a7f  ldarg.0
0x3a80  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.AuthClientBehaviorStrategy::get_EndpointInfo()
0x3a85  newobj   instance void Microsoft.Crm.ServiceBus.TokenProvider::.ctor(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x3a8a  ldc.i4.0
0x3a8b  newobj   instance void Microsoft.Crm.ServiceBus.TokenPusher::.ctor(class Microsoft.Crm.ServiceBus.TokenProvider tokenProvider, bool forServiceBusScope)
0x3a90  stloc.1
0x3a91  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::.ctor()
0x3a96  dup
0x3a97  ldloc.0
0x3a98  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::Add(var<u1>)
0x3a9d  dup
0x3a9e  ldloc.1
0x3a9f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::Add(var<u1>)
0x3aa4  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::AsReadOnly()
0x3aa9  ret
0x3aaa  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::.ctor()
0x3aaf  dup
0x3ab0  ldloc.0
0x3ab1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::Add(var<u1>)
0x3ab6  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::AsReadOnly()
0x3abb  ret
```
