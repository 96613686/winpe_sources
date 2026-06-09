# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write937_ImportMappingsImportMapRequest

- ea: `0x4bf80`
- end: `0x4c04d`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write937_ImportMappingsImportMapRequest`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x4bf80`

## string_xrefs

- `0x4bfc5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4bfdf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4bff5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c01a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c030`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c015`: `MappingsXml`
- `0x4c02b`: `ReplaceIds`

## pseudocode

```c

```

## disassembly

```asm
0x4bf80  ldarg.3
0x4bf81  brtrue.s loc_4BF90
0x4bf83  ldarg.s  4
0x4bf85  brfalse.s loc_4BF8F
0x4bf87  ldarg.0
0x4bf88  ldarg.1
0x4bf89  ldarg.2
0x4bf8a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4bf8f  ret
0x4bf90  ldarg.s  5
0x4bf92  brtrue.s loc_4BFB0
0x4bf94  ldarg.3
0x4bf95  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4bf9a  stloc.0
0x4bf9b  ldloc.0
0x4bf9c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportMappingsImportMapRequest
0x4bfa1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4bfa6  beq.s    loc_4BFB0
0x4bfa8  ldarg.0
0x4bfa9  ldarg.3
0x4bfaa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4bfaf  throw
0x4bfb0  ldarg.0
0x4bfb1  ldarg.1
0x4bfb2  ldarg.2
0x4bfb3  ldarg.3
0x4bfb4  ldc.i4.0
0x4bfb5  ldnull
0x4bfb6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4bfbb  ldarg.s  5
0x4bfbd  brfalse.s loc_4BFCF
0x4bfbf  ldarg.0
0x4bfc0  ldstr    aImportmappings// "ImportMappingsImportMapRequest"
0x4bfc5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4bfca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4bfcf  ldarg.3
0x4bfd0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4bfd5  stloc.1
0x4bfd6  ldloc.1
0x4bfd7  brfalse.s loc_4C014
0x4bfd9  ldarg.0
0x4bfda  ldstr    aOptionalparame_0// "OptionalParameters"
0x4bfdf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4bfe4  ldnull
0x4bfe5  ldc.i4.0
0x4bfe6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4bfeb  ldc.i4.0
0x4bfec  stloc.2
0x4bfed  br.s     loc_4C008
0x4bfef  ldarg.0
0x4bff0  ldstr    aOptionalparame// "OptionalParameter"
0x4bff5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4bffa  ldloc.1
0x4bffb  ldloc.2
0x4bffc  ldelem.ref
0x4bffd  ldc.i4.1
0x4bffe  ldc.i4.0
0x4bfff  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4c004  ldloc.2
0x4c005  ldc.i4.1
0x4c006  add
0x4c007  stloc.2
0x4c008  ldloc.2
0x4c009  ldloc.1
0x4c00a  ldlen
0x4c00b  conv.i4
0x4c00c  blt.s    loc_4BFEF
0x4c00e  ldarg.0
0x4c00f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4c014  ldarg.0
0x4c015  ldstr    aMappingsxml// "MappingsXml"
0x4c01a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c01f  ldarg.3
0x4c020  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportMappingsImportMapRequest::get_MappingsXml()
0x4c025  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4c02a  ldarg.0
0x4c02b  ldstr    aReplaceids// "ReplaceIds"
0x4c030  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c035  ldarg.3
0x4c036  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportMappingsImportMapRequest::get_ReplaceIds()
0x4c03b  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x4c040  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4c045  ldarg.0
0x4c046  ldarg.3
0x4c047  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4c04c  ret
```
