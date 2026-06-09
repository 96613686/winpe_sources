# Microsoft.Crm.Metadata.EnumOptionService::Update

- ea: `0x41740`
- end: `0x419d8`
- name: `Microsoft.Crm.Metadata.EnumOptionService::Update`
- size: `664`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xf470`
- `0xf500`
- `0x78620`

## callees

- `0x2bda0`
- `0x41670`
- `0x416f0`
- `0x41740`
- `0x426c0`
- `0x42810`
- `0x49900`
- `0x49910`
- `0x49920`
- `0x4bc30`
- `0x5a810`

## string_xrefs

- `0x41860`: `prvWriteAttribute`
- `0x41844`: `prvWriteOptionSet`
- `0x4177d`: `The optionSet picklist value id must be provided to update a picklist value`
- `0x41886`: `Local OptionSet({0}, Id={1}) is not customizable and cannot be fully updated.  Stripping out non-customizable fields.`
- `0x419b5`: `EnumOptionServce.Update caught exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x41740  ldarg.1
0x41741  ldstr    aPicklistdata// "picklistData"
0x41746  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4174b  ldarg.s  4
0x4174d  ldstr    aContext// "context"
0x41752  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x41757  ldarg.s  4
0x41759  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4175e  pop
0x4175f  ldarg.1
0x41760  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeEnumValueData::get_EnumDescription()
0x41765  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x4176a  stloc.0
0x4176b  ldloc.0
0x4176c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag::get_InnerEntityData()
0x41771  ldstr    aAttributepickl_0// "attributepicklistvalueid"
0x41776  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x4177b  brfalse.s loc_41788
0x4177d  ldstr    aTheOptionsetPi// "The optionSet picklist value id must be"...
0x41782  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x41787  throw
0x41788  ldloc.0
0x41789  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_AttributePicklistValueId()
0x4178e  stloc.1
0x4178f  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x41794  ldloc.1
0x41795  ldstr    aAttributepickl// "AttributePicklistValue"
0x4179a  ldarg.s  4
0x4179c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x417a1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x417a6  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x417ab  stloc.2
0x417ac  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x417b1  ldloc.2
0x417b2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_OptionSetId()
0x417b7  ldstr    aOptionset_0// "OptionSet"
0x417bc  ldc.i4.7
0x417bd  newarr   [mscorlib]System.String
0x417c2  dup
0x417c3  ldc.i4.0
0x417c4  ldstr    aIsglobal// "isglobal"
0x417c9  stelem.ref
0x417ca  dup
0x417cb  ldc.i4.1
0x417cc  ldstr    aOptionsettype// "optionsettype"
0x417d1  stelem.ref
0x417d2  dup
0x417d3  ldc.i4.2
0x417d4  ldstr    aIscustomizable// "iscustomizable"
0x417d9  stelem.ref
0x417da  dup
0x417db  ldc.i4.3
0x417dc  ldstr    aIsmanaged// "ismanaged"
0x417e1  stelem.ref
0x417e2  dup
0x417e3  ldc.i4.4
0x417e4  ldstr    aOptionsetid// "optionsetid"
0x417e9  stelem.ref
0x417ea  dup
0x417eb  ldc.i4.5
0x417ec  ldstr    aName// "name"
0x417f1  stelem.ref
0x417f2  dup
0x417f3  ldc.i4.6
0x417f4  ldstr    aParentoptionse// "parentoptionsetid"
0x417f9  stelem.ref
0x417fa  ldarg.s  4
0x417fc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x41801  stloc.3
0x41802  ldloc.3
0x41803  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x41808  stloc.s  4
0x4180a  ldloc.s  4
0x4180c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetType()
0x41811  stloc.s  5
0x41813  ldloc.2
0x41814  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_OptionSetId()
0x41819  ldloc.s  4
0x4181b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetType()
0x41820  ldloc.2
0x41821  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_Value()
0x41826  ldarg.s  4
0x41828  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4182d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption Microsoft.Crm.Metadata.EnumOptionService::GetExistingAttributePicklist(valuetype [mscorlib]System.Guid optionSetId, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType optionSetType, int32 optionValue, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x41832  stloc.s  6
0x41834  ldloc.s  4
0x41836  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_IsGlobal()
0x4183b  brfalse.s loc_41859
0x4183d  ldarg.s  4
0x4183f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x41844  ldstr    aPrvwriteoption// "prvWriteOptionSet"
0x41849  ldarg.s  4
0x4184b  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x41850  ldarg.s  4
0x41852  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x41857  br.s     loc_418C1
0x41859  ldarg.s  4
0x4185b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x41860  ldstr    aPrvwriteattrib// "prvWriteAttribute"
0x41865  ldarg.s  4
0x41867  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4186c  ldarg.s  4
0x4186e  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x41873  ldloc.3
0x41874  ldarg.s  4
0x41876  call     bool Microsoft.Crm.Metadata.EnumOptionService::IsOptionSetCustomizableInternal(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity optionSetData, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4187b  brtrue.s loc_418C1
0x4187d  ldarg.s  4
0x4187f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x41884  ldc.i4.s 0x19
0x41886  ldstr    aLocalOptionset// "Local OptionSet({0}, Id={1}) is not cus"...
0x4188b  ldc.i4.2
0x4188c  newarr   [mscorlib]System.Object
0x41891  dup
0x41892  ldc.i4.0
0x41893  ldloc.s  4
0x41895  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_Name()
0x4189a  stelem.ref
0x4189b  dup
0x4189c  ldc.i4.1
0x4189d  ldloc.s  4
0x4189f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x418a4  box      [mscorlib]System.Guid
0x418a9  stelem.ref
0x418aa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x418af  ldarg.1
0x418b0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeEnumValueData::get_EnumDescription()
0x418b5  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.MetadataEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x418ba  ldarg.s  4
0x418bc  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IsCustomizableCondition::StripOutUnmanagedAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x418c1  ldarg.2
0x418c2  ldloc.s  4
0x418c4  call     void Microsoft.Crm.Metadata.OptionSetService::ValidateIsGlobalAgainstExistingOptionSet(bool expectedIsGlobal, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag existingOptionSetDescription)
0x418c9  ldloc.0
0x418ca  ldloc.2
0x418cb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag::CreateDifferenceDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag)
0x418d0  stloc.s  7
0x418d2  ldarg.s  4
0x418d4  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x418d9  stloc.s  8
0x418db  ldarg.s  4
0x418dd  ldc.i4.1
0x418de  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoAddRootsContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AddRootsOption)
0x418e3  stloc.s  9
0x418e5  ldarg.s  4
0x418e7  ldarg.s  4
0x418e9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x418ee  ldc.i4.1
0x418ef  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::.ctor()
0x418f4  newobj   instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Guid, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject)
0x418f9  stloc.s  0xA
0x418fb  ldloc.s  7
0x418fd  brfalse.s loc_41910
0x418ff  ldarg.0
0x41900  ldloc.s  7
0x41902  ldloc.s  4
0x41904  ldarg.s  4
0x41906  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4190b  call     instance void Microsoft.Crm.Metadata.EnumOptionService::ValidateForUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag differenceDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag optionSetDescription, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x41910  ldarg.1
0x41911  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Metadata.AttributeEnumValueData::get_DisplayValues()
0x41916  ldstr    aLabels// "labels"
0x4191b  ldstr    aLabel// "label"
0x41920  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.DataToInfoConversionHelper::CreateLabelCollectionFromEntityCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection labelsEntityCollection, string collectionName, string labelName)
0x41925  stloc.s  0xB
0x41927  ldarg.1
0x41928  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Metadata.AttributeEnumValueData::get_Descriptions()
0x4192d  ldstr    aDescriptions// "Descriptions"
0x41932  ldstr    aDescription// "Description"
0x41937  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.DataToInfoConversionHelper::CreateLabelCollectionFromEntityCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection labelsEntityCollection, string collectionName, string labelName)
0x4193c  stloc.s  0xC
0x4193e  ldloc.0
0x4193f  ldloc.s  5
0x41941  ldloc.0
0x41942  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_AttributePicklistValueId()
0x41947  ldloc.s  0xB
0x41949  ldloc.s  0xC
0x4194b  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PreloadedEnumOptionMetadataDataProviderFull::.ctor(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection)
0x41950  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionValueFactory::CreateEnumOptionValue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributePicklistValueDescription, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionMetadataDataProvider)
0x41955  ldloc.s  6
0x41957  ldloc.s  4
0x41959  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_ParentOptionSetId()
0x4195e  ldloc.s  4
0x41960  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetType()
0x41965  ldnull
0x41966  ldarg.3
0x41967  ldloc.s  0xA
0x41969  ldarg.s  4
0x4196b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x41970  call     void Microsoft.Crm.Metadata.EnumOptionService::UpdateInternal(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption option, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption oldOption, valuetype [mscorlib]System.Guid parentOptionSetId, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType optionSetType, class [System.Core]System.Collections.Generic.HashSet`1<int32> parentOptionSetValues, bool mergeLabels, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x41975  ldloc.s  0xA
0x41977  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x4197c  ldarg.s  4
0x4197e  ldc.i4.4
0x4197f  ldloc.s  4
0x41981  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x41986  ldc.i4.s 9
0x41988  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::AddDependencyOperation(valuetype [Microsoft.Crm.Core]Microsoft.Crm.DependencyOperationType, valuetype [mscorlib]System.Guid, int32)
0x4198d  leave.s  loc_4199B
0x4198f  ldloc.s  9
0x41991  brfalse.s loc_4199A
0x41993  ldloc.s  9
0x41995  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4199a  endfinally
0x4199b  ldloc.s  8
0x4199d  brfalse.s loc_419A6
0x4199f  ldarg.s  4
0x419a1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x419a6  leave.s  loc_419D7
0x419a8  stloc.s  0xD
0x419aa  ldloc.s  0xD
0x419ac  ldarg.s  4
0x419ae  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x419b3  ldc.i4.s 0x19
0x419b5  ldstr    aEnumoptionserv_0// "EnumOptionServce.Update caught exceptio"...
0x419ba  ldc.i4.1
0x419bb  newarr   [mscorlib]System.Object
0x419c0  dup
0x419c1  ldc.i4.0
0x419c2  ldloc.s  0xD
0x419c4  stelem.ref
0x419c5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x419ca  ldloc.s  8
0x419cc  brfalse.s loc_419D5
0x419ce  ldarg.s  4
0x419d0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0x419d5  rethrow
0x419d7  ret
```
