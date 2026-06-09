# Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::Close

- ea: `0x5260`
- end: `0x52b9`
- name: `Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::Close`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1470`
- `0x4830`
- `0x5260`
- `0x52c0`
- `0x52e0`

## pseudocode

```c

```

## disassembly

```asm
0x5260  ldarg.0
0x5261  call     instance class Microsoft.Crm.ServiceBus.IMessagingFactory Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_MessagingFactory()
0x5266  callvirt instance void Microsoft.Crm.ServiceBus.IMessagingFactory::Close()
0x526b  leave.s  loc_52B8
0x526d  stloc.0
0x526e  ldarg.0
0x526f  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_EndPointInfo()
0x5274  brfalse.s loc_5283
0x5276  ldarg.0
0x5277  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_EndPointInfo()
0x527c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_OrganizationId()
0x5281  br.s     loc_5288
0x5283  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5288  ldc.i4.s 0x2F
0x528a  ldstr    a0// "{0}"
0x528f  ldc.i4.1
0x5290  newarr   [mscorlib]System.Object
0x5295  dup
0x5296  ldc.i4.0
0x5297  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x529c  ldstr    aExceptionWhenT// "Exception when trying to close the mess"...
0x52a1  ldc.i4.1
0x52a2  newarr   [mscorlib]System.Object
0x52a7  dup
0x52a8  ldc.i4.0
0x52a9  ldloc.0
0x52aa  stelem.ref
0x52ab  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x52b0  stelem.ref
0x52b1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x52b6  leave.s  loc_52B8
0x52b8  ret
```
