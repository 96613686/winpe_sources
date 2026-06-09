# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write23_FloatAttributeMetadata

- ea: `0x31ba0`
- end: `0x31df9`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write23_FloatAttributeMetadata`
- size: `601`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1940`
- `0x30290`
- `0x31530`

## callees

- `0x1420`
- `0x14d0`
- `0x16f0`
- `0x1890`
- `0x1940`
- `0x30bf0`
- `0x30f10`
- `0x318b0`
- `0x319c0`
- `0x31ba0`
- `0x31e00`

## string_xrefs

- `0x31be5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31bf5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31c0d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31c23`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31c39`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31c4f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31c67`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31c7f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31c97`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31caf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31cc7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31cdf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31cf7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31d0f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31d27`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31d3f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31d55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31d6b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31d81`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31d97`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31daf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31dc7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31ddf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31cda`: `ValidForCreate`
- `0x31cf2`: `ValidForRead`
- `0x31d0a`: `ValidForUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x31ba0  ldarg.3
0x31ba1  brtrue.s loc_31BB0
0x31ba3  ldarg.s  4
0x31ba5  brfalse.s loc_31BAF
0x31ba7  ldarg.0
0x31ba8  ldarg.1
0x31ba9  ldarg.2
0x31baa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x31baf  ret
0x31bb0  ldarg.s  5
0x31bb2  brtrue.s loc_31BD0
0x31bb4  ldarg.3
0x31bb5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x31bba  stloc.0
0x31bbb  ldloc.0
0x31bbc  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.FloatAttributeMetadata
0x31bc1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31bc6  beq.s    loc_31BD0
0x31bc8  ldarg.0
0x31bc9  ldarg.3
0x31bca  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x31bcf  throw
0x31bd0  ldarg.0
0x31bd1  ldarg.1
0x31bd2  ldarg.2
0x31bd3  ldarg.3
0x31bd4  ldc.i4.0
0x31bd5  ldnull
0x31bd6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x31bdb  ldarg.s  5
0x31bdd  brfalse.s loc_31BEF
0x31bdf  ldarg.0
0x31be0  ldstr    aFloatattribute// "FloatAttributeMetadata"
0x31be5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31bea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x31bef  ldarg.0
0x31bf0  ldstr    aMetadataid// "MetadataId"
0x31bf5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31bfa  ldarg.3
0x31bfb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmMetadata::get_MetadataId()
0x31c00  ldc.i4.0
0x31c01  ldc.i4.0
0x31c02  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write6_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x31c07  ldarg.0
0x31c08  ldstr    aSchemaname// "SchemaName"
0x31c0d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31c12  ldarg.3
0x31c13  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_SchemaName()
0x31c18  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x31c1d  ldarg.0
0x31c1e  ldstr    aLogicalname// "LogicalName"
0x31c23  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31c28  ldarg.3
0x31c29  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_LogicalName()
0x31c2e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x31c33  ldarg.0
0x31c34  ldstr    aEntitylogicaln// "EntityLogicalName"
0x31c39  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31c3e  ldarg.3
0x31c3f  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_EntityLogicalName()
0x31c44  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x31c49  ldarg.0
0x31c4a  ldstr    aAttributetype// "AttributeType"
0x31c4f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31c54  ldarg.3
0x31c55  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeType()
0x31c5a  ldc.i4.0
0x31c5b  ldc.i4.0
0x31c5c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write15_CrmAttributeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType o, bool isNullable, bool needType)
0x31c61  ldarg.0
0x31c62  ldstr    aDisplayname// "DisplayName"
0x31c67  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31c6c  ldarg.3
0x31c6d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayName()
0x31c72  ldc.i4.0
0x31c73  ldc.i4.0
0x31c74  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x31c79  ldarg.0
0x31c7a  ldstr    aDescription// "Description"
0x31c7f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31c84  ldarg.3
0x31c85  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_Description()
0x31c8a  ldc.i4.0
0x31c8b  ldc.i4.0
0x31c8c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x31c91  ldarg.0
0x31c92  ldstr    aIscustomfield// "IsCustomField"
0x31c97  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31c9c  ldarg.3
0x31c9d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_IsCustomField()
0x31ca2  ldc.i4.0
0x31ca3  ldc.i4.0
0x31ca4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x31ca9  ldarg.0
0x31caa  ldstr    aRequiredlevel// "RequiredLevel"
0x31caf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31cb4  ldarg.3
0x31cb5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_RequiredLevel()
0x31cba  ldc.i4.0
0x31cbb  ldc.i4.0
0x31cbc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write17_CrmAttributeRequiredLevel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel o, bool isNullable, bool needType)
0x31cc1  ldarg.0
0x31cc2  ldstr    aDefaultvalue// "DefaultValue"
0x31cc7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31ccc  ldarg.3
0x31ccd  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DefaultValue()
0x31cd2  ldc.i4.0
0x31cd3  ldc.i4.0
0x31cd4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1_Object(string n, string ns, object o, bool isNullable, bool needType)
0x31cd9  ldarg.0
0x31cda  ldstr    aValidforcreate// "ValidForCreate"
0x31cdf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31ce4  ldarg.3
0x31ce5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForCreate()
0x31cea  ldc.i4.0
0x31ceb  ldc.i4.0
0x31cec  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x31cf1  ldarg.0
0x31cf2  ldstr    aValidforread// "ValidForRead"
0x31cf7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31cfc  ldarg.3
0x31cfd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForRead()
0x31d02  ldc.i4.0
0x31d03  ldc.i4.0
0x31d04  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x31d09  ldarg.0
0x31d0a  ldstr    aValidforupdate// "ValidForUpdate"
0x31d0f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31d14  ldarg.3
0x31d15  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForUpdate()
0x31d1a  ldc.i4.0
0x31d1b  ldc.i4.0
0x31d1c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x31d21  ldarg.0
0x31d22  ldstr    aDisplaymask// "DisplayMask"
0x31d27  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31d2c  ldarg.3
0x31d2d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayMask()
0x31d32  ldc.i4.0
0x31d33  ldc.i4.0
0x31d34  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write19_CrmDisplayMasks(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks o, bool isNullable, bool needType)
0x31d39  ldarg.0
0x31d3a  ldstr    aAggregateof// "AggregateOf"
0x31d3f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31d44  ldarg.3
0x31d45  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AggregateOf()
0x31d4a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x31d4f  ldarg.0
0x31d50  ldstr    aAttributeof// "AttributeOf"
0x31d55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31d5a  ldarg.3
0x31d5b  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeOf()
0x31d60  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x31d65  ldarg.0
0x31d66  ldstr    aYomiof// "YomiOf"
0x31d6b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31d70  ldarg.3
0x31d71  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_YomiOf()
0x31d76  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x31d7b  ldarg.0
0x31d7c  ldstr    aCalculationof// "CalculationOf"
0x31d81  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31d86  ldarg.3
0x31d87  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_CalculationOf()
0x31d8c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x31d91  ldarg.0
0x31d92  ldstr    aMinvalue// "MinValue"
0x31d97  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31d9c  ldarg.3
0x31d9d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.FloatAttributeMetadata::get_MinValue()
0x31da2  ldc.i4.0
0x31da3  ldc.i4.0
0x31da4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write20_CrmFloat(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat o, bool isNullable, bool needType)
0x31da9  ldarg.0
0x31daa  ldstr    aMaxvalue// "MaxValue"
0x31daf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31db4  ldarg.3
0x31db5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.FloatAttributeMetadata::get_MaxValue()
0x31dba  ldc.i4.0
0x31dbb  ldc.i4.0
0x31dbc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write20_CrmFloat(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat o, bool isNullable, bool needType)
0x31dc1  ldarg.0
0x31dc2  ldstr    aPrecision// "Precision"
0x31dc7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31dcc  ldarg.3
0x31dcd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.FloatAttributeMetadata::get_Precision()
0x31dd2  ldc.i4.0
0x31dd3  ldc.i4.0
0x31dd4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write8_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x31dd9  ldarg.0
0x31dda  ldstr    aImemode// "ImeMode"
0x31ddf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31de4  ldarg.3
0x31de5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmImeMode [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.FloatAttributeMetadata::get_ImeMode()
0x31dea  ldc.i4.0
0x31deb  ldc.i4.0
0x31dec  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write22_CrmImeMode(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmImeMode o, bool isNullable, bool needType)
0x31df1  ldarg.0
0x31df2  ldarg.3
0x31df3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x31df8  ret
```
