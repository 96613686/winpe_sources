# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write25_MoneyAttributeMetadata

- ea: `0x31eb0`
- end: `0x32121`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write25_MoneyAttributeMetadata`
- size: `625`
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
- `0x31eb0`
- `0x32130`

## string_xrefs

- `0x31ef5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31f05`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31f1d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31f33`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31f49`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31f5f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31f77`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31f8f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31fa7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31fbf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31fd7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31fef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32007`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3201f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32037`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3204f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32065`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3207b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32091`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x320a7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x320bf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x320d7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x320ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32107`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31fea`: `ValidForCreate`
- `0x32002`: `ValidForRead`
- `0x3201a`: `ValidForUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x31eb0  ldarg.3
0x31eb1  brtrue.s loc_31EC0
0x31eb3  ldarg.s  4
0x31eb5  brfalse.s loc_31EBF
0x31eb7  ldarg.0
0x31eb8  ldarg.1
0x31eb9  ldarg.2
0x31eba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x31ebf  ret
0x31ec0  ldarg.s  5
0x31ec2  brtrue.s loc_31EE0
0x31ec4  ldarg.3
0x31ec5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x31eca  stloc.0
0x31ecb  ldloc.0
0x31ecc  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.MoneyAttributeMetadata
0x31ed1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31ed6  beq.s    loc_31EE0
0x31ed8  ldarg.0
0x31ed9  ldarg.3
0x31eda  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x31edf  throw
0x31ee0  ldarg.0
0x31ee1  ldarg.1
0x31ee2  ldarg.2
0x31ee3  ldarg.3
0x31ee4  ldc.i4.0
0x31ee5  ldnull
0x31ee6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x31eeb  ldarg.s  5
0x31eed  brfalse.s loc_31EFF
0x31eef  ldarg.0
0x31ef0  ldstr    aMoneyattribute// "MoneyAttributeMetadata"
0x31ef5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31efa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x31eff  ldarg.0
0x31f00  ldstr    aMetadataid// "MetadataId"
0x31f05  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31f0a  ldarg.3
0x31f0b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmMetadata::get_MetadataId()
0x31f10  ldc.i4.0
0x31f11  ldc.i4.0
0x31f12  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write6_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x31f17  ldarg.0
0x31f18  ldstr    aSchemaname// "SchemaName"
0x31f1d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31f22  ldarg.3
0x31f23  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_SchemaName()
0x31f28  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x31f2d  ldarg.0
0x31f2e  ldstr    aLogicalname// "LogicalName"
0x31f33  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31f38  ldarg.3
0x31f39  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_LogicalName()
0x31f3e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x31f43  ldarg.0
0x31f44  ldstr    aEntitylogicaln// "EntityLogicalName"
0x31f49  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31f4e  ldarg.3
0x31f4f  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_EntityLogicalName()
0x31f54  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x31f59  ldarg.0
0x31f5a  ldstr    aAttributetype// "AttributeType"
0x31f5f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31f64  ldarg.3
0x31f65  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeType()
0x31f6a  ldc.i4.0
0x31f6b  ldc.i4.0
0x31f6c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write15_CrmAttributeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType o, bool isNullable, bool needType)
0x31f71  ldarg.0
0x31f72  ldstr    aDisplayname// "DisplayName"
0x31f77  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31f7c  ldarg.3
0x31f7d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayName()
0x31f82  ldc.i4.0
0x31f83  ldc.i4.0
0x31f84  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x31f89  ldarg.0
0x31f8a  ldstr    aDescription// "Description"
0x31f8f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31f94  ldarg.3
0x31f95  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_Description()
0x31f9a  ldc.i4.0
0x31f9b  ldc.i4.0
0x31f9c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x31fa1  ldarg.0
0x31fa2  ldstr    aIscustomfield// "IsCustomField"
0x31fa7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31fac  ldarg.3
0x31fad  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_IsCustomField()
0x31fb2  ldc.i4.0
0x31fb3  ldc.i4.0
0x31fb4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x31fb9  ldarg.0
0x31fba  ldstr    aRequiredlevel// "RequiredLevel"
0x31fbf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31fc4  ldarg.3
0x31fc5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_RequiredLevel()
0x31fca  ldc.i4.0
0x31fcb  ldc.i4.0
0x31fcc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write17_CrmAttributeRequiredLevel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel o, bool isNullable, bool needType)
0x31fd1  ldarg.0
0x31fd2  ldstr    aDefaultvalue// "DefaultValue"
0x31fd7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31fdc  ldarg.3
0x31fdd  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DefaultValue()
0x31fe2  ldc.i4.0
0x31fe3  ldc.i4.0
0x31fe4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1_Object(string n, string ns, object o, bool isNullable, bool needType)
0x31fe9  ldarg.0
0x31fea  ldstr    aValidforcreate// "ValidForCreate"
0x31fef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31ff4  ldarg.3
0x31ff5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForCreate()
0x31ffa  ldc.i4.0
0x31ffb  ldc.i4.0
0x31ffc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x32001  ldarg.0
0x32002  ldstr    aValidforread// "ValidForRead"
0x32007  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3200c  ldarg.3
0x3200d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForRead()
0x32012  ldc.i4.0
0x32013  ldc.i4.0
0x32014  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x32019  ldarg.0
0x3201a  ldstr    aValidforupdate// "ValidForUpdate"
0x3201f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32024  ldarg.3
0x32025  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForUpdate()
0x3202a  ldc.i4.0
0x3202b  ldc.i4.0
0x3202c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x32031  ldarg.0
0x32032  ldstr    aDisplaymask// "DisplayMask"
0x32037  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3203c  ldarg.3
0x3203d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayMask()
0x32042  ldc.i4.0
0x32043  ldc.i4.0
0x32044  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write19_CrmDisplayMasks(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks o, bool isNullable, bool needType)
0x32049  ldarg.0
0x3204a  ldstr    aAggregateof// "AggregateOf"
0x3204f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32054  ldarg.3
0x32055  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AggregateOf()
0x3205a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3205f  ldarg.0
0x32060  ldstr    aAttributeof// "AttributeOf"
0x32065  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3206a  ldarg.3
0x3206b  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeOf()
0x32070  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32075  ldarg.0
0x32076  ldstr    aYomiof// "YomiOf"
0x3207b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32080  ldarg.3
0x32081  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_YomiOf()
0x32086  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3208b  ldarg.0
0x3208c  ldstr    aCalculationof// "CalculationOf"
0x32091  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32096  ldarg.3
0x32097  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_CalculationOf()
0x3209c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x320a1  ldarg.0
0x320a2  ldstr    aMinvalue// "MinValue"
0x320a7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x320ac  ldarg.3
0x320ad  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDouble [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.MoneyAttributeMetadata::get_MinValue()
0x320b2  ldc.i4.0
0x320b3  ldc.i4.0
0x320b4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write24_CrmDouble(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDouble o, bool isNullable, bool needType)
0x320b9  ldarg.0
0x320ba  ldstr    aMaxvalue// "MaxValue"
0x320bf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x320c4  ldarg.3
0x320c5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDouble [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.MoneyAttributeMetadata::get_MaxValue()
0x320ca  ldc.i4.0
0x320cb  ldc.i4.0
0x320cc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write24_CrmDouble(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDouble o, bool isNullable, bool needType)
0x320d1  ldarg.0
0x320d2  ldstr    aPrecision// "Precision"
0x320d7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x320dc  ldarg.3
0x320dd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.MoneyAttributeMetadata::get_Precision()
0x320e2  ldc.i4.0
0x320e3  ldc.i4.0
0x320e4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write8_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x320e9  ldarg.0
0x320ea  ldstr    aPrecisionsourc// "PrecisionSource"
0x320ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x320f4  ldarg.3
0x320f5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.MoneyAttributeMetadata::get_PrecisionSource()
0x320fa  ldc.i4.0
0x320fb  ldc.i4.0
0x320fc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write8_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x32101  ldarg.0
0x32102  ldstr    aImemode// "ImeMode"
0x32107  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3210c  ldarg.3
0x3210d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmImeMode [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.MoneyAttributeMetadata::get_ImeMode()
0x32112  ldc.i4.0
0x32113  ldc.i4.0
0x32114  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write22_CrmImeMode(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmImeMode o, bool isNullable, bool needType)
0x32119  ldarg.0
0x3211a  ldarg.3
0x3211b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x32120  ret
```
