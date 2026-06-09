# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write934_ImportXmlRequest

- ea: `0x4bd20`
- end: `0x4bde8`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write934_ImportXmlRequest`
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
- `0x4bd20`

## string_xrefs

- `0x4bd65`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4bd7f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4bd95`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4bdba`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4bdd0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4bdb5`: `ParameterXml`
- `0x4bdcb`: `CustomizationXml`
- `0x4bd60`: `ImportXmlRequest`

## pseudocode

```c

```

## disassembly

```asm
0x4bd20  ldarg.3
0x4bd21  brtrue.s loc_4BD30
0x4bd23  ldarg.s  4
0x4bd25  brfalse.s loc_4BD2F
0x4bd27  ldarg.0
0x4bd28  ldarg.1
0x4bd29  ldarg.2
0x4bd2a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4bd2f  ret
0x4bd30  ldarg.s  5
0x4bd32  brtrue.s loc_4BD50
0x4bd34  ldarg.3
0x4bd35  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4bd3a  stloc.0
0x4bd3b  ldloc.0
0x4bd3c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportXmlRequest
0x4bd41  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4bd46  beq.s    loc_4BD50
0x4bd48  ldarg.0
0x4bd49  ldarg.3
0x4bd4a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4bd4f  throw
0x4bd50  ldarg.0
0x4bd51  ldarg.1
0x4bd52  ldarg.2
0x4bd53  ldarg.3
0x4bd54  ldc.i4.0
0x4bd55  ldnull
0x4bd56  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4bd5b  ldarg.s  5
0x4bd5d  brfalse.s loc_4BD6F
0x4bd5f  ldarg.0
0x4bd60  ldstr    aImportxmlreque// "ImportXmlRequest"
0x4bd65  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4bd6a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4bd6f  ldarg.3
0x4bd70  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4bd75  stloc.1
0x4bd76  ldloc.1
0x4bd77  brfalse.s loc_4BDB4
0x4bd79  ldarg.0
0x4bd7a  ldstr    aOptionalparame_0// "OptionalParameters"
0x4bd7f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4bd84  ldnull
0x4bd85  ldc.i4.0
0x4bd86  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4bd8b  ldc.i4.0
0x4bd8c  stloc.2
0x4bd8d  br.s     loc_4BDA8
0x4bd8f  ldarg.0
0x4bd90  ldstr    aOptionalparame// "OptionalParameter"
0x4bd95  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4bd9a  ldloc.1
0x4bd9b  ldloc.2
0x4bd9c  ldelem.ref
0x4bd9d  ldc.i4.1
0x4bd9e  ldc.i4.0
0x4bd9f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4bda4  ldloc.2
0x4bda5  ldc.i4.1
0x4bda6  add
0x4bda7  stloc.2
0x4bda8  ldloc.2
0x4bda9  ldloc.1
0x4bdaa  ldlen
0x4bdab  conv.i4
0x4bdac  blt.s    loc_4BD8F
0x4bdae  ldarg.0
0x4bdaf  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4bdb4  ldarg.0
0x4bdb5  ldstr    aParameterxml_0// "ParameterXml"
0x4bdba  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4bdbf  ldarg.3
0x4bdc0  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportXmlRequest::get_ParameterXml()
0x4bdc5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4bdca  ldarg.0
0x4bdcb  ldstr    aCustomizationx// "CustomizationXml"
0x4bdd0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4bdd5  ldarg.3
0x4bdd6  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportXmlRequest::get_CustomizationXml()
0x4bddb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4bde0  ldarg.0
0x4bde1  ldarg.3
0x4bde2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4bde7  ret
```
