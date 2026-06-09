# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write977_ExportCompressedXmlRequest

- ea: `0x4e180`
- end: `0x4e248`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write977_ExportCompressedXmlRequest`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x4e180`

## string_xrefs

- `0x4e1c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4e1df`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4e1f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4e21a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4e230`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4e215`: `ParameterXml`
- `0x4e1c0`: `ExportCompressedXmlRequest`

## pseudocode

```c

```

## disassembly

```asm
0x4e180  ldarg.3
0x4e181  brtrue.s loc_4E190
0x4e183  ldarg.s  4
0x4e185  brfalse.s loc_4E18F
0x4e187  ldarg.0
0x4e188  ldarg.1
0x4e189  ldarg.2
0x4e18a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4e18f  ret
0x4e190  ldarg.s  5
0x4e192  brtrue.s loc_4E1B0
0x4e194  ldarg.3
0x4e195  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4e19a  stloc.0
0x4e19b  ldloc.0
0x4e19c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ExportCompressedXmlRequest
0x4e1a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e1a6  beq.s    loc_4E1B0
0x4e1a8  ldarg.0
0x4e1a9  ldarg.3
0x4e1aa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4e1af  throw
0x4e1b0  ldarg.0
0x4e1b1  ldarg.1
0x4e1b2  ldarg.2
0x4e1b3  ldarg.3
0x4e1b4  ldc.i4.0
0x4e1b5  ldnull
0x4e1b6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4e1bb  ldarg.s  5
0x4e1bd  brfalse.s loc_4E1CF
0x4e1bf  ldarg.0
0x4e1c0  ldstr    aExportcompress// "ExportCompressedXmlRequest"
0x4e1c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4e1ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4e1cf  ldarg.3
0x4e1d0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4e1d5  stloc.1
0x4e1d6  ldloc.1
0x4e1d7  brfalse.s loc_4E214
0x4e1d9  ldarg.0
0x4e1da  ldstr    aOptionalparame_0// "OptionalParameters"
0x4e1df  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4e1e4  ldnull
0x4e1e5  ldc.i4.0
0x4e1e6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4e1eb  ldc.i4.0
0x4e1ec  stloc.2
0x4e1ed  br.s     loc_4E208
0x4e1ef  ldarg.0
0x4e1f0  ldstr    aOptionalparame// "OptionalParameter"
0x4e1f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4e1fa  ldloc.1
0x4e1fb  ldloc.2
0x4e1fc  ldelem.ref
0x4e1fd  ldc.i4.1
0x4e1fe  ldc.i4.0
0x4e1ff  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4e204  ldloc.2
0x4e205  ldc.i4.1
0x4e206  add
0x4e207  stloc.2
0x4e208  ldloc.2
0x4e209  ldloc.1
0x4e20a  ldlen
0x4e20b  conv.i4
0x4e20c  blt.s    loc_4E1EF
0x4e20e  ldarg.0
0x4e20f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4e214  ldarg.0
0x4e215  ldstr    aParameterxml_0// "ParameterXml"
0x4e21a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4e21f  ldarg.3
0x4e220  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ExportCompressedXmlRequest::get_ParameterXml()
0x4e225  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4e22a  ldarg.0
0x4e22b  ldstr    aEmbeddedfilena// "EmbeddedFileName"
0x4e230  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4e235  ldarg.3
0x4e236  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ExportCompressedXmlRequest::get_EmbeddedFileName()
0x4e23b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4e240  ldarg.0
0x4e241  ldarg.3
0x4e242  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4e247  ret
```
