# Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::FillTable

- ea: `0x3c0`
- end: `0x586`
- name: `Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::FillTable`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x250`

## callees

- `0x3c0`
- `0x590`
- `0x700`

## string_xrefs

- `0x466`: `formxml`

## pseudocode

```c

```

## disassembly

```asm
0x3c0  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Utility.SortedNameList::.ctor()
0x3c5  stloc.0
0x3c6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3cb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3d0  stloc.1
0x3d1  ldloc.1
0x3d2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Entities()
0x3d7  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x3dc  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x3e1  stloc.s  4
0x3e3  br       loc_4A5
0x3e8  ldloc.s  4
0x3ea  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3ef  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata
0x3f4  stloc.s  5
0x3f6  ldloc.s  5
0x3f8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomizable()
0x3fd  brfalse  loc_4A5
0x402  ldloc.s  5
0x404  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanModifyAdditionalSettings()
0x409  brfalse  loc_4A5
0x40e  ldloc.s  5
0x410  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x415  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::CanEntityBeAssociationEntity(valuetype [mscorlib]System.Guid)
0x41a  brfalse  loc_4A5
0x41f  ldloc.s  5
0x421  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x426  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x42b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsRefreshEnabledForEntity(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x430  brfalse.s loc_4A5
0x432  ldloc.s  5
0x434  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x439  ldstr    aBpfbusinessent// "BpfBusinessEntity"
0x43e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x443  brtrue.s loc_4A5
0x445  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x44a  brfalse.s loc_455
0x44c  ldloc.s  5
0x44e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsReplicated()
0x453  brfalse.s loc_4A5
0x455  nop
0x456  ldloc.s  5
0x458  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x45d  ldc.i4.2
0x45e  ldc.i4.1
0x45f  newarr   [mscorlib]System.String
0x464  dup
0x465  ldc.i4.0
0x466  ldstr    aFormxml// "formxml"
0x46b  stelem.ref
0x46c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x471  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveInProductionForms(string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x476  stloc.s  6
0x478  ldloc.s  6
0x47a  brfalse.s loc_4A0
0x47c  ldloc.s  6
0x47e  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x483  ldc.i4.0
0x484  ble.s    loc_4A0
0x486  ldloc.0
0x487  ldloc.s  5
0x489  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x48e  ldloc.s  5
0x490  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x495  ldc.i4.1
0x496  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x49b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Utility.SortedNameList::Add(object, string)
0x4a0  leave.s  loc_4A5
0x4a2  pop
0x4a3  leave.s  loc_4A5
0x4a5  ldloc.s  4
0x4a7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4ac  brtrue   loc_3E8
0x4b1  leave.s  loc_4C8
0x4b3  ldloc.s  4
0x4b5  isinst   [mscorlib]System.IDisposable
0x4ba  stloc.s  7
0x4bc  ldloc.s  7
0x4be  brfalse.s loc_4C7
0x4c0  ldloc.s  7
0x4c2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c7  endfinally
0x4c8  ldloc.0
0x4c9  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Utility.SortNameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Utility.SortedNameList::get_SortedList()
0x4ce  stloc.2
0x4cf  ldarg.0
0x4d0  call     instance void Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::UpdateColumnHeader()
0x4d5  ldc.i4.0
0x4d6  stloc.3
0x4d7  ldc.i4.0
0x4d8  stloc.s  8
0x4da  br.s     loc_552
0x4dc  ldloc.2
0x4dd  ldloc.s  8
0x4df  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, string>>::get_Item(!!T0)
0x4e4  stloc.s  0xC
0x4e6  ldloca.s 0xC
0x4e8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, string>::get_Key()
0x4ed  castclass [mscorlib]System.String
0x4f2  stloc.s  9
0x4f4  ldloc.1
0x4f5  ldloc.s  9
0x4f7  ldc.i4.1
0x4f8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x4fd  dup
0x4fe  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsKnowledgeManagementEnabled()
0x503  stloc.s  0xA
0x505  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x50a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x50f  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x514  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x519  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x51e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x523  stloc.s  0xB
0x525  ldarg.0
0x526  ldloc.s  8
0x528  ldloc.s  9
0x52a  ldloc.2
0x52b  ldloc.s  8
0x52d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, string>>::get_Item(!!T0)
0x532  stloc.s  0xC
0x534  ldloca.s 0xC
0x536  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, string>::get_Value()
0x53b  ldloc.s  0xA
0x53d  ldloc.s  0xB
0x53f  call     instance void Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::AddRow(int32 rowNo, string entityName, string entityDisplayName, bool knowledgeManagementEnabled, string baseLangDisplayName)
0x544  ldloc.s  0xA
0x546  brfalse.s loc_54C
0x548  ldloc.3
0x549  ldc.i4.1
0x54a  add
0x54b  stloc.3
0x54c  ldloc.s  8
0x54e  ldc.i4.1
0x54f  add
0x550  stloc.s  8
0x552  ldloc.s  8
0x554  ldloc.2
0x555  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, string>>::get_Count()
0x55a  blt.s    loc_4DC
0x55c  ldarg.0
0x55d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x562  ldstr    aEntityCount// "ENTITY_COUNT"
0x567  ldloc.2
0x568  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, string>>::get_Count()
0x56d  conv.i8
0x56e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x573  ldarg.0
0x574  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x579  ldstr    aKmEntityCountS// "KM_ENTITY_COUNT_SELECTED"
0x57e  ldloc.3
0x57f  conv.i8
0x580  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x585  ret
```
