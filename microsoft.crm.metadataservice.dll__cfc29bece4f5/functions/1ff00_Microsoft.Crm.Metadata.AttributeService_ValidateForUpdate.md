# Microsoft.Crm.Metadata.AttributeService::ValidateForUpdate

- ea: `0x1ff00`
- end: `0x202c4`
- name: `Microsoft.Crm.Metadata.AttributeService::ValidateForUpdate`
- size: `964`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1e420`
- `0x757d0`

## callees

- `0x18470`
- `0x18490`
- `0x184a0`
- `0x184d0`
- `0x18550`
- `0x18660`
- `0x18760`
- `0x1be80`
- `0x1ff00`
- `0x202d0`
- `0x20320`
- `0x20350`
- `0x20580`
- `0x20600`
- `0x20740`
- `0x20870`
- `0x21250`
- `0x216b0`
- `0x21ac0`
- `0x21d50`
- `0x22a10`
- `0x22f70`
- `0x23330`
- `0x23af0`
- `0x456b0`

## string_xrefs

- `0x20226`: `linkedattributeid`
- `0x20233`: `linkedattributeid`
- `0x1ff41`: `LookupNameMatchesDuringImport`

## pseudocode

```c

```

## disassembly

```asm
0x1ff00  ldarg.0
0x1ff01  ldarg.1
0x1ff02  ldarg.3
0x1ff03  call     void Microsoft.Crm.Metadata.AttributeService::ProcessSourceTypeRules(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity existingAttributeData, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1ff08  ldarg.0
0x1ff09  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.AttributeInfo::get_DisplayNames()
0x1ff0e  ldarg.0
0x1ff0f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1ff14  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x1ff19  ldstr    aDisplayname// "DisplayName"
0x1ff1e  ldc.i4.1
0x1ff1f  ldstr    aAttributeDispl// "Attribute Display Name"
0x1ff24  ldarg.3
0x1ff25  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1ff2a  ldc.i4.0
0x1ff2b  call     void Microsoft.Crm.Metadata.LocalizedLabelHelper::ValidateLabelCollectionContents(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string parameterName, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, [opt] bool throwIfCollectionIsNullOrEmpty)
0x1ff30  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x1ff35  ldarg.3
0x1ff36  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1ff3b  ldarg.3
0x1ff3c  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x1ff41  ldstr    aLookupnamematc// "LookupNameMatchesDuringImport"
0x1ff46  ldc.i4.0
0x1ff47  box      [mscorlib]System.Boolean
0x1ff4c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string, object)
0x1ff51  unbox.any [mscorlib]System.Boolean
0x1ff56  stloc.0
0x1ff57  ldarg.2
0x1ff58  brtrue.s loc_1FFCE
0x1ff5a  ldarg.1
0x1ff5b  ldstr    aPhysicalname// "physicalname"
0x1ff60  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1ff65  castclass [mscorlib]System.String
0x1ff6a  stloc.s  7
0x1ff6c  ldc.i4.0
0x1ff6d  stloc.s  8
0x1ff6f  ldloc.0
0x1ff70  brfalse.s loc_1FF87
0x1ff72  ldarg.0
0x1ff73  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x1ff78  ldloc.s  7
0x1ff7a  ldc.i4.5
0x1ff7b  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1ff80  ldc.i4.0
0x1ff81  cgt.un
0x1ff83  stloc.s  8
0x1ff85  br.s     loc_1FF96
0x1ff87  ldarg.0
0x1ff88  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x1ff8d  ldloc.s  7
0x1ff8f  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1ff94  stloc.s  8
0x1ff96  ldarg.0
0x1ff97  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x1ff9c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ffa1  ldc.i4.0
0x1ffa2  ceq
0x1ffa4  ldloc.s  8
0x1ffa6  and
0x1ffa7  brfalse.s loc_1FFC6
0x1ffa9  ldstr    aAttributeinfoN// "AttributeInfo.Name({0}) != AttributeMet"...
0x1ffae  ldarg.0
0x1ffaf  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x1ffb4  ldloc.s  7
0x1ffb6  call     string [mscorlib]System.String::Format(string, object, object)
0x1ffbb  ldc.i4   0x80041A06
0x1ffc0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1ffc5  throw
0x1ffc6  ldarg.0
0x1ffc7  ldloc.s  7
0x1ffc9  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::set_Name(string value)
0x1ffce  ldarg.1
0x1ffcf  ldarg.3
0x1ffd0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Metadata.AttributeService::GetRollupFieldForAccessoryAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1ffd5  stloc.1
0x1ffd6  ldarg.0
0x1ffd7  ldloc.1
0x1ffd8  call     void Microsoft.Crm.Metadata.AttributeService::ValidateRollupDependentField(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata parentRollupField)
0x1ffdd  ldarg.0
0x1ffde  ldarg.3
0x1ffdf  call     void Microsoft.Crm.Metadata.AttributeService::ValidatePrimaryNameUniqueness(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1ffe4  ldarg.0
0x1ffe5  ldarg.1
0x1ffe6  call     void Microsoft.Crm.Metadata.AttributeService::ValidateTypeMatch(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity existingAttributeData)
0x1ffeb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesById()
0x1fff0  ldarg.1
0x1fff1  ldstr    aAttributetypei// "attributetypeid"
0x1fff6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1fffb  unbox.any [mscorlib]System.Guid
0x20000  box      [mscorlib]System.Guid
0x20005  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x2000a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x2000f  stloc.2
0x20010  ldarg.0
0x20011  ldloc.2
0x20012  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::set_TypeName(string value)
0x20017  ldarg.0
0x20018  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2001d  ldtoken  Microsoft.Crm.Metadata.StringAttributeInfo
0x20022  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20027  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2002c  brfalse.s loc_2003A
0x2002e  ldarg.2
0x2002f  brtrue.s loc_2003A
0x20031  ldarg.0
0x20032  ldarg.3
0x20033  call     void Microsoft.Crm.Metadata.AttributeService::ValidateYomiMappingForUpdate(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x20038  br.s     loc_2005C
0x2003a  ldarg.0
0x2003b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x20040  ldstr    aYomiof// "yomiof"
0x20045  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x2004a  brfalse.s loc_2005C
0x2004c  ldstr    aPhoneticGuideO// "phonetic guide of value can only be spe"...
0x20051  ldc.i4   0x80040203
0x20056  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2005b  throw
0x2005c  ldarg.0
0x2005d  ldarg.1
0x2005e  ldarg.3
0x2005f  call     void Microsoft.Crm.Metadata.AttributeService::ValidateMaxLengthForUpdate(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity existingAttributeData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x20064  ldarg.0
0x20065  ldarg.1
0x20066  ldarg.3
0x20067  call     void Microsoft.Crm.Metadata.AttributeService::ValidateIsSecuredBit(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity existingAttributeData, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2006c  ldarg.0
0x2006d  ldarg.1
0x2006e  ldarg.3
0x2006f  call     void Microsoft.Crm.Metadata.AttributeService::ValidateAttributeRequiredLevelForUpdate(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity existingAttributeData, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x20074  ldarg.0
0x20075  isinst   Microsoft.Crm.Metadata.DateTimeAttributeInfo
0x2007a  stloc.3
0x2007b  ldloc.3
0x2007c  brfalse.s loc_20092
0x2007e  ldloc.3
0x2007f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x20084  ldarg.1
0x20085  ldarg.3
0x20086  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x2008b  ldarg.s  4
0x2008d  call     void Microsoft.Crm.Metadata.AttributeService::ValidateDateTimeAttributeForUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity existingAttributeData, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x20092  ldarg.0
0x20093  isinst   Microsoft.Crm.Metadata.ImageAttributeInfo
0x20098  stloc.s  4
0x2009a  ldloc.s  4
0x2009c  brfalse.s loc_200A5
0x2009e  ldloc.s  4
0x200a0  call     void Microsoft.Crm.Metadata.AttributeService::ValidateImageFieldForUpdate(class Microsoft.Crm.Metadata.ImageAttributeInfo imageInfo)
0x200a5  ldarg.0
0x200a6  isinst   Microsoft.Crm.Metadata.EnumAttributeInfo
0x200ab  stloc.s  5
0x200ad  ldloc.s  5
0x200af  brfalse  loc_201AD
0x200b4  ldarg.2
0x200b5  brtrue.s loc_200DE
0x200b7  ldloc.s  5
0x200b9  ldarg.1
0x200ba  ldarg.3
0x200bb  call     void Microsoft.Crm.Metadata.AttributeService::ValidateOptionSetForUpdate(class Microsoft.Crm.Metadata.EnumAttributeInfo enumInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity existingAttributeData, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x200c0  ldloc.s  5
0x200c2  isinst   Microsoft.Crm.Metadata.PicklistAttributeInfo
0x200c7  stloc.s  0xB
0x200c9  ldloc.s  0xB
0x200cb  brfalse.s loc_200DE
0x200cd  ldarg.s  4
0x200cf  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x200d4  brtrue.s loc_200DE
0x200d6  ldloc.s  0xB
0x200d8  ldarg.3
0x200d9  call     void Microsoft.Crm.Metadata.AttributeService::ValidatePicklistDefaultValueForUpdate(class Microsoft.Crm.Metadata.PicklistAttributeInfo picklistInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x200de  ldloc.s  5
0x200e0  isinst   Microsoft.Crm.Metadata.StateAttributeInfo
0x200e5  stloc.s  9
0x200e7  ldloc.s  9
0x200e9  brfalse.s loc_20144
0x200eb  ldloc.s  9
0x200ed  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x200f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x200f7  ldstr    aAppdefaultvalu// "appdefaultvalue"
0x200fc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x20101  brtrue.s loc_20144
0x20103  ldarg.1
0x20104  ldstr    aAppdefaultvalu// "appdefaultvalue"
0x20109  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x2010e  brtrue.s loc_20133
0x20110  ldarg.1
0x20111  ldstr    aAppdefaultvalu// "appdefaultvalue"
0x20116  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2011b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20120  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x20125  ldloc.s  9
0x20127  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x2012c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AppDefaultValue()
0x20131  beq.s    loc_20144
0x20133  ldc.i4   0x80044343
0x20138  ldc.i4.0
0x20139  newarr   [mscorlib]System.Object
0x2013e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x20143  throw
0x20144  ldloc.s  5
0x20146  isinst   Microsoft.Crm.Metadata.StatusAttributeInfo
0x2014b  stloc.s  0xA
0x2014d  ldloc.s  0xA
0x2014f  brfalse  loc_201DA
0x20154  ldloc.s  0xA
0x20156  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x2015b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x20160  ldstr    aAppdefaultvalu// "appdefaultvalue"
0x20165  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x2016a  brtrue.s loc_201DA
0x2016c  ldarg.1
0x2016d  ldstr    aAppdefaultvalu// "appdefaultvalue"
0x20172  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x20177  brtrue.s loc_2019C
0x20179  ldarg.1
0x2017a  ldstr    aAppdefaultvalu// "appdefaultvalue"
0x2017f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x20184  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20189  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x2018e  ldloc.s  0xA
0x20190  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x20195  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AppDefaultValue()
0x2019a  beq.s    loc_201DA
0x2019c  ldc.i4   0x80044344
0x201a1  ldc.i4.0
0x201a2  newarr   [mscorlib]System.Object
0x201a7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x201ac  throw
0x201ad  ldarg.0
0x201ae  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x201b3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_ParentEnumAttributeId()
0x201b8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x201bd  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x201c2  brfalse.s loc_201DA
0x201c4  ldarg.0
0x201c5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x201ca  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x201cf  ldstr    aParentenumattr// "parentenumattributeid"
0x201d4  ldnull
0x201d5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x201da  ldarg.0
0x201db  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.AttributeInfo::get_LinkedAttributeId()
0x201e0  stloc.s  0xC
0x201e2  ldloca.s 0xC
0x201e4  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x201e9  brfalse  loc_20294
0x201ee  ldarg.0
0x201ef  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.AttributeInfo::get_LinkedAttributeId()
0x201f4  stloc.s  0xC
0x201f6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x201fb  stloc.s  0xD
0x201fd  ldloca.s 0xC
0x201ff  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x20204  brtrue.s loc_20209
0x20206  ldc.i4.1
0x20207  br.s     loc_20223
0x20209  ldloca.s 0xC
0x2020b  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x20210  brtrue.s loc_20215
0x20212  ldc.i4.0
0x20213  br.s     loc_20223
0x20215  ldloca.s 0xC
0x20217  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x2021c  ldloc.s  0xD
0x2021e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x20223  brfalse.s loc_20294
0x20225  ldarg.1
0x20226  ldstr    aLinkedattribut// "linkedattributeid"
0x2022b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x20230  brfalse.s loc_20244
0x20232  ldarg.1
0x20233  ldstr    aLinkedattribut// "linkedattributeid"
0x20238  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2023d  unbox.any [mscorlib]System.Guid
0x20242  br.s     loc_20249
0x20244  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x20249  stloc.s  0xE
0x2024b  ldarg.1
0x2024c  ldstr    aEntityid// "entityid"
0x20251  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x20256  unbox.any [mscorlib]System.Guid
0x2025b  ldarg.0
0x2025c  ldarg.0
0x2025d  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.AttributeInfo::get_LinkedAttributeId()
0x20262  stloc.s  0xC
0x20264  ldloc.s  0xE
0x20266  stloc.s  0xD
0x20268  ldloca.s 0xC
0x2026a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x2026f  brtrue.s loc_20274
0x20271  ldc.i4.1
0x20272  br.s     loc_2028E
0x20274  ldloca.s 0xC
0x20276  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x2027b  brtrue.s loc_20280
0x2027d  ldc.i4.0
0x2027e  br.s     loc_2028E
0x20280  ldloca.s 0xC
0x20282  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x20287  ldloc.s  0xD
  ... truncated ...
```
