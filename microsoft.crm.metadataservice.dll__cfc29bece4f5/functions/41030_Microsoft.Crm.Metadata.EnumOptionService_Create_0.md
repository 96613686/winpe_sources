# Microsoft.Crm.Metadata.EnumOptionService::Create_0

- ea: `0x41030`
- end: `0x413da`
- name: `Microsoft.Crm.Metadata.EnumOptionService::Create_0`
- size: `938`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x41010`

## callees

- `0x2bda0`
- `0x41030`
- `0x41400`
- `0x41670`
- `0x416f0`
- `0x42200`
- `0x426c0`
- `0x427d0`
- `0x42a30`
- `0x42ab0`
- `0x49900`
- `0x49910`
- `0x49920`
- `0x4bc30`
- `0x5a810`

## string_xrefs

- `0x4113c`: `prvReadAttribute`
- `0x41103`: `prvReadOptionSet`
- `0x41122`: `prvWriteAttribute`
- `0x41061`: `The EnumDescription of the AttributeEnumValueData passed to Create must contain the optionSet id`
- `0x410e9`: `prvWriteOptionSet`
- `0x4118c`: `cancreateoptionvalue`
- `0x413b6`: `EnumOptionServce.Create caught exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x41030  ldarg.1
0x41031  ldstr    aEnumdata// "enumData"
0x41036  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4103b  ldarg.s  4
0x4103d  ldstr    aContext// "context"
0x41042  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x41047  ldarg.s  4
0x41049  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4104e  pop
0x4104f  ldarg.1
0x41050  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeEnumValueData::get_EnumDescription()
0x41055  ldstr    aOptionsetid// "optionsetid"
0x4105a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x4105f  brfalse.s loc_4106C
0x41061  ldstr    aTheEnumdescrip// "The EnumDescription of the AttributeEnu"...
0x41066  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x4106b  throw
0x4106c  ldarg.1
0x4106d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeEnumValueData::get_EnumDescription()
0x41072  ldstr    aOptionsetid// "optionsetid"
0x41077  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4107c  unbox.any [mscorlib]System.Guid
0x41081  stloc.0
0x41082  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x41087  ldloc.0
0x41088  ldstr    aOptionset_0// "OptionSet"
0x4108d  ldc.i4.7
0x4108e  newarr   [mscorlib]System.String
0x41093  dup
0x41094  ldc.i4.0
0x41095  ldstr    aOptionsettype// "optionsettype"
0x4109a  stelem.ref
0x4109b  dup
0x4109c  ldc.i4.1
0x4109d  ldstr    aIsglobal// "isglobal"
0x410a2  stelem.ref
0x410a3  dup
0x410a4  ldc.i4.2
0x410a5  ldstr    aIsmanaged// "ismanaged"
0x410aa  stelem.ref
0x410ab  dup
0x410ac  ldc.i4.3
0x410ad  ldstr    aIscustomizable// "iscustomizable"
0x410b2  stelem.ref
0x410b3  dup
0x410b4  ldc.i4.4
0x410b5  ldstr    aName// "name"
0x410ba  stelem.ref
0x410bb  dup
0x410bc  ldc.i4.5
0x410bd  ldstr    aOptionsetid// "optionsetid"
0x410c2  stelem.ref
0x410c3  dup
0x410c4  ldc.i4.6
0x410c5  ldstr    aParentoptionse// "parentoptionsetid"
0x410ca  stelem.ref
0x410cb  ldarg.s  4
0x410cd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x410d2  stloc.1
0x410d3  ldloc.1
0x410d4  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x410d9  stloc.2
0x410da  ldloc.2
0x410db  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_IsGlobal()
0x410e0  brfalse.s loc_4111B
0x410e2  ldarg.s  4
0x410e4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x410e9  ldstr    aPrvwriteoption// "prvWriteOptionSet"
0x410ee  ldarg.s  4
0x410f0  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x410f5  ldarg.s  4
0x410f7  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x410fc  ldarg.s  4
0x410fe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x41103  ldstr    aPrvreadoptions// "prvReadOptionSet"
0x41108  ldarg.s  4
0x4110a  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4110f  ldarg.s  4
0x41111  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x41116  br       loc_411A1
0x4111b  ldarg.s  4
0x4111d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x41122  ldstr    aPrvwriteattrib// "prvWriteAttribute"
0x41127  ldarg.s  4
0x41129  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4112e  ldarg.s  4
0x41130  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x41135  ldarg.s  4
0x41137  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x4113c  ldstr    aPrvreadattribu// "prvReadAttribute"
0x41141  ldarg.s  4
0x41143  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x41148  ldarg.s  4
0x4114a  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4114f  ldloc.1
0x41150  ldarg.s  4
0x41152  call     bool Microsoft.Crm.Metadata.EnumOptionService::IsOptionSetCustomizableInternal(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity optionSetData, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x41157  brtrue.s loc_411A1
0x41159  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4115e  ldstr    aInsertionIntoL// "Insertion into local OptionSet({0}, Id="...
0x41163  ldc.i4.2
0x41164  newarr   [mscorlib]System.Object
0x41169  dup
0x4116a  ldc.i4.0
0x4116b  ldloc.2
0x4116c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_Name()
0x41171  stelem.ref
0x41172  dup
0x41173  ldc.i4.1
0x41174  ldloc.2
0x41175  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x4117a  box      [mscorlib]System.Guid
0x4117f  stelem.ref
0x41180  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x41185  ldarg.s  4
0x41187  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4118c  ldstr    aCancreateoptio// "cancreateoptionvalue"
0x41191  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedPropertyMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetManagedProperty(string)
0x41196  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedPropertyMetadata::get_ErrorCode()
0x4119b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x411a0  throw
0x411a1  ldarg.2
0x411a2  ldloc.2
0x411a3  call     void Microsoft.Crm.Metadata.OptionSetService::ValidateIsGlobalAgainstExistingOptionSet(bool expectedIsGlobal, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag existingOptionSetDescription)
0x411a8  ldarg.s  4
0x411aa  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x411af  stloc.3
0x411b0  ldc.i4.m1
0x411b1  stloc.s  4
0x411b3  ldloc.2
0x411b4  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetType()
0x411b9  stloc.s  5
0x411bb  ldloc.s  5
0x411bd  brfalse.s loc_411EE
0x411bf  ldloc.s  5
0x411c1  ldc.i4.2
0x411c2  beq.s    loc_411EE
0x411c4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x411c9  ldstr    aOptionsetsOfTy// "OptionSets of type {0} cannot have new "...
0x411ce  ldc.i4.1
0x411cf  newarr   [mscorlib]System.Object
0x411d4  dup
0x411d5  ldc.i4.0
0x411d6  ldloc.s  5
0x411d8  box      [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType
0x411dd  stelem.ref
0x411de  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x411e3  ldc.i4   0x80044320
0x411e8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x411ed  throw
0x411ee  ldloc.s  5
0x411f0  ldc.i4.2
0x411f1  bne.un.s loc_41209
0x411f3  ldarg.0
0x411f4  ldarg.1
0x411f5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeEnumValueData::get_EnumDescription()
0x411fa  ldloc.0
0x411fb  ldarg.s  4
0x411fd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x41202  call     instance void Microsoft.Crm.Metadata.EnumOptionService::ValidateStateValueForStatusOption(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity statusOptionData, valuetype [mscorlib]System.Guid parentOptionSetId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x41207  br.s     loc_4121A
0x41209  ldarg.1
0x4120a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeEnumValueData::get_EnumDescription()
0x4120f  ldstr    aStateStatusVal// "state_status_value"
0x41214  ldnull
0x41215  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x4121a  ldarg.1
0x4121b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeEnumValueData::get_EnumDescription()
0x41220  ldstr    aValue// "value"
0x41225  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x4122a  brfalse.s loc_41250
0x4122c  ldarg.1
0x4122d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeEnumValueData::get_EnumDescription()
0x41232  ldstr    aValue// "value"
0x41237  ldloc.0
0x41238  ldarg.s  4
0x4123a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4123f  call     int32 Microsoft.Crm.Metadata.EnumOptionService::GetNextAvailableEnumValue(valuetype [mscorlib]System.Guid optionSetId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x41244  box      [mscorlib]System.Int32
0x41249  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x4124e  br.s     loc_41273
0x41250  ldarg.0
0x41251  ldarg.1
0x41252  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeEnumValueData::get_EnumDescription()
0x41257  ldstr    aValue// "value"
0x4125c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x41261  unbox.any [mscorlib]System.Int32
0x41266  ldloc.0
0x41267  ldarg.s  4
0x41269  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4126e  call     instance void Microsoft.Crm.Metadata.EnumOptionService::ValidateCustomPicklistOrStatusValue(int32 picklistOrStatusValue, valuetype [mscorlib]System.Guid optionSetId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x41273  ldarg.1
0x41274  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeEnumValueData::get_EnumDescription()
0x41279  ldstr    aValue// "value"
0x4127e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x41283  unbox.any [mscorlib]System.Int32
0x41288  stloc.s  4
0x4128a  ldarg.1
0x4128b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeEnumValueData::get_EnumDescription()
0x41290  ldstr    aInvariantname// "invariantname"
0x41295  ldnull
0x41296  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x4129b  ldarg.1
0x4129c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeEnumValueData::get_EnumDescription()
0x412a1  ldstr    aDisplayorder// "displayorder"
0x412a6  ldloc.0
0x412a7  ldarg.s  4
0x412a9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x412ae  call     int32 Microsoft.Crm.Metadata.EnumOptionService::GetNextDisplayOrder(valuetype [mscorlib]System.Guid optionSetId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x412b3  box      [mscorlib]System.Int32
0x412b8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x412bd  ldarg.1
0x412be  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeEnumValueData::get_EnumDescription()
0x412c3  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x412c8  stloc.s  6
0x412ca  ldloc.s  6
0x412cc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_OptionSetId()
0x412d1  ldloc.s  5
0x412d3  ldloc.s  6
0x412d5  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_Value()
0x412da  ldarg.s  4
0x412dc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x412e1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption Microsoft.Crm.Metadata.EnumOptionService::GetExistingAttributePicklist(valuetype [mscorlib]System.Guid optionSetId, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType optionSetType, int32 optionValue, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x412e6  stloc.s  7
0x412e8  ldarg.s  4
0x412ea  ldc.i4.1
0x412eb  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoAddRootsContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AddRootsOption)
0x412f0  stloc.s  8
0x412f2  ldarg.1
0x412f3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Metadata.AttributeEnumValueData::get_DisplayValues()
0x412f8  ldstr    aLabels// "labels"
0x412fd  ldstr    aLabel// "label"
0x41302  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.DataToInfoConversionHelper::CreateLabelCollectionFromEntityCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection labelsEntityCollection, string collectionName, string labelName)
0x41307  stloc.s  9
0x41309  ldarg.1
0x4130a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Metadata.AttributeEnumValueData::get_Descriptions()
0x4130f  ldstr    aDescriptions// "Descriptions"
0x41314  ldstr    aDescription// "Description"
0x41319  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.DataToInfoConversionHelper::CreateLabelCollectionFromEntityCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection labelsEntityCollection, string collectionName, string labelName)
0x4131e  stloc.s  0xA
0x41320  ldloc.s  6
0x41322  ldloc.s  5
0x41324  ldloc.s  6
0x41326  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_AttributePicklistValueId()
0x4132b  ldloc.s  9
0x4132d  ldloc.s  0xA
0x4132f  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PreloadedEnumOptionMetadataDataProviderFull::.ctor(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection)
0x41334  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionValueFactory::CreateEnumOptionValue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributePicklistValueDescription, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionMetadataDataProvider)
0x41339  stloc.s  0xB
0x4133b  ldloc.s  7
0x4133d  brfalse.s loc_4135C
0x4133f  ldloc.s  0xB
0x41341  ldloc.s  7
0x41343  ldloc.2
0x41344  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_ParentOptionSetId()
0x41349  ldloc.s  5
0x4134b  ldnull
0x4134c  ldc.i4.1
0x4134d  ldarg.3
0x4134e  ldarg.s  4
0x41350  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x41355  call     void Microsoft.Crm.Metadata.EnumOptionService::UpdateInternal(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption option, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption oldOption, valuetype [mscorlib]System.Guid parentOptionSetId, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType optionSetType, class [System.Core]System.Collections.Generic.HashSet`1<int32> parentOptionSetValues, bool mergeLabels, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4135a  br.s     loc_41374
0x4135c  ldloc.s  0xB
0x4135e  ldloc.2
0x4135f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_ParentOptionSetId()
0x41364  ldc.i4.1
0x41365  ldloc.s  5
0x41367  ldarg.3
0x41368  ldarg.s  4
0x4136a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4136f  call     void Microsoft.Crm.Metadata.EnumOptionService::CreateInternal(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption enumOption, valuetype [mscorlib]System.Guid parentOptionSetId, bool validateValue, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType optionSetType, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x41374  ldarg.3
0x41375  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x4137a  leave.s  loc_41388
0x4137c  ldloc.s  8
0x4137e  brfalse.s loc_41387
0x41380  ldloc.s  8
0x41382  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41387  endfinally
0x41388  ldarg.s  4
0x4138a  ldc.i4.4
0x4138b  ldloc.s  6
0x4138d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_OptionSetId()
0x41392  ldc.i4.s 9
0x41394  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::AddDependencyOperation(valuetype [Microsoft.Crm.Core]Microsoft.Crm.DependencyOperationType, valuetype [mscorlib]System.Guid, int32)
0x41399  ldloc.3
0x4139a  brfalse.s loc_413A3
0x4139c  ldarg.s  4
0x4139e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x413a3  ldloc.s  4
0x413a5  stloc.s  0xC
0x413a7  leave.s  loc_413D7
0x413a9  stloc.s  0xD
0x413ab  ldloc.s  0xD
0x413ad  ldarg.s  4
0x413af  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x413b4  ldc.i4.s 0x19
0x413b6  ldstr    aEnumoptionserv// "EnumOptionServce.Create caught exceptio"...
0x413bb  ldc.i4.1
  ... truncated ...
```
