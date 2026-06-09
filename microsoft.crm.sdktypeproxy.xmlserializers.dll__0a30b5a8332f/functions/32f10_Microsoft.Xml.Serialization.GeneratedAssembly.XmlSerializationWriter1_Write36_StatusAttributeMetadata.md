# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write36_StatusAttributeMetadata

- ea: `0x32f10`
- end: `0x3315a`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write36_StatusAttributeMetadata`
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
- `0x32840`
- `0x32f10`

## string_xrefs

- `0x32f55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32f65`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32f7d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32f93`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32fa9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32fbf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32fd7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32fef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33007`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3301f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33037`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3304f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33067`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3307f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33097`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x330af`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x330c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x330db`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x330f1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33111`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33127`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3304a`: `ValidForCreate`
- `0x33062`: `ValidForRead`
- `0x3307a`: `ValidForUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x32f10  ldarg.3
0x32f11  brtrue.s loc_32F20
0x32f13  ldarg.s  4
0x32f15  brfalse.s loc_32F1F
0x32f17  ldarg.0
0x32f18  ldarg.1
0x32f19  ldarg.2
0x32f1a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x32f1f  ret
0x32f20  ldarg.s  5
0x32f22  brtrue.s loc_32F40
0x32f24  ldarg.3
0x32f25  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x32f2a  stloc.0
0x32f2b  ldloc.0
0x32f2c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StatusAttributeMetadata
0x32f31  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32f36  beq.s    loc_32F40
0x32f38  ldarg.0
0x32f39  ldarg.3
0x32f3a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x32f3f  throw
0x32f40  ldarg.0
0x32f41  ldarg.1
0x32f42  ldarg.2
0x32f43  ldarg.3
0x32f44  ldc.i4.0
0x32f45  ldnull
0x32f46  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x32f4b  ldarg.s  5
0x32f4d  brfalse.s loc_32F5F
0x32f4f  ldarg.0
0x32f50  ldstr    aStatusattribut// "StatusAttributeMetadata"
0x32f55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32f5a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x32f5f  ldarg.0
0x32f60  ldstr    aMetadataid// "MetadataId"
0x32f65  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32f6a  ldarg.3
0x32f6b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmMetadata::get_MetadataId()
0x32f70  ldc.i4.0
0x32f71  ldc.i4.0
0x32f72  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write6_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x32f77  ldarg.0
0x32f78  ldstr    aSchemaname// "SchemaName"
0x32f7d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32f82  ldarg.3
0x32f83  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_SchemaName()
0x32f88  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32f8d  ldarg.0
0x32f8e  ldstr    aLogicalname// "LogicalName"
0x32f93  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32f98  ldarg.3
0x32f99  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_LogicalName()
0x32f9e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32fa3  ldarg.0
0x32fa4  ldstr    aEntitylogicaln// "EntityLogicalName"
0x32fa9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32fae  ldarg.3
0x32faf  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_EntityLogicalName()
0x32fb4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32fb9  ldarg.0
0x32fba  ldstr    aAttributetype// "AttributeType"
0x32fbf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32fc4  ldarg.3
0x32fc5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeType()
0x32fca  ldc.i4.0
0x32fcb  ldc.i4.0
0x32fcc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write15_CrmAttributeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType o, bool isNullable, bool needType)
0x32fd1  ldarg.0
0x32fd2  ldstr    aDisplayname// "DisplayName"
0x32fd7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32fdc  ldarg.3
0x32fdd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayName()
0x32fe2  ldc.i4.0
0x32fe3  ldc.i4.0
0x32fe4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x32fe9  ldarg.0
0x32fea  ldstr    aDescription// "Description"
0x32fef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32ff4  ldarg.3
0x32ff5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_Description()
0x32ffa  ldc.i4.0
0x32ffb  ldc.i4.0
0x32ffc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x33001  ldarg.0
0x33002  ldstr    aIscustomfield// "IsCustomField"
0x33007  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3300c  ldarg.3
0x3300d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_IsCustomField()
0x33012  ldc.i4.0
0x33013  ldc.i4.0
0x33014  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x33019  ldarg.0
0x3301a  ldstr    aRequiredlevel// "RequiredLevel"
0x3301f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33024  ldarg.3
0x33025  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_RequiredLevel()
0x3302a  ldc.i4.0
0x3302b  ldc.i4.0
0x3302c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write17_CrmAttributeRequiredLevel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel o, bool isNullable, bool needType)
0x33031  ldarg.0
0x33032  ldstr    aDefaultvalue// "DefaultValue"
0x33037  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3303c  ldarg.3
0x3303d  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DefaultValue()
0x33042  ldc.i4.0
0x33043  ldc.i4.0
0x33044  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1_Object(string n, string ns, object o, bool isNullable, bool needType)
0x33049  ldarg.0
0x3304a  ldstr    aValidforcreate// "ValidForCreate"
0x3304f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33054  ldarg.3
0x33055  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForCreate()
0x3305a  ldc.i4.0
0x3305b  ldc.i4.0
0x3305c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x33061  ldarg.0
0x33062  ldstr    aValidforread// "ValidForRead"
0x33067  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3306c  ldarg.3
0x3306d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForRead()
0x33072  ldc.i4.0
0x33073  ldc.i4.0
0x33074  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x33079  ldarg.0
0x3307a  ldstr    aValidforupdate// "ValidForUpdate"
0x3307f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33084  ldarg.3
0x33085  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForUpdate()
0x3308a  ldc.i4.0
0x3308b  ldc.i4.0
0x3308c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x33091  ldarg.0
0x33092  ldstr    aDisplaymask// "DisplayMask"
0x33097  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3309c  ldarg.3
0x3309d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayMask()
0x330a2  ldc.i4.0
0x330a3  ldc.i4.0
0x330a4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write19_CrmDisplayMasks(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks o, bool isNullable, bool needType)
0x330a9  ldarg.0
0x330aa  ldstr    aAggregateof// "AggregateOf"
0x330af  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x330b4  ldarg.3
0x330b5  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AggregateOf()
0x330ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x330bf  ldarg.0
0x330c0  ldstr    aAttributeof// "AttributeOf"
0x330c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x330ca  ldarg.3
0x330cb  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeOf()
0x330d0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x330d5  ldarg.0
0x330d6  ldstr    aYomiof// "YomiOf"
0x330db  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x330e0  ldarg.3
0x330e1  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_YomiOf()
0x330e6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x330eb  ldarg.0
0x330ec  ldstr    aCalculationof// "CalculationOf"
0x330f1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x330f6  ldarg.3
0x330f7  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_CalculationOf()
0x330fc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x33101  ldarg.3
0x33102  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StatusAttributeMetadata::get_Options()
0x33107  stloc.1
0x33108  ldloc.1
0x33109  brfalse.s loc_33152
0x3310b  ldarg.0
0x3310c  ldstr    aOptions// "Options"
0x33111  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33116  ldnull
0x33117  ldc.i4.0
0x33118  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3311d  ldc.i4.0
0x3311e  stloc.2
0x3311f  br.s     loc_33143
0x33121  ldarg.0
0x33122  ldstr    aStatusoption// "StatusOption"
0x33127  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3312c  ldloc.1
0x3312d  ldloc.2
0x3312e  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x33133  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StatusOption
0x33138  ldc.i4.0
0x33139  ldc.i4.0
0x3313a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write35_StatusOption(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.StatusOption o, bool isNullable, bool needType)
0x3313f  ldloc.2
0x33140  ldc.i4.1
0x33141  add
0x33142  stloc.2
0x33143  ldloc.2
0x33144  ldloc.1
0x33145  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x3314a  blt.s    loc_33121
0x3314c  ldarg.0
0x3314d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x33152  ldarg.0
0x33153  ldarg.3
0x33154  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x33159  ret
```
