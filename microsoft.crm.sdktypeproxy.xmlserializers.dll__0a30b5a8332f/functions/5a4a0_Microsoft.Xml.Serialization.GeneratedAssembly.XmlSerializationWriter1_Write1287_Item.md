# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1287_Item

- ea: `0x5a4a0`
- end: `0x5a56d`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1287_Item`
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
- `0x5a4a0`

## string_xrefs

- `0x5a4e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5a4ff`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5a515`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5a53a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5a555`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5a550`: `FetchXml`
- `0x5a4e0`: `AddMembersByFetchXmlListRequest`

## pseudocode

```c

```

## disassembly

```asm
0x5a4a0  ldarg.3
0x5a4a1  brtrue.s loc_5A4B0
0x5a4a3  ldarg.s  4
0x5a4a5  brfalse.s loc_5A4AF
0x5a4a7  ldarg.0
0x5a4a8  ldarg.1
0x5a4a9  ldarg.2
0x5a4aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x5a4af  ret
0x5a4b0  ldarg.s  5
0x5a4b2  brtrue.s loc_5A4D0
0x5a4b4  ldarg.3
0x5a4b5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5a4ba  stloc.0
0x5a4bb  ldloc.0
0x5a4bc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.AddMembersByFetchXmlListRequest
0x5a4c1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5a4c6  beq.s    loc_5A4D0
0x5a4c8  ldarg.0
0x5a4c9  ldarg.3
0x5a4ca  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x5a4cf  throw
0x5a4d0  ldarg.0
0x5a4d1  ldarg.1
0x5a4d2  ldarg.2
0x5a4d3  ldarg.3
0x5a4d4  ldc.i4.0
0x5a4d5  ldnull
0x5a4d6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x5a4db  ldarg.s  5
0x5a4dd  brfalse.s loc_5A4EF
0x5a4df  ldarg.0
0x5a4e0  ldstr    aAddmembersbyfe// "AddMembersByFetchXmlListRequest"
0x5a4e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5a4ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x5a4ef  ldarg.3
0x5a4f0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x5a4f5  stloc.1
0x5a4f6  ldloc.1
0x5a4f7  brfalse.s loc_5A534
0x5a4f9  ldarg.0
0x5a4fa  ldstr    aOptionalparame_0// "OptionalParameters"
0x5a4ff  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5a504  ldnull
0x5a505  ldc.i4.0
0x5a506  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x5a50b  ldc.i4.0
0x5a50c  stloc.2
0x5a50d  br.s     loc_5A528
0x5a50f  ldarg.0
0x5a510  ldstr    aOptionalparame// "OptionalParameter"
0x5a515  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5a51a  ldloc.1
0x5a51b  ldloc.2
0x5a51c  ldelem.ref
0x5a51d  ldc.i4.1
0x5a51e  ldc.i4.0
0x5a51f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x5a524  ldloc.2
0x5a525  ldc.i4.1
0x5a526  add
0x5a527  stloc.2
0x5a528  ldloc.2
0x5a529  ldloc.1
0x5a52a  ldlen
0x5a52b  conv.i4
0x5a52c  blt.s    loc_5A50F
0x5a52e  ldarg.0
0x5a52f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x5a534  ldarg.0
0x5a535  ldstr    aListid_0// "ListId"
0x5a53a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5a53f  ldarg.3
0x5a540  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.AddMembersByFetchXmlListRequest::get_ListId()
0x5a545  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x5a54a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x5a54f  ldarg.0
0x5a550  ldstr    aFetchxml_1// "FetchXml"
0x5a555  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5a55a  ldarg.3
0x5a55b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.AddMembersByFetchXmlListRequest::get_FetchXml()
0x5a560  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x5a565  ldarg.0
0x5a566  ldarg.3
0x5a567  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x5a56c  ret
```
