# Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::CreateEventData

- ea: `0x5460`
- end: `0x54dd`
- name: `Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::CreateEventData`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x4fb0`

## callees

- `0x5360`
- `0x5460`

## pseudocode

```c

```

## disassembly

```asm
0x5460  ldarg.0
0x5461  call     instance valuetype MessageFormatType Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_MessageFormat()
0x5466  stloc.0
0x5467  ldloc.0
0x5468  ldc.i4.1
0x5469  sub
0x546a  switch   loc_547D, loc_549E, loc_5488
0x547b  br.s     loc_54B4
0x547d  ldstr    aBinarySerializ// "Binary Serialization is not supported f"...
0x5482  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x5487  throw
0x5488  ldarg.1
0x5489  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext
0x548e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5493  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.DataContractSerializer::.ctor(class [mscorlib]System.Type)
0x5498  newobj   instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.EventData::.ctor(object, class [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer)
0x549d  ret
0x549e  ldarg.1
0x549f  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext
0x54a4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x54a9  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer::.ctor(class [mscorlib]System.Type)
0x54ae  newobj   instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.EventData::.ctor(object, class [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer)
0x54b3  ret
0x54b4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x54b9  ldstr    aTheValueForMes// "The value for message format '{0}' is n"...
0x54be  ldc.i4.1
0x54bf  newarr   [mscorlib]System.Object
0x54c4  dup
0x54c5  ldc.i4.0
0x54c6  ldarg.0
0x54c7  call     instance valuetype MessageFormatType Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_MessageFormat()
0x54cc  box      MessageFormatType
0x54d1  stelem.ref
0x54d2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x54d7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x54dc  throw
```
