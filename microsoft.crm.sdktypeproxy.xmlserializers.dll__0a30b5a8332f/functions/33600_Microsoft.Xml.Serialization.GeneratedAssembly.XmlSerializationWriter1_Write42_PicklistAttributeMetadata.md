# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write42_PicklistAttributeMetadata

- ea: `0x33600`
- end: `0x3383e`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write42_PicklistAttributeMetadata`
- size: `574`
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
- `0x32770`
- `0x33600`

## string_xrefs

- `0x33645`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33655`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3366d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33683`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33699`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x336af`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x336c7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x336df`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x336f7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3370f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33727`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3373f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33757`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3376f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33787`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3379f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x337b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x337cb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x337e1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33801`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33817`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3373a`: `ValidForCreate`
- `0x33752`: `ValidForRead`
- `0x3376a`: `ValidForUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x33600  ldarg.3
0x33601  brtrue.s loc_33610
0x33603  ldarg.s  4
0x33605  brfalse.s loc_3360F
0x33607  ldarg.0
0x33608  ldarg.1
0x33609  ldarg.2
0x3360a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x3360f  ret
0x33610  ldarg.s  5
0x33612  brtrue.s loc_33630
0x33614  ldarg.3
0x33615  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3361a  stloc.0
0x3361b  ldloc.0
0x3361c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.PicklistAttributeMetadata
0x33621  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33626  beq.s    loc_33630
0x33628  ldarg.0
0x33629  ldarg.3
0x3362a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x3362f  throw
0x33630  ldarg.0
0x33631  ldarg.1
0x33632  ldarg.2
0x33633  ldarg.3
0x33634  ldc.i4.0
0x33635  ldnull
0x33636  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3363b  ldarg.s  5
0x3363d  brfalse.s loc_3364F
0x3363f  ldarg.0
0x33640  ldstr    aPicklistattrib// "PicklistAttributeMetadata"
0x33645  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3364a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3364f  ldarg.0
0x33650  ldstr    aMetadataid// "MetadataId"
0x33655  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3365a  ldarg.3
0x3365b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmMetadata::get_MetadataId()
0x33660  ldc.i4.0
0x33661  ldc.i4.0
0x33662  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write6_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x33667  ldarg.0
0x33668  ldstr    aSchemaname// "SchemaName"
0x3366d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33672  ldarg.3
0x33673  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_SchemaName()
0x33678  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3367d  ldarg.0
0x3367e  ldstr    aLogicalname// "LogicalName"
0x33683  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33688  ldarg.3
0x33689  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_LogicalName()
0x3368e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x33693  ldarg.0
0x33694  ldstr    aEntitylogicaln// "EntityLogicalName"
0x33699  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3369e  ldarg.3
0x3369f  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_EntityLogicalName()
0x336a4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x336a9  ldarg.0
0x336aa  ldstr    aAttributetype// "AttributeType"
0x336af  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x336b4  ldarg.3
0x336b5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeType()
0x336ba  ldc.i4.0
0x336bb  ldc.i4.0
0x336bc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write15_CrmAttributeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeType o, bool isNullable, bool needType)
0x336c1  ldarg.0
0x336c2  ldstr    aDisplayname// "DisplayName"
0x336c7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x336cc  ldarg.3
0x336cd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayName()
0x336d2  ldc.i4.0
0x336d3  ldc.i4.0
0x336d4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x336d9  ldarg.0
0x336da  ldstr    aDescription// "Description"
0x336df  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x336e4  ldarg.3
0x336e5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_Description()
0x336ea  ldc.i4.0
0x336eb  ldc.i4.0
0x336ec  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write10_CrmLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel o, bool isNullable, bool needType)
0x336f1  ldarg.0
0x336f2  ldstr    aIscustomfield// "IsCustomField"
0x336f7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x336fc  ldarg.3
0x336fd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_IsCustomField()
0x33702  ldc.i4.0
0x33703  ldc.i4.0
0x33704  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x33709  ldarg.0
0x3370a  ldstr    aRequiredlevel// "RequiredLevel"
0x3370f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33714  ldarg.3
0x33715  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_RequiredLevel()
0x3371a  ldc.i4.0
0x3371b  ldc.i4.0
0x3371c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write17_CrmAttributeRequiredLevel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmAttributeRequiredLevel o, bool isNullable, bool needType)
0x33721  ldarg.0
0x33722  ldstr    aDefaultvalue// "DefaultValue"
0x33727  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3372c  ldarg.3
0x3372d  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DefaultValue()
0x33732  ldc.i4.0
0x33733  ldc.i4.0
0x33734  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1_Object(string n, string ns, object o, bool isNullable, bool needType)
0x33739  ldarg.0
0x3373a  ldstr    aValidforcreate// "ValidForCreate"
0x3373f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33744  ldarg.3
0x33745  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForCreate()
0x3374a  ldc.i4.0
0x3374b  ldc.i4.0
0x3374c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x33751  ldarg.0
0x33752  ldstr    aValidforread// "ValidForRead"
0x33757  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3375c  ldarg.3
0x3375d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForRead()
0x33762  ldc.i4.0
0x33763  ldc.i4.0
0x33764  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x33769  ldarg.0
0x3376a  ldstr    aValidforupdate// "ValidForUpdate"
0x3376f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33774  ldarg.3
0x33775  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_ValidForUpdate()
0x3377a  ldc.i4.0
0x3377b  ldc.i4.0
0x3377c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write11_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x33781  ldarg.0
0x33782  ldstr    aDisplaymask// "DisplayMask"
0x33787  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3378c  ldarg.3
0x3378d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_DisplayMask()
0x33792  ldc.i4.0
0x33793  ldc.i4.0
0x33794  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write19_CrmDisplayMasks(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmDisplayMasks o, bool isNullable, bool needType)
0x33799  ldarg.0
0x3379a  ldstr    aAggregateof// "AggregateOf"
0x3379f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x337a4  ldarg.3
0x337a5  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AggregateOf()
0x337aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x337af  ldarg.0
0x337b0  ldstr    aAttributeof// "AttributeOf"
0x337b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x337ba  ldarg.3
0x337bb  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_AttributeOf()
0x337c0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x337c5  ldarg.0
0x337c6  ldstr    aYomiof// "YomiOf"
0x337cb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x337d0  ldarg.3
0x337d1  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_YomiOf()
0x337d6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x337db  ldarg.0
0x337dc  ldstr    aCalculationof// "CalculationOf"
0x337e1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x337e6  ldarg.3
0x337e7  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata::get_CalculationOf()
0x337ec  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x337f1  ldarg.3
0x337f2  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.Option[] [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.PicklistAttributeMetadata::get_Options()
0x337f7  stloc.1
0x337f8  ldloc.1
0x337f9  brfalse.s loc_33836
0x337fb  ldarg.0
0x337fc  ldstr    aOptions// "Options"
0x33801  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x33806  ldnull
0x33807  ldc.i4.0
0x33808  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3380d  ldc.i4.0
0x3380e  stloc.2
0x3380f  br.s     loc_3382A
0x33811  ldarg.0
0x33812  ldstr    aOption// "Option"
0x33817  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3381c  ldloc.1
0x3381d  ldloc.2
0x3381e  ldelem.ref
0x3381f  ldc.i4.0
0x33820  ldc.i4.0
0x33821  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write29_Option(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.Option o, bool isNullable, bool needType)
0x33826  ldloc.2
0x33827  ldc.i4.1
0x33828  add
0x33829  stloc.2
0x3382a  ldloc.2
0x3382b  ldloc.1
0x3382c  ldlen
0x3382d  conv.i4
0x3382e  blt.s    loc_33811
0x33830  ldarg.0
0x33831  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x33836  ldarg.0
0x33837  ldarg.3
0x33838  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x3383d  ret
```
