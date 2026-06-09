# Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::MessageContentType

- ea: `0x5400`
- end: `0x5458`
- name: `Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::MessageContentType`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4fb0`
- `0x50e0`

## callees

- `0x5360`
- `0x5400`

## string_xrefs

- `0x5423`: `application/xml`
- `0x5429`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0x5400  ldarg.0
0x5401  call     instance valuetype MessageFormatType Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_MessageFormat()
0x5406  stloc.0
0x5407  ldloc.0
0x5408  ldc.i4.1
0x5409  sub
0x540a  switch   loc_541D, loc_5429, loc_5423
0x541b  br.s     loc_542F
0x541d  ldstr    aApplicationMsb// "application/msbin1"
0x5422  ret
0x5423  ldstr    aApplicationXml// "application/xml"
0x5428  ret
0x5429  ldstr    aApplicationJso// "application/json"
0x542e  ret
0x542f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5434  ldstr    aTheValueForMes// "The value for message format '{0}' is n"...
0x5439  ldc.i4.1
0x543a  newarr   [mscorlib]System.Object
0x543f  dup
0x5440  ldc.i4.0
0x5441  ldarg.0
0x5442  call     instance valuetype MessageFormatType Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_MessageFormat()
0x5447  box      MessageFormatType
0x544c  stelem.ref
0x544d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5452  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x5457  throw
```
