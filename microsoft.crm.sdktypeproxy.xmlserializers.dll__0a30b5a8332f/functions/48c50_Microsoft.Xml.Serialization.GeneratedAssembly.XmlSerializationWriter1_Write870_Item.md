# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write870_Item

- ea: `0x48c50`
- end: `0x48d38`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write870_Item`
- size: `232`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x48c50`

## string_xrefs

- `0x48c95`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x48caf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x48cc5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x48cea`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x48d05`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x48d1b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x48d00`: `FetchXml`
- `0x48c90`: `RemoveMembersByFetchXmlListRequest`

## pseudocode

```c

```

## disassembly

```asm
0x48c50  ldarg.3
0x48c51  brtrue.s loc_48C60
0x48c53  ldarg.s  4
0x48c55  brfalse.s loc_48C5F
0x48c57  ldarg.0
0x48c58  ldarg.1
0x48c59  ldarg.2
0x48c5a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x48c5f  ret
0x48c60  ldarg.s  5
0x48c62  brtrue.s loc_48C80
0x48c64  ldarg.3
0x48c65  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x48c6a  stloc.0
0x48c6b  ldloc.0
0x48c6c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RemoveMembersByFetchXmlListRequest
0x48c71  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x48c76  beq.s    loc_48C80
0x48c78  ldarg.0
0x48c79  ldarg.3
0x48c7a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x48c7f  throw
0x48c80  ldarg.0
0x48c81  ldarg.1
0x48c82  ldarg.2
0x48c83  ldarg.3
0x48c84  ldc.i4.0
0x48c85  ldnull
0x48c86  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x48c8b  ldarg.s  5
0x48c8d  brfalse.s loc_48C9F
0x48c8f  ldarg.0
0x48c90  ldstr    aRemovemembersb// "RemoveMembersByFetchXmlListRequest"
0x48c95  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x48c9a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x48c9f  ldarg.3
0x48ca0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x48ca5  stloc.1
0x48ca6  ldloc.1
0x48ca7  brfalse.s loc_48CE4
0x48ca9  ldarg.0
0x48caa  ldstr    aOptionalparame_0// "OptionalParameters"
0x48caf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x48cb4  ldnull
0x48cb5  ldc.i4.0
0x48cb6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x48cbb  ldc.i4.0
0x48cbc  stloc.2
0x48cbd  br.s     loc_48CD8
0x48cbf  ldarg.0
0x48cc0  ldstr    aOptionalparame// "OptionalParameter"
0x48cc5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x48cca  ldloc.1
0x48ccb  ldloc.2
0x48ccc  ldelem.ref
0x48ccd  ldc.i4.1
0x48cce  ldc.i4.0
0x48ccf  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x48cd4  ldloc.2
0x48cd5  ldc.i4.1
0x48cd6  add
0x48cd7  stloc.2
0x48cd8  ldloc.2
0x48cd9  ldloc.1
0x48cda  ldlen
0x48cdb  conv.i4
0x48cdc  blt.s    loc_48CBF
0x48cde  ldarg.0
0x48cdf  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x48ce4  ldarg.0
0x48ce5  ldstr    aListid_0// "ListId"
0x48cea  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x48cef  ldarg.3
0x48cf0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RemoveMembersByFetchXmlListRequest::get_ListId()
0x48cf5  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x48cfa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x48cff  ldarg.0
0x48d00  ldstr    aFetchxml_1// "FetchXml"
0x48d05  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x48d0a  ldarg.3
0x48d0b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RemoveMembersByFetchXmlListRequest::get_FetchXml()
0x48d10  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x48d15  ldarg.0
0x48d16  ldstr    aKeepreturned// "KeepReturned"
0x48d1b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x48d20  ldarg.3
0x48d21  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RemoveMembersByFetchXmlListRequest::get_KeepReturned()
0x48d26  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x48d2b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x48d30  ldarg.0
0x48d31  ldarg.3
0x48d32  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x48d37  ret
```
