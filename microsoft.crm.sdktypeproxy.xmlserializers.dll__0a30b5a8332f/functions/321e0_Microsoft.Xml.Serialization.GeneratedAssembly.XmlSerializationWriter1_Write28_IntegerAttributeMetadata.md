# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write28_IntegerAttributeMetadata

- ea: `0x321e0`
- end: `0x32421`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write28_IntegerAttributeMetadata`
- size: `577`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1940`
- `0x30290`
- `0x31530`

## callees

- `0x1420`
- `0x16f0`
- `0x1890`
- `0x1940`
- `0x30bf0`
- `0x30f10`
- `0x318b0`
- `0x319c0`
- `0x321e0`
- `0x32430`

## string_xrefs

- `0x32225`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32235`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3224d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32263`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32279`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3228f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x322a7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x322bf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x322d7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x322ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32307`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3231f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32337`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3234f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32367`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3237f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32395`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x323ab`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x323c1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x323d7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x323ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32407`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3231a`: `ValidForCreate`
- `0x32332`: `ValidForRead`
- `0x3234a`: `ValidForUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x321e0  ldarg.3
0x321e1  brtrue.s loc_321F0
0x321e3  ldarg.s  4
0x321e5  brfalse.s loc_321EF
0x321e7  ldarg.0
0x321e8  ldarg.1
0x321e9  ldarg.2
0x321ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x321ef  ret
0x321f0  ldarg.s  5
0x321f2  brtrue.s loc_32210
0x321f4  ldarg.3
0x321f5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x321fa  stloc.0
0x321fb  ldloc.0
0x321fc  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.IntegerAttributeMetadata
0x32201  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32206  beq.s    loc_32210
0x32208  ldarg.0
0x32209  ldarg.3
0x3220a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x3220f  throw
0x32210  ldarg.0
0x32211  ldarg.1
0x32212  ldarg.2
0x32213  ldarg.3
0x32214  ldc.i4.0
0x32215  ldnull
0x32216  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3221b  ldarg.s  5
0x3221d  brfalse.s loc_3222F
0x3221f  ldarg.0
0x32220  ldstr    aIntegerattribu// "IntegerAttributeMetadata"
0x32225  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3222a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3222f  ldarg.0
0x32230  ldstr    aMetadataid// "MetadataId"
0x32235  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3223a  ldarg.3
0x3223b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmMetadata::get_MetadataId()
0x32240  ldc.i4.0
0x32241  ldc.i4.0
0x32242  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write6_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x32247  ldarg.0
0x32248  ldstr    aSchemaname// "SchemaName"
0x3224d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32252  ldarg.3
0x32253  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_SchemaName()
0x32258  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3225d  ldarg.0
0x3225e  ldstr    aLogicalname// "LogicalName"
0x32263  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32268  ldarg.3
0x32269  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_LogicalName()
0x3226e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32273  ldarg.0
0x32274  ldstr    aEntitylogicaln// "EntityLogicalName"
0x32279  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3227e  ldarg.3
0x3227f  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_EntityLogicalName()
0x32284  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32289  ldarg.0
0x3228a  ldstr    aAttributetype// "AttributeType"
0x3228f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32294  ldarg.3
0x32295  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeType()
0x3229a  ldc.i4.0
0x3229b  ldc.i4.0
0x3229c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write15_CrmAttributeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType o, bool isNullable, bool needType)
0x322a1  ldarg.0
0x322a2  ldstr    aDisplayname// "DisplayName"
0x322a7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x322ac  ldarg.3
0x322ad  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayName()
0x322b2  ldc.i4.0
0x322b3  ldc.i4.0
0x322b4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x322b9  ldarg.0
0x322ba  ldstr    aDescription// "Description"
0x322bf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x322c4  ldarg.3
0x322c5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_Description()
0x322ca  ldc.i4.0
0x322cb  ldc.i4.0
0x322cc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x322d1  ldarg.0
0x322d2  ldstr    aIscustomfield// "IsCustomField"
0x322d7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x322dc  ldarg.3
0x322dd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_IsCustomField()
0x322e2  ldc.i4.0
0x322e3  ldc.i4.0
0x322e4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x322e9  ldarg.0
0x322ea  ldstr    aRequiredlevel// "RequiredLevel"
0x322ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x322f4  ldarg.3
0x322f5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_RequiredLevel()
0x322fa  ldc.i4.0
0x322fb  ldc.i4.0
0x322fc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write17_CrmAttributeRequiredLevel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel o, bool isNullable, bool needType)
0x32301  ldarg.0
0x32302  ldstr    aDefaultvalue// "DefaultValue"
0x32307  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3230c  ldarg.3
0x3230d  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DefaultValue()
0x32312  ldc.i4.0
0x32313  ldc.i4.0
0x32314  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1_Object(string n, string ns, object o, bool isNullable, bool needType)
0x32319  ldarg.0
0x3231a  ldstr    aValidforcreate// "ValidForCreate"
0x3231f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32324  ldarg.3
0x32325  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForCreate()
0x3232a  ldc.i4.0
0x3232b  ldc.i4.0
0x3232c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x32331  ldarg.0
0x32332  ldstr    aValidforread// "ValidForRead"
0x32337  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3233c  ldarg.3
0x3233d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForRead()
0x32342  ldc.i4.0
0x32343  ldc.i4.0
0x32344  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x32349  ldarg.0
0x3234a  ldstr    aValidforupdate// "ValidForUpdate"
0x3234f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32354  ldarg.3
0x32355  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForUpdate()
0x3235a  ldc.i4.0
0x3235b  ldc.i4.0
0x3235c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x32361  ldarg.0
0x32362  ldstr    aDisplaymask// "DisplayMask"
0x32367  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3236c  ldarg.3
0x3236d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayMask()
0x32372  ldc.i4.0
0x32373  ldc.i4.0
0x32374  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write19_CrmDisplayMasks(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks o, bool isNullable, bool needType)
0x32379  ldarg.0
0x3237a  ldstr    aAggregateof// "AggregateOf"
0x3237f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32384  ldarg.3
0x32385  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AggregateOf()
0x3238a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3238f  ldarg.0
0x32390  ldstr    aAttributeof// "AttributeOf"
0x32395  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3239a  ldarg.3
0x3239b  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeOf()
0x323a0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x323a5  ldarg.0
0x323a6  ldstr    aYomiof// "YomiOf"
0x323ab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x323b0  ldarg.3
0x323b1  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_YomiOf()
0x323b6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x323bb  ldarg.0
0x323bc  ldstr    aCalculationof// "CalculationOf"
0x323c1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x323c6  ldarg.3
0x323c7  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_CalculationOf()
0x323cc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x323d1  ldarg.0
0x323d2  ldstr    aMinvalue// "MinValue"
0x323d7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x323dc  ldarg.3
0x323dd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.IntegerAttributeMetadata::get_MinValue()
0x323e2  ldc.i4.0
0x323e3  ldc.i4.0
0x323e4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write8_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x323e9  ldarg.0
0x323ea  ldstr    aMaxvalue// "MaxValue"
0x323ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x323f4  ldarg.3
0x323f5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.IntegerAttributeMetadata::get_MaxValue()
0x323fa  ldc.i4.0
0x323fb  ldc.i4.0
0x323fc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write8_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x32401  ldarg.0
0x32402  ldstr    aFormat// "Format"
0x32407  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3240c  ldarg.3
0x3240d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmIntegerFormat [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.IntegerAttributeMetadata::get_Format()
0x32412  ldc.i4.0
0x32413  ldc.i4.0
0x32414  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write27_CrmIntegerFormat(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmIntegerFormat o, bool isNullable, bool needType)
0x32419  ldarg.0
0x3241a  ldarg.3
0x3241b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x32420  ret
```
