# Microsoft.Crm.Sdk.LegacySdkAdapterBase::ConvertToDynamicEntity

- ea: `0x8430`
- end: `0x84e3`
- name: `Microsoft.Crm.Sdk.LegacySdkAdapterBase::ConvertToDynamicEntity`
- size: `179`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xfc20`
- `0xfc70`

## callees

- `0x1460`
- `0x4370`
- `0x8430`
- `0xa990`

## string_xrefs

- `0x84af`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x844c`: `http://schemas.microsoft.com/crm/2007/Entities`

## pseudocode

```c

```

## disassembly

```asm
0x8430  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x8435  stloc.0
0x8436  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::get_Instance()
0x843b  ldarg.1
0x843c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x8441  ldarg.1
0x8442  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x8447  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x844c  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2007/E"...
0x8451  callvirt instance class [System.Xml]System.Xml.Serialization.XmlSerializer [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::GetSerializer(class [mscorlib]System.Type, string, string)
0x8456  stloc.1
0x8457  ldloc.0
0x8458  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x845d  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x8462  stloc.2
0x8463  ldloc.1
0x8464  ldloc.2
0x8465  ldarg.1
0x8466  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializer::Serialize(class [mscorlib]System.IO.TextWriter, object)
0x846b  ldloc.2
0x846c  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x8471  leave.s  loc_847D
0x8473  ldloc.2
0x8474  brfalse.s loc_847C
0x8476  ldloc.2
0x8477  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x847c  endfinally
0x847d  ldloc.0
0x847e  callvirt instance string [mscorlib]System.Object::ToString()
0x8483  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x8488  stloc.3
0x8489  newobj   instance void [System.Xml]System.Xml.XmlReaderSettings::.ctor()
0x848e  stloc.s  4
0x8490  ldloc.s  4
0x8492  ldc.i4.1
0x8493  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_IgnoreWhitespace(bool)
0x8498  ldloc.3
0x8499  ldloc.s  4
0x849b  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader, class [System.Xml]System.Xml.XmlReaderSettings)
0x84a0  stloc.s  5
0x84a2  ldloc.s  5
0x84a4  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x84a9  pop
0x84aa  newobj   instance void Microsoft.Crm.Sdk.Crm2007.Request::.ctor()
0x84af  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0x84b4  ldloc.s  5
0x84b6  ldarg.0
0x84b7  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.LegacySdkAdapterBase::_organizationId
0x84bc  newobj   instance void Microsoft.Crm.Sdk.ParsingContext::.ctor(class Microsoft.Crm.Sdk.RequestBase request, string namespaceName, class [System.Xml]System.Xml.XmlReader reader, valuetype [mscorlib]System.Guid organizationId)
0x84c1  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Sdk.ParserHelper::ParseEntity(class Microsoft.Crm.Sdk.ParsingContext context)
0x84c6  stloc.s  6
0x84c8  leave.s  loc_84E0
0x84ca  ldloc.s  5
0x84cc  brfalse.s loc_84D5
0x84ce  ldloc.s  5
0x84d0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x84d5  endfinally
0x84d6  ldloc.3
0x84d7  brfalse.s loc_84DF
0x84d9  ldloc.3
0x84da  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x84df  endfinally
0x84e0  ldloc.s  6
0x84e2  ret
```
