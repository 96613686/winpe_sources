# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write938_Item

- ea: `0x4c050`
- end: `0x4c11d`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write938_Item`
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
- `0x4c050`

## string_xrefs

- `0x4c095`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c0af`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c0c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c0ea`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c100`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c0e5`: `MappingsXml`
- `0x4c0fb`: `ReplaceIds`

## pseudocode

```c

```

## disassembly

```asm
0x4c050  ldarg.3
0x4c051  brtrue.s loc_4C060
0x4c053  ldarg.s  4
0x4c055  brfalse.s loc_4C05F
0x4c057  ldarg.0
0x4c058  ldarg.1
0x4c059  ldarg.2
0x4c05a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4c05f  ret
0x4c060  ldarg.s  5
0x4c062  brtrue.s loc_4C080
0x4c064  ldarg.3
0x4c065  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4c06a  stloc.0
0x4c06b  ldloc.0
0x4c06c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportLinearMappingsImportMapRequest
0x4c071  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4c076  beq.s    loc_4C080
0x4c078  ldarg.0
0x4c079  ldarg.3
0x4c07a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4c07f  throw
0x4c080  ldarg.0
0x4c081  ldarg.1
0x4c082  ldarg.2
0x4c083  ldarg.3
0x4c084  ldc.i4.0
0x4c085  ldnull
0x4c086  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4c08b  ldarg.s  5
0x4c08d  brfalse.s loc_4C09F
0x4c08f  ldarg.0
0x4c090  ldstr    aImportlinearma// "ImportLinearMappingsImportMapRequest"
0x4c095  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c09a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4c09f  ldarg.3
0x4c0a0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4c0a5  stloc.1
0x4c0a6  ldloc.1
0x4c0a7  brfalse.s loc_4C0E4
0x4c0a9  ldarg.0
0x4c0aa  ldstr    aOptionalparame_0// "OptionalParameters"
0x4c0af  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c0b4  ldnull
0x4c0b5  ldc.i4.0
0x4c0b6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4c0bb  ldc.i4.0
0x4c0bc  stloc.2
0x4c0bd  br.s     loc_4C0D8
0x4c0bf  ldarg.0
0x4c0c0  ldstr    aOptionalparame// "OptionalParameter"
0x4c0c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c0ca  ldloc.1
0x4c0cb  ldloc.2
0x4c0cc  ldelem.ref
0x4c0cd  ldc.i4.1
0x4c0ce  ldc.i4.0
0x4c0cf  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4c0d4  ldloc.2
0x4c0d5  ldc.i4.1
0x4c0d6  add
0x4c0d7  stloc.2
0x4c0d8  ldloc.2
0x4c0d9  ldloc.1
0x4c0da  ldlen
0x4c0db  conv.i4
0x4c0dc  blt.s    loc_4C0BF
0x4c0de  ldarg.0
0x4c0df  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4c0e4  ldarg.0
0x4c0e5  ldstr    aMappingsxml// "MappingsXml"
0x4c0ea  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c0ef  ldarg.3
0x4c0f0  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportLinearMappingsImportMapRequest::get_MappingsXml()
0x4c0f5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4c0fa  ldarg.0
0x4c0fb  ldstr    aReplaceids// "ReplaceIds"
0x4c100  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c105  ldarg.3
0x4c106  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportLinearMappingsImportMapRequest::get_ReplaceIds()
0x4c10b  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x4c110  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4c115  ldarg.0
0x4c116  ldarg.3
0x4c117  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4c11c  ret
```
