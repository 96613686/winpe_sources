# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write37_DecimalAttributeMetadata

- ea: `0x33160`
- end: `0x333a1`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write37_DecimalAttributeMetadata`
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
- `0x32130`
- `0x33160`

## string_xrefs

- `0x331a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x331b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x331cd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x331e3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x331f9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3320f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33227`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3323f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33257`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3326f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33287`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3329f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x332b7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x332cf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x332e7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x332ff`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33315`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3332b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33341`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33357`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3336f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33387`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3329a`: `ValidForCreate`
- `0x332b2`: `ValidForRead`
- `0x332ca`: `ValidForUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x33160  ldarg.3
0x33161  brtrue.s loc_33170
0x33163  ldarg.s  4
0x33165  brfalse.s loc_3316F
0x33167  ldarg.0
0x33168  ldarg.1
0x33169  ldarg.2
0x3316a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x3316f  ret
0x33170  ldarg.s  5
0x33172  brtrue.s loc_33190
0x33174  ldarg.3
0x33175  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3317a  stloc.0
0x3317b  ldloc.0
0x3317c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.DecimalAttributeMetadata
0x33181  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33186  beq.s    loc_33190
0x33188  ldarg.0
0x33189  ldarg.3
0x3318a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x3318f  throw
0x33190  ldarg.0
0x33191  ldarg.1
0x33192  ldarg.2
0x33193  ldarg.3
0x33194  ldc.i4.0
0x33195  ldnull
0x33196  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3319b  ldarg.s  5
0x3319d  brfalse.s loc_331AF
0x3319f  ldarg.0
0x331a0  ldstr    aDecimalattribu// "DecimalAttributeMetadata"
0x331a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x331aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x331af  ldarg.0
0x331b0  ldstr    aMetadataid// "MetadataId"
0x331b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x331ba  ldarg.3
0x331bb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmMetadata::get_MetadataId()
0x331c0  ldc.i4.0
0x331c1  ldc.i4.0
0x331c2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write6_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x331c7  ldarg.0
0x331c8  ldstr    aSchemaname// "SchemaName"
0x331cd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x331d2  ldarg.3
0x331d3  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_SchemaName()
0x331d8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x331dd  ldarg.0
0x331de  ldstr    aLogicalname// "LogicalName"
0x331e3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x331e8  ldarg.3
0x331e9  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_LogicalName()
0x331ee  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x331f3  ldarg.0
0x331f4  ldstr    aEntitylogicaln// "EntityLogicalName"
0x331f9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x331fe  ldarg.3
0x331ff  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_EntityLogicalName()
0x33204  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x33209  ldarg.0
0x3320a  ldstr    aAttributetype// "AttributeType"
0x3320f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33214  ldarg.3
0x33215  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeType()
0x3321a  ldc.i4.0
0x3321b  ldc.i4.0
0x3321c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write15_CrmAttributeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType o, bool isNullable, bool needType)
0x33221  ldarg.0
0x33222  ldstr    aDisplayname// "DisplayName"
0x33227  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3322c  ldarg.3
0x3322d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayName()
0x33232  ldc.i4.0
0x33233  ldc.i4.0
0x33234  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x33239  ldarg.0
0x3323a  ldstr    aDescription// "Description"
0x3323f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33244  ldarg.3
0x33245  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_Description()
0x3324a  ldc.i4.0
0x3324b  ldc.i4.0
0x3324c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x33251  ldarg.0
0x33252  ldstr    aIscustomfield// "IsCustomField"
0x33257  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3325c  ldarg.3
0x3325d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_IsCustomField()
0x33262  ldc.i4.0
0x33263  ldc.i4.0
0x33264  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x33269  ldarg.0
0x3326a  ldstr    aRequiredlevel// "RequiredLevel"
0x3326f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33274  ldarg.3
0x33275  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_RequiredLevel()
0x3327a  ldc.i4.0
0x3327b  ldc.i4.0
0x3327c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write17_CrmAttributeRequiredLevel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel o, bool isNullable, bool needType)
0x33281  ldarg.0
0x33282  ldstr    aDefaultvalue// "DefaultValue"
0x33287  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3328c  ldarg.3
0x3328d  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DefaultValue()
0x33292  ldc.i4.0
0x33293  ldc.i4.0
0x33294  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1_Object(string n, string ns, object o, bool isNullable, bool needType)
0x33299  ldarg.0
0x3329a  ldstr    aValidforcreate// "ValidForCreate"
0x3329f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x332a4  ldarg.3
0x332a5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForCreate()
0x332aa  ldc.i4.0
0x332ab  ldc.i4.0
0x332ac  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x332b1  ldarg.0
0x332b2  ldstr    aValidforread// "ValidForRead"
0x332b7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x332bc  ldarg.3
0x332bd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForRead()
0x332c2  ldc.i4.0
0x332c3  ldc.i4.0
0x332c4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x332c9  ldarg.0
0x332ca  ldstr    aValidforupdate// "ValidForUpdate"
0x332cf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x332d4  ldarg.3
0x332d5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForUpdate()
0x332da  ldc.i4.0
0x332db  ldc.i4.0
0x332dc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x332e1  ldarg.0
0x332e2  ldstr    aDisplaymask// "DisplayMask"
0x332e7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x332ec  ldarg.3
0x332ed  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayMask()
0x332f2  ldc.i4.0
0x332f3  ldc.i4.0
0x332f4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write19_CrmDisplayMasks(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks o, bool isNullable, bool needType)
0x332f9  ldarg.0
0x332fa  ldstr    aAggregateof// "AggregateOf"
0x332ff  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33304  ldarg.3
0x33305  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AggregateOf()
0x3330a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3330f  ldarg.0
0x33310  ldstr    aAttributeof// "AttributeOf"
0x33315  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3331a  ldarg.3
0x3331b  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeOf()
0x33320  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x33325  ldarg.0
0x33326  ldstr    aYomiof// "YomiOf"
0x3332b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33330  ldarg.3
0x33331  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_YomiOf()
0x33336  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3333b  ldarg.0
0x3333c  ldstr    aCalculationof// "CalculationOf"
0x33341  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33346  ldarg.3
0x33347  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_CalculationOf()
0x3334c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x33351  ldarg.0
0x33352  ldstr    aMinvalue// "MinValue"
0x33357  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3335c  ldarg.3
0x3335d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDouble [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.DecimalAttributeMetadata::get_MinValue()
0x33362  ldc.i4.0
0x33363  ldc.i4.0
0x33364  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write24_CrmDouble(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDouble o, bool isNullable, bool needType)
0x33369  ldarg.0
0x3336a  ldstr    aMaxvalue// "MaxValue"
0x3336f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33374  ldarg.3
0x33375  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDouble [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.DecimalAttributeMetadata::get_MaxValue()
0x3337a  ldc.i4.0
0x3337b  ldc.i4.0
0x3337c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write24_CrmDouble(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDouble o, bool isNullable, bool needType)
0x33381  ldarg.0
0x33382  ldstr    aPrecision// "Precision"
0x33387  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3338c  ldarg.3
0x3338d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.DecimalAttributeMetadata::get_Precision()
0x33392  ldc.i4.0
0x33393  ldc.i4.0
0x33394  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write8_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x33399  ldarg.0
0x3339a  ldarg.3
0x3339b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x333a0  ret
```
