# Microsoft.Crm.ServiceBus.ServiceBusUtility::GetObjectSize

- ea: `0x2700`
- end: `0x2819`
- name: `Microsoft.Crm.ServiceBus.ServiceBusUtility::GetObjectSize`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2820`

## callees

- `0x2700`

## string_xrefs

- `0x27fb`: `SERVICE BUS: ServiceBusUtility.GetObjectSize() failed with {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x2700  ldc.i4.m1
0x2701  conv.i8
0x2702  stloc.0
0x2703  ldarg.3
0x2704  ldnull
0x2705  stind.ref
0x2706  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x270b  stloc.1
0x270c  ldarg.1
0x270d  ldc.i4.1
0x270e  sub
0x270f  switch   loc_2782, loc_2725, loc_2755
0x2720  br       loc_27C2
0x2725  ldarg.0
0x2726  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x272b  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer::.ctor(class [mscorlib]System.Type)
0x2730  ldloc.1
0x2731  ldarg.0
0x2732  callvirt instance void [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::WriteObject(class [mscorlib]System.IO.Stream, object)
0x2737  ldloc.1
0x2738  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x273d  stloc.0
0x273e  ldarg.3
0x273f  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Default()
0x2744  ldloc.1
0x2745  callvirt instance unsigned int8[] [mscorlib]System.IO.MemoryStream::ToArray()
0x274a  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x274f  stind.ref
0x2750  br       loc_27E6
0x2755  ldarg.0
0x2756  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x275b  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.DataContractSerializer::.ctor(class [mscorlib]System.Type)
0x2760  ldloc.1
0x2761  ldarg.0
0x2762  callvirt instance void [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::WriteObject(class [mscorlib]System.IO.Stream, object)
0x2767  ldloc.1
0x2768  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x276d  stloc.0
0x276e  ldarg.3
0x276f  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Default()
0x2774  ldloc.1
0x2775  callvirt instance unsigned int8[] [mscorlib]System.IO.MemoryStream::ToArray()
0x277a  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x277f  stind.ref
0x2780  br.s     loc_27E6
0x2782  ldarg.0
0x2783  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2788  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.DataContractSerializer::.ctor(class [mscorlib]System.Type)
0x278d  stloc.2
0x278e  ldloc.1
0x278f  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::CreateBinaryWriter(class [mscorlib]System.IO.Stream)
0x2794  stloc.3
0x2795  ldloc.2
0x2796  ldloc.3
0x2797  ldarg.0
0x2798  callvirt instance void [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::WriteObject(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter, object)
0x279d  ldloc.1
0x279e  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x27a3  stloc.0
0x27a4  ldarg.3
0x27a5  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Default()
0x27aa  ldloc.1
0x27ab  callvirt instance unsigned int8[] [mscorlib]System.IO.MemoryStream::ToArray()
0x27b0  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x27b5  stind.ref
0x27b6  leave.s  loc_27E6
0x27b8  ldloc.3
0x27b9  brfalse.s loc_27C1
0x27bb  ldloc.3
0x27bc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27c1  endfinally
0x27c2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x27c7  ldstr    aTheValueForMes// "The value for message format '{0}' is n"...
0x27cc  ldc.i4.1
0x27cd  newarr   [mscorlib]System.Object
0x27d2  dup
0x27d3  ldc.i4.0
0x27d4  ldarg.1
0x27d5  box      MessageFormatType
0x27da  stelem.ref
0x27db  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x27e0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x27e5  throw
0x27e6  leave.s  loc_27F2
0x27e8  ldloc.1
0x27e9  brfalse.s loc_27F1
0x27eb  ldloc.1
0x27ec  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27f1  endfinally
0x27f2  leave.s  loc_2817
0x27f4  stloc.s  4
0x27f6  ldloc.s  4
0x27f8  ldarg.2
0x27f9  ldc.i4.s 0x2F
0x27fb  ldstr    aServiceBusServ// "SERVICE BUS: ServiceBusUtility.GetObjec"...
0x2800  ldc.i4.1
0x2801  newarr   [mscorlib]System.Object
0x2806  dup
0x2807  ldc.i4.0
0x2808  ldloc.s  4
0x280a  callvirt instance string [mscorlib]System.Object::ToString()
0x280f  stelem.ref
0x2810  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2815  leave.s  loc_2817
0x2817  ldloc.0
0x2818  ret
```
