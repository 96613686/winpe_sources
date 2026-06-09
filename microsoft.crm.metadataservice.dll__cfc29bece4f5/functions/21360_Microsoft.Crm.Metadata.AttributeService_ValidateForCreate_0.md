# Microsoft.Crm.Metadata.AttributeService::ValidateForCreate_0

- ea: `0x21360`
- end: `0x216a4`
- name: `Microsoft.Crm.Metadata.AttributeService::ValidateForCreate_0`
- size: `836`
- prototype: ``
- caller_count: `2`
- callee_count: `27`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c100`
- `0x21220`

## callees

- `0x18470`
- `0x18490`
- `0x184a0`
- `0x184d0`
- `0x18530`
- `0x18660`
- `0x18760`
- `0x187a0`
- `0x187b0`
- `0x21250`
- `0x21360`
- `0x216b0`
- `0x219b0`
- `0x21a00`
- `0x21ac0`
- `0x21d50`
- `0x22460`
- `0x22580`
- `0x22880`
- `0x229b0`
- `0x22b00`
- `0x233e0`
- `0x456b0`
- `0x49cc0`
- `0x58380`
- `0x58430`
- `0x58540`

## string_xrefs

- `0x21392`: `Cannot create an attribute without specifying an entity id`
- `0x21524`: `rowguid is a reserved name. Cannot create attribute whose name is rowguid`
- `0x2166a`: `Cannot create custom attribute '{0}' of type '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x21360  ldstr    aAttribute// "Attribute"
0x21365  ldarg.0
0x21366  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x2136b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x21370  ldstr    aAttributeid// "attributeid"
0x21375  ldarg.1
0x21376  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x2137b  call     void Microsoft.Crm.Metadata.MetadataValidator::ValidateMetadataIdIsSetAndUnique(string metadataEntityName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity metadataBusinessEntity, string metadataIdColumnName, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x21380  ldarg.0
0x21381  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_EntityId()
0x21386  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2138b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x21390  brfalse.s loc_2139D
0x21392  ldstr    aCannotCreateAn// "Cannot create an attribute without spec"...
0x21397  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x2139c  throw
0x2139d  ldarg.1
0x2139e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x213a3  ldarg.0
0x213a4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_EntityId()
0x213a9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(valuetype [mscorlib]System.Guid)
0x213ae  stloc.0
0x213af  ldarg.0
0x213b0  callvirt instance bool Microsoft.Crm.Metadata.AttributeInfo::get_IsRollupField()
0x213b5  brfalse.s loc_213DE
0x213b7  ldloc.0
0x213b8  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x213bd  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.RollupSharedUtility::IsEntityValidForRollups(int32)
0x213c2  brtrue.s loc_213DE
0x213c4  ldc.i4   0x80044813
0x213c9  ldc.i4.1
0x213ca  newarr   [mscorlib]System.Object
0x213cf  dup
0x213d0  ldc.i4.0
0x213d1  ldloc.0
0x213d2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x213d7  stelem.ref
0x213d8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x213dd  throw
0x213de  ldnull
0x213df  stloc.1
0x213e0  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x213e5  ldarg.0
0x213e6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_EntityId()
0x213eb  ldstr    aEntity_0// "Entity"
0x213f0  ldarg.1
0x213f1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x213f6  ldloca.s 1
0x213f8  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::TryRetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity&)
0x213fd  pop
0x213fe  ldloc.1
0x213ff  ldarg.0
0x21400  call     void Microsoft.Crm.Metadata.AttributeService::ValidateAttributeTypesForVirtualEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity metadataBusinessEntity, class Microsoft.Crm.Metadata.AttributeInfo attributeInfo)
0x21405  ldarg.0
0x21406  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x2140b  ldstr    aMultiselectpic// "multiselectpicklist"
0x21410  call     bool [mscorlib]System.String::op_Equality(string, string)
0x21415  brfalse.s loc_21438
0x21417  ldarg.0
0x21418  callvirt instance bool Microsoft.Crm.Metadata.AttributeInfo::get_IsRollupField()
0x2141d  brtrue.s loc_21427
0x2141f  ldarg.0
0x21420  callvirt instance bool Microsoft.Crm.Metadata.AttributeInfo::get_IsCalculatedField()
0x21425  brfalse.s loc_21438
0x21427  ldc.i4   0x80050221
0x2142c  ldc.i4.0
0x2142d  newarr   [mscorlib]System.Object
0x21432  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x21437  throw
0x21438  ldarg.0
0x21439  isinst   Microsoft.Crm.Metadata.ImageAttributeInfo
0x2143e  brfalse.s loc_214AA
0x21440  ldarg.0
0x21441  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_EntityId()
0x21446  ldarg.1
0x21447  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x2144c  ldarg.s  4
0x2144e  call     bool Microsoft.Crm.Metadata.AttributeService::IsCustomEntity(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x21453  brtrue.s loc_21466
0x21455  ldc.i4   0x80048531
0x2145a  ldc.i4.0
0x2145b  newarr   [mscorlib]System.Object
0x21460  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x21465  throw
0x21466  ldarg.0
0x21467  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x2146c  ldsfld   string Microsoft.Crm.Metadata.ImageAttributeInfo::SchemaName
0x21471  ldc.i4.5
0x21472  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x21477  brfalse.s loc_2149C
0x21479  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2147e  ldstr    aACustomImageAt// "A custom image attribute must be named "...
0x21483  ldc.i4.1
0x21484  newarr   [mscorlib]System.Object
0x21489  dup
0x2148a  ldc.i4.0
0x2148b  ldsfld   string Microsoft.Crm.Metadata.ImageAttributeInfo::SchemaName
0x21490  stelem.ref
0x21491  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x21496  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2149b  throw
0x2149c  ldarg.0
0x2149d  ldsfld   string Microsoft.Crm.Metadata.ImageAttributeInfo::SchemaName
0x214a2  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::set_Name(string value)
0x214a7  ldc.i4.0
0x214a8  starg.s  3
0x214aa  ldarg.0
0x214ab  isinst   Microsoft.Crm.Metadata.DateTimeAttributeInfo
0x214b0  stloc.2
0x214b1  ldloc.2
0x214b2  brfalse.s loc_214BA
0x214b4  ldloc.2
0x214b5  call     void Microsoft.Crm.Metadata.AttributeService::ValidateDateTimeAttributeForCreate(class Microsoft.Crm.Metadata.DateTimeAttributeInfo attributeInfo)
0x214ba  ldarg.2
0x214bb  brtrue.s loc_214CB
0x214bd  ldarg.0
0x214be  ldarg.1
0x214bf  call     void Microsoft.Crm.Metadata.AttributeService::ValidateAttributeEntityForCreate(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x214c4  ldarg.0
0x214c5  ldarg.1
0x214c6  call     void Microsoft.Crm.Metadata.AttributeService::ValidatePrimaryNameUniqueness(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x214cb  ldarg.0
0x214cc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.AttributeInfo::get_DisplayNames()
0x214d1  ldarg.0
0x214d2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x214d7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x214dc  ldstr    aDisplayname// "DisplayName"
0x214e1  ldc.i4.1
0x214e2  ldstr    aAttributeDispl// "Attribute Display Name"
0x214e7  ldarg.1
0x214e8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x214ed  ldarg.s  4
0x214ef  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x214f4  ldc.i4.0
0x214f5  ceq
0x214f7  call     void Microsoft.Crm.Metadata.LocalizedLabelHelper::ValidateLabelCollectionContents(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string parameterName, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, [opt] bool throwIfCollectionIsNullOrEmpty)
0x214fc  ldarg.0
0x214fd  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x21502  newobj   instance void Microsoft.Crm.Metadata.SchemaNameValidator::.ctor(string schemaName)
0x21507  stloc.3
0x21508  ldarg.3
0x21509  brfalse.s loc_21534
0x2150b  ldloc.3
0x2150c  callvirt instance void Microsoft.Crm.Metadata.SchemaNameValidator::ValidateSchemaName()
0x21511  ldarg.0
0x21512  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x21517  ldstr    aRowguid// "rowguid"
0x2151c  ldc.i4.5
0x2151d  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x21522  brtrue.s loc_21534
0x21524  ldstr    aRowguidIsARese// "rowguid is a reserved name. Cannot crea"...
0x21529  ldc.i4   0x80047001
0x2152e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x21533  throw
0x21534  ldarg.0
0x21535  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2153a  ldtoken  Microsoft.Crm.Metadata.StringAttributeInfo
0x2153f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21544  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x21549  brfalse.s loc_21554
0x2154b  ldarg.0
0x2154c  ldarg.1
0x2154d  call     void Microsoft.Crm.Metadata.AttributeService::ValidateYomiMappingForCreate(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x21552  br.s     loc_21576
0x21554  ldarg.0
0x21555  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x2155a  ldstr    aYomiof// "yomiof"
0x2155f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x21564  brfalse.s loc_21576
0x21566  ldstr    aPhoneticGuideO// "phonetic guide of value can only be spe"...
0x2156b  ldc.i4   0x80040203
0x21570  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x21575  throw
0x21576  ldloc.3
0x21577  callvirt instance void Microsoft.Crm.Metadata.SchemaNameValidator::ValidateKeywordConflict()
0x2157c  ldarg.3
0x2157d  brfalse.s loc_21585
0x2157f  ldarg.0
0x21580  call     void Microsoft.Crm.Metadata.AttributeService::ValidateAttributeRequiredLevelForCreate(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo)
0x21585  ldarg.0
0x21586  isinst   Microsoft.Crm.Metadata.EnumAttributeInfo
0x2158b  stloc.s  4
0x2158d  ldloc.s  4
0x2158f  brfalse.s loc_215B0
0x21591  ldloc.s  4
0x21593  ldarg.1
0x21594  call     void Microsoft.Crm.Metadata.AttributeService::ValidateOptionSetForCreate(class Microsoft.Crm.Metadata.EnumAttributeInfo enumInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x21599  ldloc.s  4
0x2159b  isinst   Microsoft.Crm.Metadata.PicklistAttributeInfo
0x215a0  stloc.s  5
0x215a2  ldloc.s  5
0x215a4  brfalse.s loc_215DD
0x215a6  ldloc.s  5
0x215a8  ldarg.1
0x215a9  call     void Microsoft.Crm.Metadata.AttributeService::ValidatePicklistDefaultValueForCreate(class Microsoft.Crm.Metadata.PicklistAttributeInfo picklistInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x215ae  br.s     loc_215DD
0x215b0  ldarg.0
0x215b1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x215b6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_ParentEnumAttributeId()
0x215bb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x215c0  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x215c5  brfalse.s loc_215DD
0x215c7  ldarg.0
0x215c8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x215cd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x215d2  ldstr    aParentenumattr// "parentenumattributeid"
0x215d7  ldnull
0x215d8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x215dd  ldarg.0
0x215de  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.AttributeInfo::get_LinkedAttributeId()
0x215e3  stloc.s  6
0x215e5  ldloca.s 6
0x215e7  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x215ec  brfalse.s loc_21633
0x215ee  ldarg.0
0x215ef  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.AttributeInfo::get_LinkedAttributeId()
0x215f4  stloc.s  6
0x215f6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x215fb  stloc.s  7
0x215fd  ldloca.s 6
0x215ff  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x21604  brtrue.s loc_21609
0x21606  ldc.i4.1
0x21607  br.s     loc_21623
0x21609  ldloca.s 6
0x2160b  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x21610  brtrue.s loc_21615
0x21612  ldc.i4.0
0x21613  br.s     loc_21623
0x21615  ldloca.s 6
0x21617  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x2161c  ldloc.s  7
0x2161e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x21623  brfalse.s loc_21633
0x21625  ldarg.0
0x21626  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_EntityId()
0x2162b  ldarg.0
0x2162c  ldc.i4.1
0x2162d  ldarg.1
0x2162e  call     void Microsoft.Crm.Metadata.AttributeService::ValidateLinkedAttributeForCreateUpdate(valuetype [mscorlib]System.Guid entityId, class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, bool isLinkedAttributeChanged, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x21633  ldarg.0
0x21634  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x21639  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsCustomField()
0x2163e  brfalse.s loc_216A3
0x21640  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesById()
0x21645  ldarg.0
0x21646  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x2164b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeTypeId()
0x21650  box      [mscorlib]System.Guid
0x21655  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x2165a  stloc.s  8
0x2165c  ldloc.s  8
0x2165e  call     bool Microsoft.Crm.Metadata.AttributeService::IsAttributeTypeValidForUserToCreate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo attributeTypeInfo)
0x21663  brtrue.s loc_2169D
0x21665  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2166a  ldstr    aCannotCreateCu// "Cannot create custom attribute '{0}' of"...
0x2166f  ldc.i4.2
0x21670  newarr   [mscorlib]System.Object
0x21675  dup
0x21676  ldc.i4.0
0x21677  ldarg.0
0x21678  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x2167d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_Name()
0x21682  stelem.ref
0x21683  dup
0x21684  ldc.i4.1
0x21685  ldloc.s  8
0x21687  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x2168c  stelem.ref
0x2168d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x21692  ldc.i4   0x80040203
0x21697  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2169c  throw
0x2169d  ldarg.0
0x2169e  call     void Microsoft.Crm.Metadata.AttributeService::ValidateAutoNumberFormatAttribute(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo)
0x216a3  ret
```
