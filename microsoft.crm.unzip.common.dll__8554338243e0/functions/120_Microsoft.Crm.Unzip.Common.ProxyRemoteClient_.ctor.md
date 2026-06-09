# Microsoft.Crm.Unzip.Common.ProxyRemoteClient::.ctor

- ea: `0x120`
- end: `0x1a2`
- name: `Microsoft.Crm.Unzip.Common.ProxyRemoteClient::.ctor`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1b0`

## pseudocode

```c

```

## disassembly

```asm
0x120  ldarg.0
0x121  call     instance void [mscorlib]System.Object::.ctor()
0x126  newobj   instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::.ctor()
0x12b  dup
0x12c  ldc.i4.0
0x12d  ldc.i4.5
0x12e  ldc.i4.0
0x12f  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x134  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_ReceiveTimeout(valuetype [mscorlib]System.TimeSpan)
0x139  dup
0x13a  ldc.i4.0
0x13b  ldc.i4.5
0x13c  ldc.i4.0
0x13d  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x142  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_SendTimeout(valuetype [mscorlib]System.TimeSpan)
0x147  dup
0x148  ldc.i4   0x640000
0x14d  conv.i8
0x14e  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_MaxReceivedMessageSize(int64)
0x153  dup
0x154  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_ReaderQuotas()
0x159  ldc.i4   0x190000
0x15e  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxArrayLength(int32)
0x163  newobj   instance void class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class Microsoft.Crm.Unzip.Common.IUnzipProxy>::.ctor(class [System.ServiceModel]System.ServiceModel.Channels.Binding)
0x168  stloc.0
0x169  ldloc.0
0x16a  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.CommunicationObject::Open()
0x16f  ldarg.1
0x170  ldc.i4.0
0x171  newarr   [System.ServiceModel]System.ServiceModel.Channels.AddressHeader
0x176  newobj   instance void [System.ServiceModel]System.ServiceModel.EndpointAddress::.ctor(class [System]System.Uri, class [System.ServiceModel]System.ServiceModel.Channels.AddressHeader[])
0x17b  stloc.1
0x17c  ldarg.0
0x17d  ldloc.0
0x17e  ldloc.1
0x17f  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class Microsoft.Crm.Unzip.Common.IUnzipProxy>::CreateChannel(!!T0)
0x184  stfld    class Microsoft.Crm.Unzip.Common.IUnzipProxy Microsoft.Crm.Unzip.Common.ProxyRemoteClient::_proxy
0x189  ldarg.0
0x18a  ldfld    class Microsoft.Crm.Unzip.Common.IUnzipProxy Microsoft.Crm.Unzip.Common.ProxyRemoteClient::_proxy
0x18f  castclass [System.ServiceModel]System.ServiceModel.IContextChannel
0x194  ldc.i4.0
0x195  ldc.i4.5
0x196  ldc.i4.0
0x197  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x19c  callvirt instance void [System.ServiceModel]System.ServiceModel.IContextChannel::set_OperationTimeout(valuetype [mscorlib]System.TimeSpan)
0x1a1  ret
```
