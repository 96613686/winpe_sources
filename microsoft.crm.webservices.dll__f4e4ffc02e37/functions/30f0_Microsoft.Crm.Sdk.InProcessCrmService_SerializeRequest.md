# Microsoft.Crm.Sdk.InProcessCrmService::SerializeRequest

- ea: `0x30f0`
- end: `0x3124`
- name: `Microsoft.Crm.Sdk.InProcessCrmService::SerializeRequest`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e20`
- `0xfb50`

## callees

- `0x30f0`
- `0x3430`

## pseudocode

```c

```

## disassembly

```asm
0x30f0  ldarg.1
0x30f1  isinst   Microsoft.Crm.Sdk.RequestBase
0x30f6  brfalse.s loc_30F9
0x30f8  ret
0x30f9  ldarg.2
0x30fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x30ff  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x3104  stloc.0
0x3105  call     class [System.Xml]System.Xml.Serialization.XmlSerializer Microsoft.Crm.Sdk.InProcessCrmService::get_RequestSerializer()
0x310a  ldloc.0
0x310b  ldarg.1
0x310c  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializer::Serialize(class [mscorlib]System.IO.TextWriter, object)
0x3111  ldloc.0
0x3112  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x3117  leave.s  loc_3123
0x3119  ldloc.0
0x311a  brfalse.s loc_3122
0x311c  ldloc.0
0x311d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3122  endfinally
0x3123  ret
```
