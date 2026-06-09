# Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::ConvertToInternalRequest

- ea: `0x40b0`
- end: `0x4229`
- name: `Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::ConvertToInternalRequest`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xfd80`

## callees

- `0x40b0`
- `0x4790`
- `0x8150`
- `0xa9c0`

## string_xrefs

- `0x40f9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x418d`: `InProcessLegacySdkAdapter starts processing Request {0} Xml:{1}{2}`

## pseudocode

```c

```

## disassembly

```asm
0x40b0  ldarg.1
0x40b1  isinst   Microsoft.Crm.Sdk.RequestBase
0x40b6  stloc.0
0x40b7  ldloc.0
0x40b8  brfalse.s loc_40BC
0x40ba  ldloc.0
0x40bb  ret
0x40bc  ldc.i4.1
0x40bd  stloc.1
0x40be  ldarg.1
0x40bf  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x40c4  ldstr    aReturndynamice// "ReturnDynamicEntities"
0x40c9  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x40ce  stloc.2
0x40cf  ldloc.2
0x40d0  ldnull
0x40d1  call     bool [mscorlib]System.Reflection.PropertyInfo::op_Inequality(class [mscorlib]System.Reflection.PropertyInfo, class [mscorlib]System.Reflection.PropertyInfo)
0x40d6  brfalse.s loc_40E6
0x40d8  ldloc.2
0x40d9  ldarg.1
0x40da  ldnull
0x40db  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x40e0  unbox.any [mscorlib]System.Boolean
0x40e5  stloc.1
0x40e6  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x40eb  stloc.3
0x40ec  ldarg.1
0x40ed  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x40f2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::get_BaseType()
0x40f7  stloc.s  4
0x40f9  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0x40fe  stloc.s  5
0x4100  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::get_Instance()
0x4105  ldloc.s  4
0x4107  ldloc.s  4
0x4109  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x410e  ldloc.s  5
0x4110  callvirt instance class [System.Xml]System.Xml.Serialization.XmlSerializer [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::GetSerializer(class [mscorlib]System.Type, string, string)
0x4115  stloc.s  6
0x4117  ldloc.3
0x4118  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x411d  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x4122  stloc.s  7
0x4124  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x4129  stloc.s  8
0x412b  ldloc.s  8
0x412d  ldc.i4.1
0x412e  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x4133  ldloc.s  7
0x4135  ldloc.s  8
0x4137  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.IO.TextWriter, class [System.Xml]System.Xml.XmlWriterSettings)
0x413c  stloc.s  9
0x413e  ldloc.s  9
0x4140  ldstr    aRoot// "root"
0x4145  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x414a  ldloc.s  6
0x414c  ldloc.s  9
0x414e  ldarg.1
0x414f  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializer::Serialize(class [System.Xml]System.Xml.XmlWriter, object)
0x4154  ldloc.s  9
0x4156  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x415b  ldloc.s  9
0x415d  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x4162  leave.s  loc_4170
0x4164  ldloc.s  9
0x4166  brfalse.s loc_416F
0x4168  ldloc.s  9
0x416a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x416f  endfinally
0x4170  ldloc.s  7
0x4172  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x4177  leave.s  loc_4185
0x4179  ldloc.s  7
0x417b  brfalse.s loc_4184
0x417d  ldloc.s  7
0x417f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4184  endfinally
0x4185  ldarg.0
0x4186  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.LegacySdkAdapterBase::get_OrganizationId()
0x418b  ldc.i4.s 0x1A
0x418d  ldstr    aInprocesslegac// "InProcessLegacySdkAdapter starts proces"...
0x4192  ldc.i4.3
0x4193  newarr   [mscorlib]System.Object
0x4198  dup
0x4199  ldc.i4.0
0x419a  ldarg.1
0x419b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x41a0  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x41a5  stelem.ref
0x41a6  dup
0x41a7  ldc.i4.1
0x41a8  call     string [mscorlib]System.Environment::get_NewLine()
0x41ad  stelem.ref
0x41ae  dup
0x41af  ldc.i4.2
0x41b0  ldloc.3
0x41b1  stelem.ref
0x41b2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x41b7  ldarg.1
0x41b8  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x41bd  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x41c2  ldloc.1
0x41c3  ldarg.0
0x41c4  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.LegacySdkAdapterBase::get_OrganizationId()
0x41c9  newobj   instance void Microsoft.Crm.Sdk.Crm2007.Request::.ctor(string requestName, bool returnDynamicEntities, valuetype [mscorlib]System.Guid organizationId)
0x41ce  stloc.0
0x41cf  ldloc.3
0x41d0  callvirt instance string [mscorlib]System.Object::ToString()
0x41d5  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x41da  stloc.s  0xA
0x41dc  newobj   instance void [System.Xml]System.Xml.XmlReaderSettings::.ctor()
0x41e1  stloc.s  0xB
0x41e3  ldloc.s  0xB
0x41e5  ldc.i4.1
0x41e6  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_IgnoreWhitespace(bool)
0x41eb  ldloc.s  0xA
0x41ed  ldloc.s  0xB
0x41ef  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader, class [System.Xml]System.Xml.XmlReaderSettings)
0x41f4  stloc.s  0xC
0x41f6  ldloc.s  0xC
0x41f8  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x41fd  ldloc.s  0xC
0x41ff  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x4204  pop
0x4205  ldloc.0
0x4206  ldloc.s  0xC
0x4208  callvirt instance void Microsoft.Crm.Sdk.RequestBase::ReadXml(class [System.Xml]System.Xml.XmlReader reader)
0x420d  leave.s  loc_4227
0x420f  ldloc.s  0xC
0x4211  brfalse.s loc_421A
0x4213  ldloc.s  0xC
0x4215  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x421a  endfinally
0x421b  ldloc.s  0xA
0x421d  brfalse.s loc_4226
0x421f  ldloc.s  0xA
0x4221  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4226  endfinally
0x4227  ldloc.0
0x4228  ret
```
