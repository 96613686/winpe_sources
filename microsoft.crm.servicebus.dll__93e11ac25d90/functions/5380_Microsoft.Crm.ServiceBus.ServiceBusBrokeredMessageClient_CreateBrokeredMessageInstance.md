# Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::CreateBrokeredMessageInstance

- ea: `0x5380`
- end: `0x53f9`
- name: `Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::CreateBrokeredMessageInstance`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x50e0`

## callees

- `0x5360`
- `0x5380`

## pseudocode

```c

```

## disassembly

```asm
0x5380  ldarg.0
0x5381  call     instance valuetype MessageFormatType Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_MessageFormat()
0x5386  stloc.0
0x5387  ldloc.0
0x5388  ldc.i4.1
0x5389  sub
0x538a  switch   loc_539D, loc_53BA, loc_53A4
0x539b  br.s     loc_53D0
0x539d  ldarg.1
0x539e  newobj   instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.BrokeredMessage::.ctor(object)
0x53a3  ret
0x53a4  ldarg.1
0x53a5  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext
0x53aa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53af  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.DataContractSerializer::.ctor(class [mscorlib]System.Type)
0x53b4  newobj   instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.BrokeredMessage::.ctor(object, class [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer)
0x53b9  ret
0x53ba  ldarg.1
0x53bb  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext
0x53c0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53c5  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer::.ctor(class [mscorlib]System.Type)
0x53ca  newobj   instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.BrokeredMessage::.ctor(object, class [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer)
0x53cf  ret
0x53d0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x53d5  ldstr    aTheValueForMes// "The value for message format '{0}' is n"...
0x53da  ldc.i4.1
0x53db  newarr   [mscorlib]System.Object
0x53e0  dup
0x53e1  ldc.i4.0
0x53e2  ldarg.0
0x53e3  call     instance valuetype MessageFormatType Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_MessageFormat()
0x53e8  box      MessageFormatType
0x53ed  stelem.ref
0x53ee  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x53f3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x53f8  throw
```
