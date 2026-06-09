# Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::ConvertToInternalMetadataRequest

- ea: `0x3de0`
- end: `0x3e98`
- name: `Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::ConvertToInternalMetadataRequest`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xfe40`

## callees

- `0x3de0`

## string_xrefs

- `0x3df4`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x3de0  ldnull
0x3de1  stloc.0
0x3de2  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3de7  stloc.1
0x3de8  ldarg.1
0x3de9  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3dee  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::get_BaseType()
0x3df3  stloc.2
0x3df4  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0x3df9  stloc.3
0x3dfa  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::get_Instance()
0x3dff  ldloc.2
0x3e00  ldloc.2
0x3e01  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3e06  ldloc.3
0x3e07  ldloc.2
0x3e08  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x3e0d  ldloc.2
0x3e0e  callvirt instance class [System.Xml]System.Xml.Serialization.XmlSerializer [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::GetSerializer(class [mscorlib]System.Type, string, string, class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Type)
0x3e13  stloc.s  4
0x3e15  ldloc.1
0x3e16  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3e1b  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x3e20  stloc.s  7
0x3e22  ldloc.s  4
0x3e24  ldloc.s  7
0x3e26  ldarg.1
0x3e27  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializer::Serialize(class [mscorlib]System.IO.TextWriter, object)
0x3e2c  ldloc.s  7
0x3e2e  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x3e33  leave.s  loc_3E41
0x3e35  ldloc.s  7
0x3e37  brfalse.s loc_3E40
0x3e39  ldloc.s  7
0x3e3b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3e40  endfinally
0x3e41  ldtoken  Microsoft.Crm.Sdk.Crm2007.MetadataServiceRequest
0x3e46  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3e4b  stloc.s  5
0x3e4d  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::get_Instance()
0x3e52  ldloc.s  5
0x3e54  ldloc.s  5
0x3e56  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3e5b  ldloc.3
0x3e5c  ldloc.s  5
0x3e5e  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x3e63  ldloc.s  5
0x3e65  callvirt instance class [System.Xml]System.Xml.Serialization.XmlSerializer [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::GetSerializer(class [mscorlib]System.Type, string, string, class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Type)
0x3e6a  stloc.s  6
0x3e6c  ldloc.1
0x3e6d  callvirt instance string [mscorlib]System.Object::ToString()
0x3e72  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x3e77  stloc.s  8
0x3e79  ldloc.s  6
0x3e7b  ldloc.s  8
0x3e7d  callvirt instance object [System.Xml]System.Xml.Serialization.XmlSerializer::Deserialize(class [mscorlib]System.IO.TextReader)
0x3e82  castclass Microsoft.Crm.Sdk.Crm2007.MetadataServiceRequest
0x3e87  stloc.0
0x3e88  leave.s  loc_3E96
0x3e8a  ldloc.s  8
0x3e8c  brfalse.s loc_3E95
0x3e8e  ldloc.s  8
0x3e90  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3e95  endfinally
0x3e96  ldloc.0
0x3e97  ret
```
