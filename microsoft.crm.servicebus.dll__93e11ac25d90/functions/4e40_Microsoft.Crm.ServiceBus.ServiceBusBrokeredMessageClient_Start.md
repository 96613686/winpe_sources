# Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::Start

- ea: `0x4e40`
- end: `0x4f0e`
- name: `Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::Start`
- size: `206`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callees

- `0x13f0`
- `0x1410`
- `0x1450`
- `0x1470`
- `0x1530`
- `0x15d0`
- `0x15f0`
- `0x3e30`
- `0x4500`
- `0x4e40`
- `0x52c0`
- `0x52d0`
- `0x52f0`
- `0x5310`
- `0x5320`
- `0x5330`
- `0x5340`
- `0x5350`
- `0x5370`
- `0x54e0`

## pseudocode

```c

```

## disassembly

```asm
0x4e40  ldarg.0
0x4e41  ldarg.1
0x4e42  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::Start(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x4e47  ldarg.0
0x4e48  ldarg.1
0x4e49  call     instance void Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::set_EndPointInfo(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation value)
0x4e4e  ldarg.0
0x4e4f  ldarg.1
0x4e50  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_Path()
0x4e55  call     instance void Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::set_EntityPath(string value)
0x4e5a  ldarg.0
0x4e5b  ldarg.1
0x4e5c  callvirt instance valuetype NamespaceFormatType Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_NamespaceFormat()
0x4e61  call     instance void Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::set_NamespaceFormat(valuetype NamespaceFormatType value)
0x4e66  ldarg.0
0x4e67  ldarg.1
0x4e68  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_NamespaceAddress()
0x4e6d  call     instance void Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::set_NamespaceAddress(string value)
0x4e72  ldarg.0
0x4e73  ldarg.1
0x4e74  callvirt instance valuetype MessageFormatType Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_MessageFormat()
0x4e79  call     instance void Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::set_MessageFormat(valuetype MessageFormatType value)
0x4e7e  ldnull
0x4e7f  stloc.0
0x4e80  ldarg.0
0x4e81  ldarg.1
0x4e82  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_OrganizationId()
0x4e87  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::GetServiceBusOperationTimeout(valuetype [mscorlib]System.Guid organizationId)
0x4e8c  stloc.1
0x4e8d  ldarg.0
0x4e8e  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_EndPointInfo()
0x4e93  callvirt instance valuetype ContractType Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_Contract()
0x4e98  ldc.i4.7
0x4e99  bne.un.s loc_4EB1
0x4e9b  newobj   instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.MessagingFactorySettings::.ctor()
0x4ea0  dup
0x4ea1  ldloc.1
0x4ea2  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.MessagingFactorySettings::set_OperationTimeout(valuetype [mscorlib]System.TimeSpan)
0x4ea7  dup
0x4ea8  ldc.i4.1
0x4ea9  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.MessagingFactorySettings::set_TransportType(valuetype [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.TransportType)
0x4eae  stloc.0
0x4eaf  br.s     loc_4EBE
0x4eb1  newobj   instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.MessagingFactorySettings::.ctor()
0x4eb6  dup
0x4eb7  ldloc.1
0x4eb8  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.MessagingFactorySettings::set_OperationTimeout(valuetype [mscorlib]System.TimeSpan)
0x4ebd  stloc.0
0x4ebe  ldarg.0
0x4ebf  call     T0x2B000005
0x4ec4  stloc.2
0x4ec5  ldloc.0
0x4ec6  ldloc.2
0x4ec7  callvirt instance class [Microsoft.ServiceBus]Microsoft.ServiceBus.TokenProvider [Microsoft.ServiceBus]Microsoft.ServiceBus.TransportClientEndpointBehavior::get_TokenProvider()
0x4ecc  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.MessagingFactorySettings::set_TokenProvider(class [Microsoft.ServiceBus]Microsoft.ServiceBus.TokenProvider)
0x4ed1  ldnull
0x4ed2  stloc.3
0x4ed3  ldarg.0
0x4ed4  call     instance valuetype NamespaceFormatType Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_NamespaceFormat()
0x4ed9  ldc.i4.2
0x4eda  bne.un.s loc_4EEA
0x4edc  ldarg.0
0x4edd  call     instance string Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_NamespaceAddress()
0x4ee2  newobj   instance void [System]System.Uri::.ctor(string)
0x4ee7  stloc.3
0x4ee8  br.s     loc_4F00
0x4eea  ldstr    aSb// "sb"
0x4eef  ldarg.1
0x4ef0  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_SolutionName()
0x4ef5  ldsfld   string [mscorlib]System.String::Empty
0x4efa  call     class [System]System.Uri [Microsoft.ServiceBus]Microsoft.ServiceBus.ServiceBusEnvironment::CreateServiceUri(string, string, string)
0x4eff  stloc.3
0x4f00  ldarg.0
0x4f01  ldloc.3
0x4f02  ldloc.0
0x4f03  call     class Microsoft.Crm.ServiceBus.IMessagingFactory Microsoft.Crm.ServiceBus.MessagingFactoryFactory::Create(class [System]System.Uri namespaceUri, class [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.MessagingFactorySettings settings)
0x4f08  call     instance void Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::set_MessagingFactory(class Microsoft.Crm.ServiceBus.IMessagingFactory value)
0x4f0d  ret
```
