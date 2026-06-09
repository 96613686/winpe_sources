# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write40_MemoAttributeMetadata

- ea: `0x333b0`
- end: `0x335f1`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write40_MemoAttributeMetadata`
- size: `577`
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
- `0x15d0`
- `0x16f0`
- `0x1890`
- `0x1940`
- `0x30bf0`
- `0x30f10`
- `0x318b0`
- `0x319c0`
- `0x333b0`

## string_xrefs

- `0x333f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33405`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3341d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33433`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33449`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3345f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33477`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3348f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x334a7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x334bf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x334d7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x334ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33507`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3351f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33537`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3354f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33565`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3357b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33591`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x335a7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x335bf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x335d7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x334ea`: `ValidForCreate`
- `0x33502`: `ValidForRead`
- `0x3351a`: `ValidForUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x333b0  ldarg.3
0x333b1  brtrue.s loc_333C0
0x333b3  ldarg.s  4
0x333b5  brfalse.s loc_333BF
0x333b7  ldarg.0
0x333b8  ldarg.1
0x333b9  ldarg.2
0x333ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x333bf  ret
0x333c0  ldarg.s  5
0x333c2  brtrue.s loc_333E0
0x333c4  ldarg.3
0x333c5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x333ca  stloc.0
0x333cb  ldloc.0
0x333cc  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.MemoAttributeMetadata
0x333d1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x333d6  beq.s    loc_333E0
0x333d8  ldarg.0
0x333d9  ldarg.3
0x333da  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x333df  throw
0x333e0  ldarg.0
0x333e1  ldarg.1
0x333e2  ldarg.2
0x333e3  ldarg.3
0x333e4  ldc.i4.0
0x333e5  ldnull
0x333e6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x333eb  ldarg.s  5
0x333ed  brfalse.s loc_333FF
0x333ef  ldarg.0
0x333f0  ldstr    aMemoattributem// "MemoAttributeMetadata"
0x333f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x333fa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x333ff  ldarg.0
0x33400  ldstr    aMetadataid// "MetadataId"
0x33405  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3340a  ldarg.3
0x3340b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmMetadata::get_MetadataId()
0x33410  ldc.i4.0
0x33411  ldc.i4.0
0x33412  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write6_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x33417  ldarg.0
0x33418  ldstr    aSchemaname// "SchemaName"
0x3341d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33422  ldarg.3
0x33423  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_SchemaName()
0x33428  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3342d  ldarg.0
0x3342e  ldstr    aLogicalname// "LogicalName"
0x33433  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33438  ldarg.3
0x33439  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_LogicalName()
0x3343e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x33443  ldarg.0
0x33444  ldstr    aEntitylogicaln// "EntityLogicalName"
0x33449  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3344e  ldarg.3
0x3344f  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_EntityLogicalName()
0x33454  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x33459  ldarg.0
0x3345a  ldstr    aAttributetype// "AttributeType"
0x3345f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33464  ldarg.3
0x33465  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeType()
0x3346a  ldc.i4.0
0x3346b  ldc.i4.0
0x3346c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write15_CrmAttributeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType o, bool isNullable, bool needType)
0x33471  ldarg.0
0x33472  ldstr    aDisplayname// "DisplayName"
0x33477  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3347c  ldarg.3
0x3347d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayName()
0x33482  ldc.i4.0
0x33483  ldc.i4.0
0x33484  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x33489  ldarg.0
0x3348a  ldstr    aDescription// "Description"
0x3348f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33494  ldarg.3
0x33495  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_Description()
0x3349a  ldc.i4.0
0x3349b  ldc.i4.0
0x3349c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x334a1  ldarg.0
0x334a2  ldstr    aIscustomfield// "IsCustomField"
0x334a7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x334ac  ldarg.3
0x334ad  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_IsCustomField()
0x334b2  ldc.i4.0
0x334b3  ldc.i4.0
0x334b4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x334b9  ldarg.0
0x334ba  ldstr    aRequiredlevel// "RequiredLevel"
0x334bf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x334c4  ldarg.3
0x334c5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_RequiredLevel()
0x334ca  ldc.i4.0
0x334cb  ldc.i4.0
0x334cc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write17_CrmAttributeRequiredLevel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel o, bool isNullable, bool needType)
0x334d1  ldarg.0
0x334d2  ldstr    aDefaultvalue// "DefaultValue"
0x334d7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x334dc  ldarg.3
0x334dd  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DefaultValue()
0x334e2  ldc.i4.0
0x334e3  ldc.i4.0
0x334e4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1_Object(string n, string ns, object o, bool isNullable, bool needType)
0x334e9  ldarg.0
0x334ea  ldstr    aValidforcreate// "ValidForCreate"
0x334ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x334f4  ldarg.3
0x334f5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForCreate()
0x334fa  ldc.i4.0
0x334fb  ldc.i4.0
0x334fc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x33501  ldarg.0
0x33502  ldstr    aValidforread// "ValidForRead"
0x33507  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3350c  ldarg.3
0x3350d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForRead()
0x33512  ldc.i4.0
0x33513  ldc.i4.0
0x33514  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x33519  ldarg.0
0x3351a  ldstr    aValidforupdate// "ValidForUpdate"
0x3351f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33524  ldarg.3
0x33525  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForUpdate()
0x3352a  ldc.i4.0
0x3352b  ldc.i4.0
0x3352c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x33531  ldarg.0
0x33532  ldstr    aDisplaymask// "DisplayMask"
0x33537  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3353c  ldarg.3
0x3353d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayMask()
0x33542  ldc.i4.0
0x33543  ldc.i4.0
0x33544  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write19_CrmDisplayMasks(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks o, bool isNullable, bool needType)
0x33549  ldarg.0
0x3354a  ldstr    aAggregateof// "AggregateOf"
0x3354f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33554  ldarg.3
0x33555  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AggregateOf()
0x3355a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3355f  ldarg.0
0x33560  ldstr    aAttributeof// "AttributeOf"
0x33565  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3356a  ldarg.3
0x3356b  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeOf()
0x33570  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x33575  ldarg.0
0x33576  ldstr    aYomiof// "YomiOf"
0x3357b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33580  ldarg.3
0x33581  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_YomiOf()
0x33586  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3358b  ldarg.0
0x3358c  ldstr    aCalculationof// "CalculationOf"
0x33591  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33596  ldarg.3
0x33597  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_CalculationOf()
0x3359c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x335a1  ldarg.0
0x335a2  ldstr    aFormat// "Format"
0x335a7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x335ac  ldarg.3
0x335ad  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmStringFormat [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.MemoAttributeMetadata::get_Format()
0x335b2  ldc.i4.0
0x335b3  ldc.i4.0
0x335b4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write39_CrmStringFormat(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmStringFormat o, bool isNullable, bool needType)
0x335b9  ldarg.0
0x335ba  ldstr    aMaxlength// "MaxLength"
0x335bf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x335c4  ldarg.3
0x335c5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.MemoAttributeMetadata::get_MaxLength()
0x335ca  ldc.i4.0
0x335cb  ldc.i4.0
0x335cc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write8_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x335d1  ldarg.0
0x335d2  ldstr    aImemode// "ImeMode"
0x335d7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x335dc  ldarg.3
0x335dd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmImeMode [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.MemoAttributeMetadata::get_ImeMode()
0x335e2  ldc.i4.0
0x335e3  ldc.i4.0
0x335e4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write22_CrmImeMode(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmImeMode o, bool isNullable, bool needType)
0x335e9  ldarg.0
0x335ea  ldarg.3
0x335eb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x335f0  ret
```
