# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write30_BooleanAttributeMetadata

- ea: `0x32540`
- end: `0x32769`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write30_BooleanAttributeMetadata`
- size: `553`
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
- `0x32540`
- `0x32770`

## string_xrefs

- `0x32585`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32595`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x325ad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x325c3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x325d9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x325ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32607`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3261f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32637`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3264f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32667`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3267f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32697`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x326af`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x326c7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x326df`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x326f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3270b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32721`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x32737`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3274f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3267a`: `ValidForCreate`
- `0x32692`: `ValidForRead`
- `0x326aa`: `ValidForUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x32540  ldarg.3
0x32541  brtrue.s loc_32550
0x32543  ldarg.s  4
0x32545  brfalse.s loc_3254F
0x32547  ldarg.0
0x32548  ldarg.1
0x32549  ldarg.2
0x3254a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x3254f  ret
0x32550  ldarg.s  5
0x32552  brtrue.s loc_32570
0x32554  ldarg.3
0x32555  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3255a  stloc.0
0x3255b  ldloc.0
0x3255c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.BooleanAttributeMetadata
0x32561  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32566  beq.s    loc_32570
0x32568  ldarg.0
0x32569  ldarg.3
0x3256a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x3256f  throw
0x32570  ldarg.0
0x32571  ldarg.1
0x32572  ldarg.2
0x32573  ldarg.3
0x32574  ldc.i4.0
0x32575  ldnull
0x32576  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3257b  ldarg.s  5
0x3257d  brfalse.s loc_3258F
0x3257f  ldarg.0
0x32580  ldstr    aBooleanattribu// "BooleanAttributeMetadata"
0x32585  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3258a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3258f  ldarg.0
0x32590  ldstr    aMetadataid// "MetadataId"
0x32595  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3259a  ldarg.3
0x3259b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmMetadata::get_MetadataId()
0x325a0  ldc.i4.0
0x325a1  ldc.i4.0
0x325a2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write6_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x325a7  ldarg.0
0x325a8  ldstr    aSchemaname// "SchemaName"
0x325ad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x325b2  ldarg.3
0x325b3  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_SchemaName()
0x325b8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x325bd  ldarg.0
0x325be  ldstr    aLogicalname// "LogicalName"
0x325c3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x325c8  ldarg.3
0x325c9  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_LogicalName()
0x325ce  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x325d3  ldarg.0
0x325d4  ldstr    aEntitylogicaln// "EntityLogicalName"
0x325d9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x325de  ldarg.3
0x325df  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_EntityLogicalName()
0x325e4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x325e9  ldarg.0
0x325ea  ldstr    aAttributetype// "AttributeType"
0x325ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x325f4  ldarg.3
0x325f5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeType()
0x325fa  ldc.i4.0
0x325fb  ldc.i4.0
0x325fc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write15_CrmAttributeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType o, bool isNullable, bool needType)
0x32601  ldarg.0
0x32602  ldstr    aDisplayname// "DisplayName"
0x32607  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3260c  ldarg.3
0x3260d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayName()
0x32612  ldc.i4.0
0x32613  ldc.i4.0
0x32614  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x32619  ldarg.0
0x3261a  ldstr    aDescription// "Description"
0x3261f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32624  ldarg.3
0x32625  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_Description()
0x3262a  ldc.i4.0
0x3262b  ldc.i4.0
0x3262c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x32631  ldarg.0
0x32632  ldstr    aIscustomfield// "IsCustomField"
0x32637  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3263c  ldarg.3
0x3263d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_IsCustomField()
0x32642  ldc.i4.0
0x32643  ldc.i4.0
0x32644  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x32649  ldarg.0
0x3264a  ldstr    aRequiredlevel// "RequiredLevel"
0x3264f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32654  ldarg.3
0x32655  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_RequiredLevel()
0x3265a  ldc.i4.0
0x3265b  ldc.i4.0
0x3265c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write17_CrmAttributeRequiredLevel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel o, bool isNullable, bool needType)
0x32661  ldarg.0
0x32662  ldstr    aDefaultvalue// "DefaultValue"
0x32667  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3266c  ldarg.3
0x3266d  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DefaultValue()
0x32672  ldc.i4.0
0x32673  ldc.i4.0
0x32674  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1_Object(string n, string ns, object o, bool isNullable, bool needType)
0x32679  ldarg.0
0x3267a  ldstr    aValidforcreate// "ValidForCreate"
0x3267f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32684  ldarg.3
0x32685  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForCreate()
0x3268a  ldc.i4.0
0x3268b  ldc.i4.0
0x3268c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x32691  ldarg.0
0x32692  ldstr    aValidforread// "ValidForRead"
0x32697  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3269c  ldarg.3
0x3269d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForRead()
0x326a2  ldc.i4.0
0x326a3  ldc.i4.0
0x326a4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x326a9  ldarg.0
0x326aa  ldstr    aValidforupdate// "ValidForUpdate"
0x326af  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x326b4  ldarg.3
0x326b5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForUpdate()
0x326ba  ldc.i4.0
0x326bb  ldc.i4.0
0x326bc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x326c1  ldarg.0
0x326c2  ldstr    aDisplaymask// "DisplayMask"
0x326c7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x326cc  ldarg.3
0x326cd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayMask()
0x326d2  ldc.i4.0
0x326d3  ldc.i4.0
0x326d4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write19_CrmDisplayMasks(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks o, bool isNullable, bool needType)
0x326d9  ldarg.0
0x326da  ldstr    aAggregateof// "AggregateOf"
0x326df  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x326e4  ldarg.3
0x326e5  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AggregateOf()
0x326ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x326ef  ldarg.0
0x326f0  ldstr    aAttributeof// "AttributeOf"
0x326f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x326fa  ldarg.3
0x326fb  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeOf()
0x32700  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32705  ldarg.0
0x32706  ldstr    aYomiof// "YomiOf"
0x3270b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32710  ldarg.3
0x32711  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_YomiOf()
0x32716  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3271b  ldarg.0
0x3271c  ldstr    aCalculationof// "CalculationOf"
0x32721  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32726  ldarg.3
0x32727  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_CalculationOf()
0x3272c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x32731  ldarg.0
0x32732  ldstr    aTrueoption// "TrueOption"
0x32737  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3273c  ldarg.3
0x3273d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.Option [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.BooleanAttributeMetadata::get_TrueOption()
0x32742  ldc.i4.0
0x32743  ldc.i4.0
0x32744  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write29_Option(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.Option o, bool isNullable, bool needType)
0x32749  ldarg.0
0x3274a  ldstr    aFalseoption// "FalseOption"
0x3274f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x32754  ldarg.3
0x32755  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.Option [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.BooleanAttributeMetadata::get_FalseOption()
0x3275a  ldc.i4.0
0x3275b  ldc.i4.0
0x3275c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write29_Option(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.Option o, bool isNullable, bool needType)
0x32761  ldarg.0
0x32762  ldarg.3
0x32763  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x32768  ret
```
