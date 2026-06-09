# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1243_Item

- ea: `0x57c20`
- end: `0x57d28`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1243_Item`
- size: `264`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x57c20`

## string_xrefs

- `0x57c65`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x57c7f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x57c95`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x57cba`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x57cda`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x57cf1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x57c60`: `CreateOrUpdateImportMapFromAppRequest`
- `0x57cb5`: `MapXml`
- `0x57cd5`: `ColMappingIdsToDelete`

## pseudocode

```c

```

## disassembly

```asm
0x57c20  ldarg.3
0x57c21  brtrue.s loc_57C30
0x57c23  ldarg.s  4
0x57c25  brfalse.s loc_57C2F
0x57c27  ldarg.0
0x57c28  ldarg.1
0x57c29  ldarg.2
0x57c2a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x57c2f  ret
0x57c30  ldarg.s  5
0x57c32  brtrue.s loc_57C50
0x57c34  ldarg.3
0x57c35  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x57c3a  stloc.0
0x57c3b  ldloc.0
0x57c3c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateOrUpdateImportMapFromAppRequest
0x57c41  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x57c46  beq.s    loc_57C50
0x57c48  ldarg.0
0x57c49  ldarg.3
0x57c4a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x57c4f  throw
0x57c50  ldarg.0
0x57c51  ldarg.1
0x57c52  ldarg.2
0x57c53  ldarg.3
0x57c54  ldc.i4.0
0x57c55  ldnull
0x57c56  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x57c5b  ldarg.s  5
0x57c5d  brfalse.s loc_57C6F
0x57c5f  ldarg.0
0x57c60  ldstr    aCreateorupdate// "CreateOrUpdateImportMapFromAppRequest"
0x57c65  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x57c6a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x57c6f  ldarg.3
0x57c70  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x57c75  stloc.1
0x57c76  ldloc.1
0x57c77  brfalse.s loc_57CB4
0x57c79  ldarg.0
0x57c7a  ldstr    aOptionalparame_0// "OptionalParameters"
0x57c7f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x57c84  ldnull
0x57c85  ldc.i4.0
0x57c86  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x57c8b  ldc.i4.0
0x57c8c  stloc.2
0x57c8d  br.s     loc_57CA8
0x57c8f  ldarg.0
0x57c90  ldstr    aOptionalparame// "OptionalParameter"
0x57c95  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x57c9a  ldloc.1
0x57c9b  ldloc.2
0x57c9c  ldelem.ref
0x57c9d  ldc.i4.1
0x57c9e  ldc.i4.0
0x57c9f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x57ca4  ldloc.2
0x57ca5  ldc.i4.1
0x57ca6  add
0x57ca7  stloc.2
0x57ca8  ldloc.2
0x57ca9  ldloc.1
0x57caa  ldlen
0x57cab  conv.i4
0x57cac  blt.s    loc_57C8F
0x57cae  ldarg.0
0x57caf  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x57cb4  ldarg.0
0x57cb5  ldstr    aMapxml// "MapXml"
0x57cba  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x57cbf  ldarg.3
0x57cc0  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateOrUpdateImportMapFromAppRequest::get_MapXml()
0x57cc5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x57cca  ldarg.3
0x57ccb  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateOrUpdateImportMapFromAppRequest::get_ColMappingIdsToDelete()
0x57cd0  stloc.3
0x57cd1  ldloc.3
0x57cd2  brfalse.s loc_57D20
0x57cd4  ldarg.0
0x57cd5  ldstr    aColmappingidst// "ColMappingIdsToDelete"
0x57cda  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x57cdf  ldnull
0x57ce0  ldc.i4.0
0x57ce1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x57ce6  ldc.i4.0
0x57ce7  stloc.s  4
0x57ce9  br.s     loc_57D13
0x57ceb  ldarg.0
0x57cec  ldstr    aGuid// "guid"
0x57cf1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x57cf6  ldloc.3
0x57cf7  ldloc.s  4
0x57cf9  ldelema  [mscorlib]System.Guid
0x57cfe  ldobj    [mscorlib]System.Guid
0x57d03  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x57d08  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x57d0d  ldloc.s  4
0x57d0f  ldc.i4.1
0x57d10  add
0x57d11  stloc.s  4
0x57d13  ldloc.s  4
0x57d15  ldloc.3
0x57d16  ldlen
0x57d17  conv.i4
0x57d18  blt.s    loc_57CEB
0x57d1a  ldarg.0
0x57d1b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x57d20  ldarg.0
0x57d21  ldarg.3
0x57d22  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x57d27  ret
```
