# Microsoft.Crm.Metadata.AttributeService::AddAttributeDescriptionForUpdate

- ea: `0x1f780`
- end: `0x1fe75`
- name: `Microsoft.Crm.Metadata.AttributeService::AddAttributeDescriptionForUpdate`
- size: `1781`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1f670`
- `0x1f700`

## callees

- `0x18530`
- `0x18760`
- `0x1c6a0`
- `0x1f780`
- `0x40f10`
- `0x4ab30`
- `0x4ab50`
- `0x4ab70`
- `0x4b2d0`
- `0x4c2b0`
- `0x4c6c0`

## string_xrefs

- `0x1fe1b`: `{0} is not a valid type for linked attribute`

## pseudocode

```c

```

## disassembly

```asm
0x1f780  ldarg.3
0x1f781  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f786  stloc.0
0x1f787  ldloc.0
0x1f788  ldarg.0
0x1f789  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_AttributeId(valuetype [mscorlib]System.Guid)
0x1f78e  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x1f793  ldarg.0
0x1f794  ldstr    aAttribute// "Attribute"
0x1f799  ldc.i4.1
0x1f79a  newarr   [mscorlib]System.String
0x1f79f  dup
0x1f7a0  ldc.i4.0
0x1f7a1  ldstr    aDisplaymask// "displaymask"
0x1f7a6  stelem.ref
0x1f7a7  ldarg.3
0x1f7a8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1f7ad  stloc.1
0x1f7ae  ldloc.1
0x1f7af  ldstr    aDisplaymask// "displaymask"
0x1f7b4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1f7b9  brfalse.s loc_1F7D1
0x1f7bb  ldloc.0
0x1f7bc  ldloc.1
0x1f7bd  ldstr    aDisplaymask// "displaymask"
0x1f7c2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1f7c7  unbox.any [mscorlib]System.Int32
0x1f7cc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_DisplayMask(int32)
0x1f7d1  ldloc.0
0x1f7d2  ldarg.1
0x1f7d3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1f7d8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsSecured()
0x1f7dd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsSecured(bool)
0x1f7e2  ldloc.0
0x1f7e3  ldarg.1
0x1f7e4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1f7e9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_RequiredLevel()
0x1f7ee  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_RequiredLevel(string)
0x1f7f3  ldloc.0
0x1f7f4  ldarg.1
0x1f7f5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1f7fa  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IMEMode()
0x1f7ff  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IMEMode(string)
0x1f804  ldarg.1
0x1f805  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x1f80a  ldstr    aNvarchar// "nvarchar"
0x1f80f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1f814  brtrue.s loc_1F82B
0x1f816  ldarg.1
0x1f817  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x1f81c  ldstr    aNtext// "ntext"
0x1f821  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1f826  brfalse  loc_1F8C9
0x1f82b  ldarg.1
0x1f82c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1f831  ldstr    aMaxlength// "maxlength"
0x1f836  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x1f83b  brfalse.s loc_1F894
0x1f83d  ldloc.0
0x1f83e  ldarg.1
0x1f83f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1f844  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_MaxLength()
0x1f849  box      [mscorlib]System.Int32
0x1f84e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f853  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x1f858  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_MaxLength(int32)
0x1f85d  ldarg.1
0x1f85e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1f863  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_MaxLength()
0x1f868  ldc.i4   0x3FFFFFFF
0x1f86d  bge.s    loc_1F894
0x1f86f  ldarg.1
0x1f870  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x1f875  ldstr    aNtext// "ntext"
0x1f87a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1f87f  brfalse.s loc_1F894
0x1f881  ldloc.0
0x1f882  ldarg.1
0x1f883  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1f888  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_MaxLength()
0x1f88d  ldc.i4.2
0x1f88e  mul
0x1f88f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_Length(int32)
0x1f894  ldarg.1
0x1f895  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1f89a  ldstr    aAutonumberform// "autonumberformat"
0x1f89f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x1f8a4  brfalse  loc_1FE3F
0x1f8a9  ldloc.0
0x1f8aa  ldarg.1
0x1f8ab  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1f8b0  ldstr    aAutonumberform// "autonumberformat"
0x1f8b5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x1f8ba  castclass [mscorlib]System.String
0x1f8bf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_AutoNumberFormat(string)
0x1f8c4  br       loc_1FE3F
0x1f8c9  ldarg.1
0x1f8ca  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x1f8cf  ldstr    aFloat// "float"
0x1f8d4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1f8d9  brtrue.s loc_1F914
0x1f8db  ldarg.1
0x1f8dc  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x1f8e1  ldstr    aDecimal// "decimal"
0x1f8e6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1f8eb  brtrue.s loc_1F914
0x1f8ed  ldarg.1
0x1f8ee  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x1f8f3  ldstr    aInt// "int"
0x1f8f8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1f8fd  brtrue.s loc_1F914
0x1f8ff  ldarg.1
0x1f900  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x1f905  ldstr    aMoney// "money"
0x1f90a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1f90f  brfalse  loc_1F9D2
0x1f914  ldarg.1
0x1f915  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1f91a  ldstr    aMaxvalue// "maxvalue"
0x1f91f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x1f924  brfalse.s loc_1F946
0x1f926  ldloc.0
0x1f927  ldarg.1
0x1f928  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1f92d  callvirt instance float64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_MaxValue()
0x1f932  box      [mscorlib]System.Double
0x1f937  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f93c  call     float64 [mscorlib]System.Convert::ToDouble(object, class [mscorlib]System.IFormatProvider)
0x1f941  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_MaxValue(float64)
0x1f946  ldarg.1
0x1f947  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1f94c  ldstr    aMinvalue// "minvalue"
0x1f951  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x1f956  brfalse.s loc_1F978
0x1f958  ldloc.0
0x1f959  ldarg.1
0x1f95a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1f95f  callvirt instance float64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_MinValue()
0x1f964  box      [mscorlib]System.Double
0x1f969  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f96e  call     float64 [mscorlib]System.Convert::ToDouble(object, class [mscorlib]System.IFormatProvider)
0x1f973  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_MinValue(float64)
0x1f978  ldarg.1
0x1f979  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x1f97e  ldstr    aInt// "int"
0x1f983  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1f988  brfalse  loc_1FE3F
0x1f98d  ldloc.0
0x1f98e  ldarg.1
0x1f98f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1f994  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_Precision()
0x1f999  box      [mscorlib]System.Int32
0x1f99e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f9a3  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x1f9a8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_Precision(int32)
0x1f9ad  ldloc.0
0x1f9ae  ldarg.1
0x1f9af  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1f9b4  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_PrecisionSource()
0x1f9b9  box      [mscorlib]System.Int32
0x1f9be  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f9c3  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x1f9c8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_PrecisionSource(int32)
0x1f9cd  br       loc_1FE3F
0x1f9d2  ldarg.1
0x1f9d3  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x1f9d8  ldstr    aDatetime// "datetime"
0x1f9dd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1f9e2  brfalse.s loc_1FA0B
0x1f9e4  ldloc.0
0x1f9e5  ldarg.1
0x1f9e6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1f9eb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_Format()
0x1f9f0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_Format(string)
0x1f9f5  ldloc.0
0x1f9f6  ldarg.1
0x1f9f7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1f9fc  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_Behavior()
0x1fa01  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_Behavior(int32)
0x1fa06  br       loc_1FE3F
0x1fa0b  ldarg.1
0x1fa0c  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x1fa11  ldstr    aBit// "bit"
0x1fa16  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1fa1b  brtrue.s loc_1FA44
0x1fa1d  ldarg.1
0x1fa1e  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x1fa23  ldstr    aPicklist// "picklist"
0x1fa28  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1fa2d  brtrue.s loc_1FA44
0x1fa2f  ldarg.1
0x1fa30  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x1fa35  ldstr    aMultiselectpic// "multiselectpicklist"
0x1fa3a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1fa3f  brfalse  loc_1FDF2
0x1fa44  ldloc.0
0x1fa45  ldarg.1
0x1fa46  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1fa4b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AppDefaultValue()
0x1fa50  box      [mscorlib]System.Int32
0x1fa55  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1fa5a  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x1fa5f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_AppDefaultValue(int32)
0x1fa64  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x1fa69  ldarg.0
0x1fa6a  ldstr    aAttribute// "Attribute"
0x1fa6f  ldc.i4.1
0x1fa70  newarr   [mscorlib]System.String
0x1fa75  dup
0x1fa76  ldc.i4.0
0x1fa77  ldstr    aOptionsetid// "optionsetid"
0x1fa7c  stelem.ref
0x1fa7d  ldarg.3
0x1fa7e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1fa83  stloc.3
0x1fa84  ldloc.3
0x1fa85  ldstr    aOptionsetid// "optionsetid"
0x1fa8a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1fa8f  brfalse  loc_1FE3F
0x1fa94  ldloc.3
0x1fa95  ldstr    aOptionsetid// "optionsetid"
0x1fa9a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1fa9f  unbox.any [mscorlib]System.Guid
0x1faa4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1faa9  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1faae  brfalse  loc_1FE3F
0x1fab3  ldloc.3
0x1fab4  ldstr    aOptionsetid// "optionsetid"
0x1fab9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1fabe  unbox.any [mscorlib]System.Guid
0x1fac3  stloc.s  4
0x1fac5  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x1faca  ldloc.s  4
0x1facc  ldstr    aOptionset_0// "OptionSet"
0x1fad1  ldc.i4.2
0x1fad2  newarr   [mscorlib]System.String
0x1fad7  dup
0x1fad8  ldc.i4.0
0x1fad9  ldstr    aName// "name"
0x1fade  stelem.ref
0x1fadf  dup
0x1fae0  ldc.i4.1
0x1fae1  ldstr    aIsglobal// "isglobal"
0x1fae6  stelem.ref
0x1fae7  ldarg.3
0x1fae8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1faed  stloc.s  5
0x1faef  ldloc.s  5
0x1faf1  ldstr    aIsglobal// "isglobal"
0x1faf6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1fafb  unbox.any [mscorlib]System.Boolean
0x1fb00  brtrue   loc_1FE3F
0x1fb05  ldarg.1
0x1fb06  isinst   Microsoft.Crm.Metadata.EnumAttributeInfo
0x1fb0b  stloc.s  6
0x1fb0d  ldstr    aDescriptions// "Descriptions"
0x1fb12  ldstr    aDescription// "Description"
0x1fb17  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor(string, string)
0x1fb1c  stloc.s  7
0x1fb1e  ldstr    aDisplaynames// "displaynames"
0x1fb23  ldstr    aDisplayname_0// "displayname"
0x1fb28  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor(string, string)
0x1fb2d  stloc.s  8
0x1fb2f  ldloc.s  6
0x1fb31  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x1fb36  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.OptionSetInfo::get_DisplayNames()
0x1fb3b  brfalse.s loc_1FB9B
0x1fb3d  ldloc.s  6
0x1fb3f  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x1fb44  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.OptionSetInfo::get_DisplayNames()
0x1fb49  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::GetEnumerator()
0x1fb4e  stloc.s  9
0x1fb50  br.s     loc_1FB7B
0x1fb52  ldloc.s  9
0x1fb54  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1fb59  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label
0x1fb5e  stloc.s  0xA
0x1fb60  ldloc.s  8
0x1fb62  ldloc.s  0xA
0x1fb64  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_LanguageCode()
0x1fb69  ldloc.s  0xA
0x1fb6b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x1fb70  ldarg.3
0x1fb71  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1fb76  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x1fb7b  ldloc.s  9
0x1fb7d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1fb82  brtrue.s loc_1FB52
0x1fb84  leave.s  loc_1FB9B
0x1fb86  ldloc.s  9
0x1fb88  isinst   [mscorlib]System.IDisposable
0x1fb8d  stloc.s  0xB
0x1fb8f  ldloc.s  0xB
0x1fb91  brfalse.s loc_1FB9A
0x1fb93  ldloc.s  0xB
0x1fb95  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1fb9a  endfinally
0x1fb9b  ldloc.s  6
0x1fb9d  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x1fba2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.OptionSetInfo::get_Descriptions()
  ... truncated ...
```
