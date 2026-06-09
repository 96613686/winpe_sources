# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write33_DateTimeAttributeMetadata

- ea: `0x329a0`
- end: `0x32bc9`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write33_DateTimeAttributeMetadata`
- size: `553`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1940`
- `0x30290`
- `0x31530`

## callees

- `0x14d0`
- `0x16f0`
- `0x1890`
- `0x1940`
- `0x30bf0`
- `0x30f10`
- `0x318b0`
- `0x319c0`
- `0x329a0`
- `0x32bd0`

## string_xrefs

- `0x329e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x329f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32a0d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32a23`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32a39`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32a4f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32a67`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32a7f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32a97`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32aaf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32ac7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32adf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32af7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32b0f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32b27`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32b3f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32b55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32b6b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32b81`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32b97`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32baf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32ada`: `ValidForCreate`
- `0x32af2`: `ValidForRead`
- `0x32b0a`: `ValidForUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x329a0  ldarg.3
0x329a1  brtrue.s loc_329B0
0x329a3  ldarg.s  4
0x329a5  brfalse.s loc_329AF
0x329a7  ldarg.0
0x329a8  ldarg.1
0x329a9  ldarg.2
0x329aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x329af  ret
0x329b0  ldarg.s  5
0x329b2  brtrue.s loc_329D0
0x329b4  ldarg.3
0x329b5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x329ba  stloc.0
0x329bb  ldloc.0
0x329bc  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.DateTimeAttributeMetadata
0x329c1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x329c6  beq.s    loc_329D0
0x329c8  ldarg.0
0x329c9  ldarg.3
0x329ca  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x329cf  throw
0x329d0  ldarg.0
0x329d1  ldarg.1
0x329d2  ldarg.2
0x329d3  ldarg.3
0x329d4  ldc.i4.0
0x329d5  ldnull
0x329d6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x329db  ldarg.s  5
0x329dd  brfalse.s loc_329EF
0x329df  ldarg.0
0x329e0  ldstr    aDatetimeattrib// "DateTimeAttributeMetadata"
0x329e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x329ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x329ef  ldarg.0
0x329f0  ldstr    aMetadataid// "MetadataId"
0x329f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x329fa  ldarg.3
0x329fb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmMetadata::get_MetadataId()
0x32a00  ldc.i4.0
0x32a01  ldc.i4.0
0x32a02  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write6_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x32a07  ldarg.0
0x32a08  ldstr    aSchemaname// "SchemaName"
0x32a0d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32a12  ldarg.3
0x32a13  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_SchemaName()
0x32a18  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32a1d  ldarg.0
0x32a1e  ldstr    aLogicalname// "LogicalName"
0x32a23  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32a28  ldarg.3
0x32a29  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_LogicalName()
0x32a2e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32a33  ldarg.0
0x32a34  ldstr    aEntitylogicaln// "EntityLogicalName"
0x32a39  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32a3e  ldarg.3
0x32a3f  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_EntityLogicalName()
0x32a44  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32a49  ldarg.0
0x32a4a  ldstr    aAttributetype// "AttributeType"
0x32a4f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32a54  ldarg.3
0x32a55  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeType()
0x32a5a  ldc.i4.0
0x32a5b  ldc.i4.0
0x32a5c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write15_CrmAttributeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType o, bool isNullable, bool needType)
0x32a61  ldarg.0
0x32a62  ldstr    aDisplayname// "DisplayName"
0x32a67  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32a6c  ldarg.3
0x32a6d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayName()
0x32a72  ldc.i4.0
0x32a73  ldc.i4.0
0x32a74  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x32a79  ldarg.0
0x32a7a  ldstr    aDescription// "Description"
0x32a7f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32a84  ldarg.3
0x32a85  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_Description()
0x32a8a  ldc.i4.0
0x32a8b  ldc.i4.0
0x32a8c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x32a91  ldarg.0
0x32a92  ldstr    aIscustomfield// "IsCustomField"
0x32a97  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32a9c  ldarg.3
0x32a9d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_IsCustomField()
0x32aa2  ldc.i4.0
0x32aa3  ldc.i4.0
0x32aa4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x32aa9  ldarg.0
0x32aaa  ldstr    aRequiredlevel// "RequiredLevel"
0x32aaf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32ab4  ldarg.3
0x32ab5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_RequiredLevel()
0x32aba  ldc.i4.0
0x32abb  ldc.i4.0
0x32abc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write17_CrmAttributeRequiredLevel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel o, bool isNullable, bool needType)
0x32ac1  ldarg.0
0x32ac2  ldstr    aDefaultvalue// "DefaultValue"
0x32ac7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32acc  ldarg.3
0x32acd  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DefaultValue()
0x32ad2  ldc.i4.0
0x32ad3  ldc.i4.0
0x32ad4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1_Object(string n, string ns, object o, bool isNullable, bool needType)
0x32ad9  ldarg.0
0x32ada  ldstr    aValidforcreate// "ValidForCreate"
0x32adf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32ae4  ldarg.3
0x32ae5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForCreate()
0x32aea  ldc.i4.0
0x32aeb  ldc.i4.0
0x32aec  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x32af1  ldarg.0
0x32af2  ldstr    aValidforread// "ValidForRead"
0x32af7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32afc  ldarg.3
0x32afd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForRead()
0x32b02  ldc.i4.0
0x32b03  ldc.i4.0
0x32b04  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x32b09  ldarg.0
0x32b0a  ldstr    aValidforupdate// "ValidForUpdate"
0x32b0f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32b14  ldarg.3
0x32b15  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForUpdate()
0x32b1a  ldc.i4.0
0x32b1b  ldc.i4.0
0x32b1c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x32b21  ldarg.0
0x32b22  ldstr    aDisplaymask// "DisplayMask"
0x32b27  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32b2c  ldarg.3
0x32b2d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayMask()
0x32b32  ldc.i4.0
0x32b33  ldc.i4.0
0x32b34  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write19_CrmDisplayMasks(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks o, bool isNullable, bool needType)
0x32b39  ldarg.0
0x32b3a  ldstr    aAggregateof// "AggregateOf"
0x32b3f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32b44  ldarg.3
0x32b45  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AggregateOf()
0x32b4a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32b4f  ldarg.0
0x32b50  ldstr    aAttributeof// "AttributeOf"
0x32b55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32b5a  ldarg.3
0x32b5b  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeOf()
0x32b60  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32b65  ldarg.0
0x32b66  ldstr    aYomiof// "YomiOf"
0x32b6b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32b70  ldarg.3
0x32b71  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_YomiOf()
0x32b76  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32b7b  ldarg.0
0x32b7c  ldstr    aCalculationof// "CalculationOf"
0x32b81  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32b86  ldarg.3
0x32b87  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_CalculationOf()
0x32b8c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32b91  ldarg.0
0x32b92  ldstr    aFormat// "Format"
0x32b97  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32b9c  ldarg.3
0x32b9d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDateTimeFormat [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.DateTimeAttributeMetadata::get_Format()
0x32ba2  ldc.i4.0
0x32ba3  ldc.i4.0
0x32ba4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write32_CrmDateTimeFormat(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDateTimeFormat o, bool isNullable, bool needType)
0x32ba9  ldarg.0
0x32baa  ldstr    aImemode// "ImeMode"
0x32baf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32bb4  ldarg.3
0x32bb5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmImeMode [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.DateTimeAttributeMetadata::get_ImeMode()
0x32bba  ldc.i4.0
0x32bbb  ldc.i4.0
0x32bbc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write22_CrmImeMode(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmImeMode o, bool isNullable, bool needType)
0x32bc1  ldarg.0
0x32bc2  ldarg.3
0x32bc3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x32bc8  ret
```
