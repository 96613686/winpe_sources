# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write41_StringAttributeMetadata

- ea: `0x11c0`
- end: `0x1419`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write41_StringAttributeMetadata`
- size: `601`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1100`
- `0x1940`
- `0x30290`
- `0x31530`

## callees

- `0x11c0`
- `0x1420`
- `0x14d0`
- `0x15d0`
- `0x16f0`
- `0x1890`
- `0x1940`
- `0x30bf0`
- `0x30f10`
- `0x318b0`
- `0x319c0`

## string_xrefs

- `0x1205`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1215`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x122d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1243`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1259`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x126f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1287`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x129f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x12b7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x12cf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x12e7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x12ff`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1317`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x132f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1347`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x135f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1375`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x138b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x13a1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x13b7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x13cf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x13e7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x13ff`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x12fa`: `ValidForCreate`
- `0x1312`: `ValidForRead`
- `0x132a`: `ValidForUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x11c0  ldarg.3
0x11c1  brtrue.s loc_11D0
0x11c3  ldarg.s  4
0x11c5  brfalse.s loc_11CF
0x11c7  ldarg.0
0x11c8  ldarg.1
0x11c9  ldarg.2
0x11ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x11cf  ret
0x11d0  ldarg.s  5
0x11d2  brtrue.s loc_11F0
0x11d4  ldarg.3
0x11d5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x11da  stloc.0
0x11db  ldloc.0
0x11dc  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StringAttributeMetadata
0x11e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11e6  beq.s    loc_11F0
0x11e8  ldarg.0
0x11e9  ldarg.3
0x11ea  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x11ef  throw
0x11f0  ldarg.0
0x11f1  ldarg.1
0x11f2  ldarg.2
0x11f3  ldarg.3
0x11f4  ldc.i4.0
0x11f5  ldnull
0x11f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x11fb  ldarg.s  5
0x11fd  brfalse.s loc_120F
0x11ff  ldarg.0
0x1200  ldstr    aStringattribut// "StringAttributeMetadata"
0x1205  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x120a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x120f  ldarg.0
0x1210  ldstr    aMetadataid// "MetadataId"
0x1215  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x121a  ldarg.3
0x121b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmMetadata::get_MetadataId()
0x1220  ldc.i4.0
0x1221  ldc.i4.0
0x1222  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write6_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1227  ldarg.0
0x1228  ldstr    aSchemaname// "SchemaName"
0x122d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1232  ldarg.3
0x1233  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_SchemaName()
0x1238  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x123d  ldarg.0
0x123e  ldstr    aLogicalname// "LogicalName"
0x1243  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1248  ldarg.3
0x1249  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_LogicalName()
0x124e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1253  ldarg.0
0x1254  ldstr    aEntitylogicaln// "EntityLogicalName"
0x1259  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x125e  ldarg.3
0x125f  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_EntityLogicalName()
0x1264  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1269  ldarg.0
0x126a  ldstr    aAttributetype// "AttributeType"
0x126f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1274  ldarg.3
0x1275  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeType()
0x127a  ldc.i4.0
0x127b  ldc.i4.0
0x127c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write15_CrmAttributeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType o, bool isNullable, bool needType)
0x1281  ldarg.0
0x1282  ldstr    aDisplayname// "DisplayName"
0x1287  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x128c  ldarg.3
0x128d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayName()
0x1292  ldc.i4.0
0x1293  ldc.i4.0
0x1294  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x1299  ldarg.0
0x129a  ldstr    aDescription// "Description"
0x129f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x12a4  ldarg.3
0x12a5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_Description()
0x12aa  ldc.i4.0
0x12ab  ldc.i4.0
0x12ac  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x12b1  ldarg.0
0x12b2  ldstr    aIscustomfield// "IsCustomField"
0x12b7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x12bc  ldarg.3
0x12bd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_IsCustomField()
0x12c2  ldc.i4.0
0x12c3  ldc.i4.0
0x12c4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x12c9  ldarg.0
0x12ca  ldstr    aRequiredlevel// "RequiredLevel"
0x12cf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x12d4  ldarg.3
0x12d5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_RequiredLevel()
0x12da  ldc.i4.0
0x12db  ldc.i4.0
0x12dc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write17_CrmAttributeRequiredLevel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel o, bool isNullable, bool needType)
0x12e1  ldarg.0
0x12e2  ldstr    aDefaultvalue// "DefaultValue"
0x12e7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x12ec  ldarg.3
0x12ed  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DefaultValue()
0x12f2  ldc.i4.0
0x12f3  ldc.i4.0
0x12f4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1_Object(string n, string ns, object o, bool isNullable, bool needType)
0x12f9  ldarg.0
0x12fa  ldstr    aValidforcreate// "ValidForCreate"
0x12ff  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1304  ldarg.3
0x1305  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForCreate()
0x130a  ldc.i4.0
0x130b  ldc.i4.0
0x130c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1311  ldarg.0
0x1312  ldstr    aValidforread// "ValidForRead"
0x1317  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x131c  ldarg.3
0x131d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForRead()
0x1322  ldc.i4.0
0x1323  ldc.i4.0
0x1324  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1329  ldarg.0
0x132a  ldstr    aValidforupdate// "ValidForUpdate"
0x132f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1334  ldarg.3
0x1335  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForUpdate()
0x133a  ldc.i4.0
0x133b  ldc.i4.0
0x133c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1341  ldarg.0
0x1342  ldstr    aDisplaymask// "DisplayMask"
0x1347  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x134c  ldarg.3
0x134d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayMask()
0x1352  ldc.i4.0
0x1353  ldc.i4.0
0x1354  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write19_CrmDisplayMasks(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks o, bool isNullable, bool needType)
0x1359  ldarg.0
0x135a  ldstr    aAggregateof// "AggregateOf"
0x135f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1364  ldarg.3
0x1365  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AggregateOf()
0x136a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x136f  ldarg.0
0x1370  ldstr    aAttributeof// "AttributeOf"
0x1375  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x137a  ldarg.3
0x137b  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeOf()
0x1380  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1385  ldarg.0
0x1386  ldstr    aYomiof// "YomiOf"
0x138b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1390  ldarg.3
0x1391  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_YomiOf()
0x1396  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x139b  ldarg.0
0x139c  ldstr    aCalculationof// "CalculationOf"
0x13a1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x13a6  ldarg.3
0x13a7  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_CalculationOf()
0x13ac  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x13b1  ldarg.0
0x13b2  ldstr    aFormat// "Format"
0x13b7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x13bc  ldarg.3
0x13bd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmStringFormat [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StringAttributeMetadata::get_Format()
0x13c2  ldc.i4.0
0x13c3  ldc.i4.0
0x13c4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write39_CrmStringFormat(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmStringFormat o, bool isNullable, bool needType)
0x13c9  ldarg.0
0x13ca  ldstr    aMaxlength// "MaxLength"
0x13cf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x13d4  ldarg.3
0x13d5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StringAttributeMetadata::get_MaxLength()
0x13da  ldc.i4.0
0x13db  ldc.i4.0
0x13dc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write8_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x13e1  ldarg.0
0x13e2  ldstr    aImemode// "ImeMode"
0x13e7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x13ec  ldarg.3
0x13ed  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmImeMode [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StringAttributeMetadata::get_ImeMode()
0x13f2  ldc.i4.0
0x13f3  ldc.i4.0
0x13f4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write22_CrmImeMode(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmImeMode o, bool isNullable, bool needType)
0x13f9  ldarg.0
0x13fa  ldstr    aDatabaselength// "DatabaseLength"
0x13ff  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1404  ldarg.3
0x1405  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StringAttributeMetadata::get_DatabaseLength()
0x140a  ldc.i4.0
0x140b  ldc.i4.0
0x140c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write8_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1411  ldarg.0
0x1412  ldarg.3
0x1413  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1418  ret
```
