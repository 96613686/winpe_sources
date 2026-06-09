# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write34_LookupAttributeMetadata

- ea: `0x32cc0`
- end: `0x32f08`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write34_LookupAttributeMetadata`
- size: `584`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1940`
- `0x30290`
- `0x31530`
- `0x688c0`

## callees

- `0x16f0`
- `0x1890`
- `0x1940`
- `0x30bf0`
- `0x30f10`
- `0x318b0`
- `0x319c0`
- `0x32cc0`

## string_xrefs

- `0x32d05`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32d15`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32d2d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32d43`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32d59`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32d6f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32d87`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32d9f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32db7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32dcf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32de7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32dff`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32e17`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32e2f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32e47`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32e5f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32e75`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32e8b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32ea1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32ec1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32ed7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32dfa`: `ValidForCreate`
- `0x32e12`: `ValidForRead`
- `0x32e2a`: `ValidForUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x32cc0  ldarg.3
0x32cc1  brtrue.s loc_32CD0
0x32cc3  ldarg.s  4
0x32cc5  brfalse.s loc_32CCF
0x32cc7  ldarg.0
0x32cc8  ldarg.1
0x32cc9  ldarg.2
0x32cca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x32ccf  ret
0x32cd0  ldarg.s  5
0x32cd2  brtrue.s loc_32CF0
0x32cd4  ldarg.3
0x32cd5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x32cda  stloc.0
0x32cdb  ldloc.0
0x32cdc  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.LookupAttributeMetadata
0x32ce1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32ce6  beq.s    loc_32CF0
0x32ce8  ldarg.0
0x32ce9  ldarg.3
0x32cea  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x32cef  throw
0x32cf0  ldarg.0
0x32cf1  ldarg.1
0x32cf2  ldarg.2
0x32cf3  ldarg.3
0x32cf4  ldc.i4.0
0x32cf5  ldnull
0x32cf6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x32cfb  ldarg.s  5
0x32cfd  brfalse.s loc_32D0F
0x32cff  ldarg.0
0x32d00  ldstr    aLookupattribut_0// "LookupAttributeMetadata"
0x32d05  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32d0a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x32d0f  ldarg.0
0x32d10  ldstr    aMetadataid// "MetadataId"
0x32d15  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32d1a  ldarg.3
0x32d1b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmMetadata::get_MetadataId()
0x32d20  ldc.i4.0
0x32d21  ldc.i4.0
0x32d22  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write6_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x32d27  ldarg.0
0x32d28  ldstr    aSchemaname// "SchemaName"
0x32d2d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32d32  ldarg.3
0x32d33  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_SchemaName()
0x32d38  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32d3d  ldarg.0
0x32d3e  ldstr    aLogicalname// "LogicalName"
0x32d43  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32d48  ldarg.3
0x32d49  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_LogicalName()
0x32d4e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32d53  ldarg.0
0x32d54  ldstr    aEntitylogicaln// "EntityLogicalName"
0x32d59  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32d5e  ldarg.3
0x32d5f  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_EntityLogicalName()
0x32d64  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32d69  ldarg.0
0x32d6a  ldstr    aAttributetype// "AttributeType"
0x32d6f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32d74  ldarg.3
0x32d75  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeType()
0x32d7a  ldc.i4.0
0x32d7b  ldc.i4.0
0x32d7c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write15_CrmAttributeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType o, bool isNullable, bool needType)
0x32d81  ldarg.0
0x32d82  ldstr    aDisplayname// "DisplayName"
0x32d87  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32d8c  ldarg.3
0x32d8d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayName()
0x32d92  ldc.i4.0
0x32d93  ldc.i4.0
0x32d94  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x32d99  ldarg.0
0x32d9a  ldstr    aDescription// "Description"
0x32d9f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32da4  ldarg.3
0x32da5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_Description()
0x32daa  ldc.i4.0
0x32dab  ldc.i4.0
0x32dac  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x32db1  ldarg.0
0x32db2  ldstr    aIscustomfield// "IsCustomField"
0x32db7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32dbc  ldarg.3
0x32dbd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_IsCustomField()
0x32dc2  ldc.i4.0
0x32dc3  ldc.i4.0
0x32dc4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x32dc9  ldarg.0
0x32dca  ldstr    aRequiredlevel// "RequiredLevel"
0x32dcf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32dd4  ldarg.3
0x32dd5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_RequiredLevel()
0x32dda  ldc.i4.0
0x32ddb  ldc.i4.0
0x32ddc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write17_CrmAttributeRequiredLevel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel o, bool isNullable, bool needType)
0x32de1  ldarg.0
0x32de2  ldstr    aDefaultvalue// "DefaultValue"
0x32de7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32dec  ldarg.3
0x32ded  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DefaultValue()
0x32df2  ldc.i4.0
0x32df3  ldc.i4.0
0x32df4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1_Object(string n, string ns, object o, bool isNullable, bool needType)
0x32df9  ldarg.0
0x32dfa  ldstr    aValidforcreate// "ValidForCreate"
0x32dff  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32e04  ldarg.3
0x32e05  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForCreate()
0x32e0a  ldc.i4.0
0x32e0b  ldc.i4.0
0x32e0c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x32e11  ldarg.0
0x32e12  ldstr    aValidforread// "ValidForRead"
0x32e17  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32e1c  ldarg.3
0x32e1d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForRead()
0x32e22  ldc.i4.0
0x32e23  ldc.i4.0
0x32e24  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x32e29  ldarg.0
0x32e2a  ldstr    aValidforupdate// "ValidForUpdate"
0x32e2f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32e34  ldarg.3
0x32e35  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForUpdate()
0x32e3a  ldc.i4.0
0x32e3b  ldc.i4.0
0x32e3c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x32e41  ldarg.0
0x32e42  ldstr    aDisplaymask// "DisplayMask"
0x32e47  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32e4c  ldarg.3
0x32e4d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayMask()
0x32e52  ldc.i4.0
0x32e53  ldc.i4.0
0x32e54  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write19_CrmDisplayMasks(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks o, bool isNullable, bool needType)
0x32e59  ldarg.0
0x32e5a  ldstr    aAggregateof// "AggregateOf"
0x32e5f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32e64  ldarg.3
0x32e65  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AggregateOf()
0x32e6a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32e6f  ldarg.0
0x32e70  ldstr    aAttributeof// "AttributeOf"
0x32e75  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32e7a  ldarg.3
0x32e7b  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeOf()
0x32e80  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32e85  ldarg.0
0x32e86  ldstr    aYomiof// "YomiOf"
0x32e8b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32e90  ldarg.3
0x32e91  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_YomiOf()
0x32e96  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32e9b  ldarg.0
0x32e9c  ldstr    aCalculationof// "CalculationOf"
0x32ea1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32ea6  ldarg.3
0x32ea7  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_CalculationOf()
0x32eac  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32eb1  ldarg.3
0x32eb2  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.LookupAttributeMetadata::get_Targets()
0x32eb7  stloc.1
0x32eb8  ldloc.1
0x32eb9  brfalse.s loc_32F00
0x32ebb  ldarg.0
0x32ebc  ldstr    aTargets// "Targets"
0x32ec1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32ec6  ldnull
0x32ec7  ldc.i4.0
0x32ec8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x32ecd  ldc.i4.0
0x32ece  stloc.2
0x32ecf  br.s     loc_32EF1
0x32ed1  ldarg.0
0x32ed2  ldstr    aTarget// "Target"
0x32ed7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32edc  ldloc.1
0x32edd  ldloc.2
0x32ede  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x32ee3  castclass [mscorlib]System.String
0x32ee8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32eed  ldloc.2
0x32eee  ldc.i4.1
0x32eef  add
0x32ef0  stloc.2
0x32ef1  ldloc.2
0x32ef2  ldloc.1
0x32ef3  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x32ef8  blt.s    loc_32ED1
0x32efa  ldarg.0
0x32efb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x32f00  ldarg.0
0x32f01  ldarg.3
0x32f02  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x32f07  ret
```
