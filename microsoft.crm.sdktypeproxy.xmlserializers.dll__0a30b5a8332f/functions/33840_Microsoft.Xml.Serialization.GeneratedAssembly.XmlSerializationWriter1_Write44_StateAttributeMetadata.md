# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write44_StateAttributeMetadata

- ea: `0x33840`
- end: `0x33a8a`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write44_StateAttributeMetadata`
- size: `586`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1940`
- `0x30290`
- `0x31530`

## callees

- `0x16f0`
- `0x1890`
- `0x1940`
- `0x30bf0`
- `0x30f10`
- `0x318b0`
- `0x319c0`
- `0x328e0`
- `0x33840`

## string_xrefs

- `0x33885`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33895`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x338ad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x338c3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x338d9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x338ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33907`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3391f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33937`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3394f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33967`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3397f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33997`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x339af`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x339c7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x339df`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x339f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33a0b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33a21`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33a41`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33a57`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3397a`: `ValidForCreate`
- `0x33992`: `ValidForRead`
- `0x339aa`: `ValidForUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x33840  ldarg.3
0x33841  brtrue.s loc_33850
0x33843  ldarg.s  4
0x33845  brfalse.s loc_3384F
0x33847  ldarg.0
0x33848  ldarg.1
0x33849  ldarg.2
0x3384a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x3384f  ret
0x33850  ldarg.s  5
0x33852  brtrue.s loc_33870
0x33854  ldarg.3
0x33855  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3385a  stloc.0
0x3385b  ldloc.0
0x3385c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StateAttributeMetadata
0x33861  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33866  beq.s    loc_33870
0x33868  ldarg.0
0x33869  ldarg.3
0x3386a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x3386f  throw
0x33870  ldarg.0
0x33871  ldarg.1
0x33872  ldarg.2
0x33873  ldarg.3
0x33874  ldc.i4.0
0x33875  ldnull
0x33876  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3387b  ldarg.s  5
0x3387d  brfalse.s loc_3388F
0x3387f  ldarg.0
0x33880  ldstr    aStateattribute// "StateAttributeMetadata"
0x33885  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3388a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3388f  ldarg.0
0x33890  ldstr    aMetadataid// "MetadataId"
0x33895  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3389a  ldarg.3
0x3389b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmMetadata::get_MetadataId()
0x338a0  ldc.i4.0
0x338a1  ldc.i4.0
0x338a2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write6_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x338a7  ldarg.0
0x338a8  ldstr    aSchemaname// "SchemaName"
0x338ad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x338b2  ldarg.3
0x338b3  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_SchemaName()
0x338b8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x338bd  ldarg.0
0x338be  ldstr    aLogicalname// "LogicalName"
0x338c3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x338c8  ldarg.3
0x338c9  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_LogicalName()
0x338ce  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x338d3  ldarg.0
0x338d4  ldstr    aEntitylogicaln// "EntityLogicalName"
0x338d9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x338de  ldarg.3
0x338df  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_EntityLogicalName()
0x338e4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x338e9  ldarg.0
0x338ea  ldstr    aAttributetype// "AttributeType"
0x338ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x338f4  ldarg.3
0x338f5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeType()
0x338fa  ldc.i4.0
0x338fb  ldc.i4.0
0x338fc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write15_CrmAttributeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType o, bool isNullable, bool needType)
0x33901  ldarg.0
0x33902  ldstr    aDisplayname// "DisplayName"
0x33907  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3390c  ldarg.3
0x3390d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayName()
0x33912  ldc.i4.0
0x33913  ldc.i4.0
0x33914  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x33919  ldarg.0
0x3391a  ldstr    aDescription// "Description"
0x3391f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33924  ldarg.3
0x33925  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_Description()
0x3392a  ldc.i4.0
0x3392b  ldc.i4.0
0x3392c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x33931  ldarg.0
0x33932  ldstr    aIscustomfield// "IsCustomField"
0x33937  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3393c  ldarg.3
0x3393d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_IsCustomField()
0x33942  ldc.i4.0
0x33943  ldc.i4.0
0x33944  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x33949  ldarg.0
0x3394a  ldstr    aRequiredlevel// "RequiredLevel"
0x3394f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33954  ldarg.3
0x33955  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_RequiredLevel()
0x3395a  ldc.i4.0
0x3395b  ldc.i4.0
0x3395c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write17_CrmAttributeRequiredLevel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel o, bool isNullable, bool needType)
0x33961  ldarg.0
0x33962  ldstr    aDefaultvalue// "DefaultValue"
0x33967  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3396c  ldarg.3
0x3396d  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DefaultValue()
0x33972  ldc.i4.0
0x33973  ldc.i4.0
0x33974  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1_Object(string n, string ns, object o, bool isNullable, bool needType)
0x33979  ldarg.0
0x3397a  ldstr    aValidforcreate// "ValidForCreate"
0x3397f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33984  ldarg.3
0x33985  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForCreate()
0x3398a  ldc.i4.0
0x3398b  ldc.i4.0
0x3398c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x33991  ldarg.0
0x33992  ldstr    aValidforread// "ValidForRead"
0x33997  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3399c  ldarg.3
0x3399d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForRead()
0x339a2  ldc.i4.0
0x339a3  ldc.i4.0
0x339a4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x339a9  ldarg.0
0x339aa  ldstr    aValidforupdate// "ValidForUpdate"
0x339af  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x339b4  ldarg.3
0x339b5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForUpdate()
0x339ba  ldc.i4.0
0x339bb  ldc.i4.0
0x339bc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x339c1  ldarg.0
0x339c2  ldstr    aDisplaymask// "DisplayMask"
0x339c7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x339cc  ldarg.3
0x339cd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayMask()
0x339d2  ldc.i4.0
0x339d3  ldc.i4.0
0x339d4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write19_CrmDisplayMasks(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks o, bool isNullable, bool needType)
0x339d9  ldarg.0
0x339da  ldstr    aAggregateof// "AggregateOf"
0x339df  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x339e4  ldarg.3
0x339e5  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AggregateOf()
0x339ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x339ef  ldarg.0
0x339f0  ldstr    aAttributeof// "AttributeOf"
0x339f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x339fa  ldarg.3
0x339fb  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeOf()
0x33a00  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x33a05  ldarg.0
0x33a06  ldstr    aYomiof// "YomiOf"
0x33a0b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33a10  ldarg.3
0x33a11  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_YomiOf()
0x33a16  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x33a1b  ldarg.0
0x33a1c  ldstr    aCalculationof// "CalculationOf"
0x33a21  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33a26  ldarg.3
0x33a27  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_CalculationOf()
0x33a2c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x33a31  ldarg.3
0x33a32  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StateAttributeMetadata::get_Options()
0x33a37  stloc.1
0x33a38  ldloc.1
0x33a39  brfalse.s loc_33A82
0x33a3b  ldarg.0
0x33a3c  ldstr    aOptions// "Options"
0x33a41  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33a46  ldnull
0x33a47  ldc.i4.0
0x33a48  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x33a4d  ldc.i4.0
0x33a4e  stloc.2
0x33a4f  br.s     loc_33A73
0x33a51  ldarg.0
0x33a52  ldstr    aStateoption// "StateOption"
0x33a57  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33a5c  ldloc.1
0x33a5d  ldloc.2
0x33a5e  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x33a63  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StateOption
0x33a68  ldc.i4.0
0x33a69  ldc.i4.0
0x33a6a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write43_StateOption(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StateOption o, bool isNullable, bool needType)
0x33a6f  ldloc.2
0x33a70  ldc.i4.1
0x33a71  add
0x33a72  stloc.2
0x33a73  ldloc.2
0x33a74  ldloc.1
0x33a75  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x33a7a  blt.s    loc_33A51
0x33a7c  ldarg.0
0x33a7d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x33a82  ldarg.0
0x33a83  ldarg.3
0x33a84  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x33a89  ret
```
