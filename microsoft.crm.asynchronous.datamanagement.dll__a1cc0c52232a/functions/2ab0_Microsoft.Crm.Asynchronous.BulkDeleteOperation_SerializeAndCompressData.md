# Microsoft.Crm.Asynchronous.BulkDeleteOperation::SerializeAndCompressData

- ea: `0x2ab0`
- end: `0x2aed`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::SerializeAndCompressData`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1f350`

## callees

- `0x2ab0`

## pseudocode

```c

```

## disassembly

```asm
0x2ab0  ldtoken  [Microsoft.Crm]Microsoft.Crm.BulkDeleteChildData
0x2ab5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2aba  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type)
0x2abf  stloc.0
0x2ac0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2ac5  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x2aca  stloc.1
0x2acb  ldloc.0
0x2acc  ldloc.1
0x2acd  ldarg.1
0x2ace  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializer::Serialize(class [mscorlib]System.IO.TextWriter, object)
0x2ad3  ldloc.1
0x2ad4  callvirt instance string [mscorlib]System.Object::ToString()
0x2ad9  call     string [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.DataCompressionHelper::CompressData(string)
0x2ade  stloc.2
0x2adf  leave.s  loc_2AEB
0x2ae1  ldloc.1
0x2ae2  brfalse.s loc_2AEA
0x2ae4  ldloc.1
0x2ae5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2aea  endfinally
0x2aeb  ldloc.2
0x2aec  ret
```
