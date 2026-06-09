# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write940_Item

- ea: `0x4c210`
- end: `0x4c2e2`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write940_Item`
- size: `210`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x4c210`

## string_xrefs

- `0x4c255`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c26f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c285`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c2aa`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c2c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c250`: `ImportCompressedTranslationsXmlWithProgressRequest`
- `0x4c2a5`: `CompressedTranslationsXml`

## pseudocode

```c

```

## disassembly

```asm
0x4c210  ldarg.3
0x4c211  brtrue.s loc_4C220
0x4c213  ldarg.s  4
0x4c215  brfalse.s loc_4C21F
0x4c217  ldarg.0
0x4c218  ldarg.1
0x4c219  ldarg.2
0x4c21a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4c21f  ret
0x4c220  ldarg.s  5
0x4c222  brtrue.s loc_4C240
0x4c224  ldarg.3
0x4c225  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4c22a  stloc.0
0x4c22b  ldloc.0
0x4c22c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportCompressedTranslationsXmlWithProgressRequest
0x4c231  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4c236  beq.s    loc_4C240
0x4c238  ldarg.0
0x4c239  ldarg.3
0x4c23a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4c23f  throw
0x4c240  ldarg.0
0x4c241  ldarg.1
0x4c242  ldarg.2
0x4c243  ldarg.3
0x4c244  ldc.i4.0
0x4c245  ldnull
0x4c246  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4c24b  ldarg.s  5
0x4c24d  brfalse.s loc_4C25F
0x4c24f  ldarg.0
0x4c250  ldstr    aImportcompress_0// "ImportCompressedTranslationsXmlWithProg"...
0x4c255  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c25a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4c25f  ldarg.3
0x4c260  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4c265  stloc.1
0x4c266  ldloc.1
0x4c267  brfalse.s loc_4C2A4
0x4c269  ldarg.0
0x4c26a  ldstr    aOptionalparame_0// "OptionalParameters"
0x4c26f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c274  ldnull
0x4c275  ldc.i4.0
0x4c276  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4c27b  ldc.i4.0
0x4c27c  stloc.2
0x4c27d  br.s     loc_4C298
0x4c27f  ldarg.0
0x4c280  ldstr    aOptionalparame// "OptionalParameter"
0x4c285  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c28a  ldloc.1
0x4c28b  ldloc.2
0x4c28c  ldelem.ref
0x4c28d  ldc.i4.1
0x4c28e  ldc.i4.0
0x4c28f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4c294  ldloc.2
0x4c295  ldc.i4.1
0x4c296  add
0x4c297  stloc.2
0x4c298  ldloc.2
0x4c299  ldloc.1
0x4c29a  ldlen
0x4c29b  conv.i4
0x4c29c  blt.s    loc_4C27F
0x4c29e  ldarg.0
0x4c29f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4c2a4  ldarg.0
0x4c2a5  ldstr    aCompressedtran// "CompressedTranslationsXml"
0x4c2aa  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c2af  ldarg.3
0x4c2b0  callvirt instance unsigned int8[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportCompressedTranslationsXmlWithProgressRequest::get_CompressedTranslationsXml()
0x4c2b5  call     unsigned int8[] [System.Xml]System.Xml.Serialization.XmlSerializationWriter::FromByteArrayBase64(unsigned int8[])
0x4c2ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, unsigned int8[])
0x4c2bf  ldarg.0
0x4c2c0  ldstr    aImportjobid_0// "ImportJobId"
0x4c2c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c2ca  ldarg.3
0x4c2cb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportCompressedTranslationsXmlWithProgressRequest::get_ImportJobId()
0x4c2d0  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4c2d5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4c2da  ldarg.0
0x4c2db  ldarg.3
0x4c2dc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4c2e1  ret
```
