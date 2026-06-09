# Microsoft.Crm.ObjectModel.SenderFormPageConverter::BuildPanorama

- ea: `0xaee70`
- end: `0xaf1a5`
- name: `Microsoft.Crm.ObjectModel.SenderFormPageConverter::BuildPanorama`
- size: `821`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0xadbd0`

## callees

- `0x19ba0`
- `0xae340`
- `0xae3e0`
- `0xae480`
- `0xae550`
- `0xae8c0`
- `0xaeb40`
- `0xaee70`
- `0xb9cc0`
- `0xb9d60`

## string_xrefs

- `0xaf044`: `PopOutLinkLabelViewModel`
- `0xaf049`: `PopOutLinkLabel`
- `0xaf0a1`: `PopOutLinkLabelCommandName`
- `0xaf0a9`: `OpenInBrowserCommand`
- `0xaf0b9`: `MoCA_OWA_PopoutLink_Label_Tooltip`
- `0xaf04e`: `CompanyLabel`
- `0xaf116`: `HasCollapseForAcompli`
- `0xaf099`: `company_name`
- `0xaf152`: `CompanyPane`
- `0xaf168`: `companyPaneCssClass`

## pseudocode

```c

```

## disassembly

```asm
0xaee70  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::.ctor()
0xaee75  stloc.2
0xaee76  ldloc.2
0xaee77  ldstr    aPanoramaitem// "PanoramaItem"
0xaee7c  ldstr    aPanoramaitem// "PanoramaItem"
0xaee81  ldstr    aLoading// "loading"
0xaee86  ldc.i4.1
0xaee87  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor
0xaee8c  dup
0xaee8d  ldc.i4.0
0xaee8e  ldstr    aShowprogress// "showProgress"
0xaee93  ldc.i4.1
0xaee94  box      [mscorlib]System.Boolean
0xaee99  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xaee9e  stelem.ref
0xaee9f  ldc.i4.2
0xaeea0  newarr   [mscorlib]System.Object
0xaeea5  dup
0xaeea6  ldc.i4.0
0xaeea7  ldstr    aCssclass// "CssClass"
0xaeeac  stelem.ref
0xaeead  dup
0xaeeae  ldc.i4.1
0xaeeaf  ldstr    aLoadingpanecss// "loadingPaneCssClass"
0xaeeb4  stelem.ref
0xaeeb5  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0xaeeba  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::.ctor(string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary)
0xaeebf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0xaeec4  ldloc.2
0xaeec5  stloc.0
0xaeec6  ldarg.0
0xaeec7  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.SubGridDescriptor> Microsoft.Crm.ObjectModel.SenderFormPageConverter::GetSubgridDescriptors()
0xaeecc  ldnull
0xaeecd  stloc.1
0xaeece  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.SubGridDescriptor>::GetEnumerator()
0xaeed3  stloc.3
0xaeed4  br       loc_AEF86
0xaeed9  ldloca.s 3
0xaeedb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.ObjectModel.SubGridDescriptor>::get_Current()
0xaeee0  stloc.s  4
0xaeee2  ldarg.0
0xaeee3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.ObjectModel.RelationshipMetadata>> Microsoft.Crm.ObjectModel.SenderFormPageConverter::_internalRelationshipMetadataIndexedByRelationshipName
0xaeee8  ldloc.s  4
0xaeeea  ldfld    string Microsoft.Crm.ObjectModel.SubGridDescriptor::RelationshipName
0xaeeef  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.ObjectModel.RelationshipMetadata>>::get_Item(void)
0xaeef4  ldc.i4.0
0xaeef5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.ObjectModel.RelationshipMetadata>::get_Item(!!T0)
0xaeefa  stloc.s  5
0xaeefc  ldloca.s 6
0xaeefe  ldloc.s  4
0xaef00  ldfld    string Microsoft.Crm.ObjectModel.SubGridDescriptor::ViewId
0xaef05  call     instance void [mscorlib]System.Guid::.ctor(string)
0xaef0a  ldloc.s  4
0xaef0c  ldfld    valuetype Microsoft.Crm.ObjectModel.ControlType Microsoft.Crm.ObjectModel.SubGridDescriptor::Type
0xaef11  ldc.i4.s 0x13
0xaef13  bne.un.s loc_AEF3E
0xaef15  ldloc.0
0xaef16  ldc.i4.1
0xaef17  ldarg.0
0xaef18  ldloc.s  5
0xaef1a  call     instance class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor Microsoft.Crm.ObjectModel.SenderFormPageConverter::BuildUpdomingActivities(class Microsoft.Crm.ObjectModel.RelationshipMetadata activityRelationship)
0xaef1f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Insert(int32, var<u1>)
0xaef24  ldloc.0
0xaef25  ldc.i4.2
0xaef26  ldarg.0
0xaef27  ldloc.s  5
0xaef29  call     instance class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor Microsoft.Crm.ObjectModel.SenderFormPageConverter::BuildPastActivities(class Microsoft.Crm.ObjectModel.RelationshipMetadata activityRelationship)
0xaef2e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Insert(int32, var<u1>)
0xaef33  ldarg.0
0xaef34  ldloc.s  5
0xaef36  call     instance class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor Microsoft.Crm.ObjectModel.SenderFormPageConverter::BuildNotesPane(class Microsoft.Crm.ObjectModel.RelationshipMetadata activityRelationship)
0xaef3b  stloc.1
0xaef3c  br.s     loc_AEF86
0xaef3e  ldloca.s 6
0xaef40  ldstr    a4e3600faB9c849// "{4E3600FA-B9C8-49F4-B69A-51EBA06D9BDF}"
0xaef45  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xaef4a  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xaef4f  brtrue.s loc_AEF64
0xaef51  ldloca.s 6
0xaef53  ldstr    aFe4bc089890146// "{FE4BC089-8901-466C-A41B-1C1090F204D4}"
0xaef58  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xaef5d  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xaef62  brfalse.s loc_AEF76
0xaef64  ldloc.0
0xaef65  ldarg.0
0xaef66  ldloc.s  6
0xaef68  ldloc.s  5
0xaef6a  call     instance class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor Microsoft.Crm.ObjectModel.SenderFormPageConverter::CreateConnectionListViewModelFromViewInformation(valuetype [mscorlib]System.Guid viewIdGuid, class Microsoft.Crm.ObjectModel.RelationshipMetadata relationshipMetadata)
0xaef6f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0xaef74  br.s     loc_AEF86
0xaef76  ldloc.0
0xaef77  ldarg.0
0xaef78  ldloc.s  5
0xaef7a  ldloc.s  4
0xaef7c  call     instance class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor Microsoft.Crm.ObjectModel.SenderFormPageConverter::BuildPane(class Microsoft.Crm.ObjectModel.RelationshipMetadata relationshipMetadata, class Microsoft.Crm.ObjectModel.SubGridDescriptor subGridDescriptor)
0xaef81  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0xaef86  ldloca.s 3
0xaef88  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.ObjectModel.SubGridDescriptor>::MoveNext()
0xaef8d  brtrue   loc_AEED9
0xaef92  leave.s  loc_AEFA2
0xaef94  ldloca.s 3
0xaef96  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.ObjectModel.SubGridDescriptor>
0xaef9c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaefa1  endfinally
0xaefa2  ldloc.1
0xaefa3  brfalse.s loc_AEFAC
0xaefa5  ldloc.0
0xaefa6  ldloc.1
0xaefa7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0xaefac  ldarg.0
0xaefad  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.ObjectModel.SenderFormPageConverter::_entityMetadata
0xaefb2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xaefb7  ldstr    aContact_0// "contact"
0xaefbc  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaefc1  brtrue.s loc_AEFDD
0xaefc3  ldarg.0
0xaefc4  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.ObjectModel.SenderFormPageConverter::_entityMetadata
0xaefc9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xaefce  ldstr    aLead_0// "lead"
0xaefd3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaefd8  brfalse  loc_AF188
0xaefdd  ldarg.0
0xaefde  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.ObjectModel.SenderFormPageConverter::_entityMetadata
0xaefe3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xaefe8  ldstr    aContact_0// "contact"
0xaefed  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaeff2  brtrue.s loc_AEFFB
0xaeff4  ldstr    aParentaccounti// "parentaccountid"
0xaeff9  br.s     loc_AF000
0xaeffb  ldstr    aParentcustomer// "parentcustomerid"
0xaf000  stloc.s  7
0xaf002  ldarg.0
0xaf003  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.ConverterBase::get_Context()
0xaf008  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0xaf00d  ldstr    aAccount_0// "account"
0xaf012  ldc.i4.1
0xaf013  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xaf018  stloc.s  8
0xaf01a  ldloc.s  8
0xaf01c  brfalse  loc_AF188
0xaf021  ldc.i4.1
0xaf022  stloc.s  9
0xaf024  ldloc.1
0xaf025  brfalse.s loc_AF02A
0xaf027  ldc.i4.3
0xaf028  stloc.s  9
0xaf02a  ldloc.s  8
0xaf02c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0xaf031  ldarg.0
0xaf032  call     instance int32 Microsoft.Crm.ObjectModel.ConverterBase::get_UserLanguageCode()
0xaf037  ldarg.0
0xaf038  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.ConverterBase::get_Context()
0xaf03d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xaf042  stloc.s  0xA
0xaf044  ldstr    aPopoutlinklabe// "PopOutLinkLabelViewModel"
0xaf049  ldstr    aPopoutlinklabe_0// "PopOutLinkLabel"
0xaf04e  ldstr    aCompanylabel// "CompanyLabel"
0xaf053  ldloc.s  7
0xaf055  ldstr    aName_1// "!name"
0xaf05a  call     string [mscorlib]System.String::Concat(string, string)
0xaf05f  ldnull
0xaf060  ldc.i4.2
0xaf061  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor
0xaf066  dup
0xaf067  ldc.i4.0
0xaf068  ldstr    aEntityreferenc_1// "EntityReferenceField"
0xaf06d  ldloc.s  7
0xaf06f  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xaf074  stelem.ref
0xaf075  dup
0xaf076  ldc.i4.1
0xaf077  ldstr    aShowsetregardi// "ShowSetRegardingButton"
0xaf07c  ldc.i4.1
0xaf07d  box      [mscorlib]System.Boolean
0xaf082  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xaf087  stelem.ref
0xaf088  ldc.i4.s 0xE
0xaf08a  newarr   [mscorlib]System.Object
0xaf08f  dup
0xaf090  ldc.i4.0
0xaf091  ldstr    aLabelcssclass// "LabelCssClass"
0xaf096  stelem.ref
0xaf097  dup
0xaf098  ldc.i4.1
0xaf099  ldstr    aCompanyName// "company_name"
0xaf09e  stelem.ref
0xaf09f  dup
0xaf0a0  ldc.i4.2
0xaf0a1  ldstr    aPopoutlinklabe_1// "PopOutLinkLabelCommandName"
0xaf0a6  stelem.ref
0xaf0a7  dup
0xaf0a8  ldc.i4.3
0xaf0a9  ldstr    aOpeninbrowserc// "OpenInBrowserCommand"
0xaf0ae  stelem.ref
0xaf0af  dup
0xaf0b0  ldc.i4.4
0xaf0b1  ldstr    aTitle// "Title"
0xaf0b6  stelem.ref
0xaf0b7  dup
0xaf0b8  ldc.i4.5
0xaf0b9  ldstr    aMocaOwaPopoutl// "MoCA_OWA_PopoutLink_Label_Tooltip"
0xaf0be  ldarg.0
0xaf0bf  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.ObjectModel.SenderFormPageConverter::userCultureInfo
0xaf0c4  ldc.i4.1
0xaf0c5  newarr   [mscorlib]System.Object
0xaf0ca  dup
0xaf0cb  ldc.i4.0
0xaf0cc  ldloc.s  0xA
0xaf0ce  callvirt instance string [mscorlib]System.String::ToLower()
0xaf0d3  stelem.ref
0xaf0d4  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture, object[] args)
0xaf0d9  stelem.ref
0xaf0da  dup
0xaf0db  ldc.i4.6
0xaf0dc  ldstr    aSetregardingbu_1// "SetRegardingButtonTitle"
0xaf0e1  stelem.ref
0xaf0e2  dup
0xaf0e3  ldc.i4.7
0xaf0e4  ldstr    aMocaOwaSetrega// "MoCA_OWA_SetRegarding_Button_Tooltip"
0xaf0e9  ldarg.0
0xaf0ea  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.ObjectModel.SenderFormPageConverter::userCultureInfo
0xaf0ef  ldc.i4.1
0xaf0f0  newarr   [mscorlib]System.Object
0xaf0f5  dup
0xaf0f6  ldc.i4.0
0xaf0f7  ldloc.s  0xA
0xaf0f9  callvirt instance string [mscorlib]System.String::ToLower()
0xaf0fe  stelem.ref
0xaf0ff  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture, object[] args)
0xaf104  stelem.ref
0xaf105  dup
0xaf106  ldc.i4.8
0xaf107  ldstr    aPrefixtext// "PrefixText"
0xaf10c  stelem.ref
0xaf10d  dup
0xaf10e  ldc.i4.s 9
0xaf110  ldloc.s  0xA
0xaf112  stelem.ref
0xaf113  dup
0xaf114  ldc.i4.s 0xA
0xaf116  ldstr    aHascollapsefor// "HasCollapseForAcompli"
0xaf11b  stelem.ref
0xaf11c  dup
0xaf11d  ldc.i4.s 0xB
0xaf11f  ldc.i4.1
0xaf120  box      [mscorlib]System.Boolean
0xaf125  stelem.ref
0xaf126  dup
0xaf127  ldc.i4.s 0xC
0xaf129  ldstr    aCssclassname// "CssClassName"
0xaf12e  stelem.ref
0xaf12f  dup
0xaf130  ldc.i4.s 0xD
0xaf132  ldstr    aAccountcard// "accountCard"
0xaf137  stelem.ref
0xaf138  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0xaf13d  ldnull
0xaf13e  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.DescriptorBuilder::CreateControlViewModelDescriptor(string, string, string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, string)
0xaf143  stloc.s  0xB
0xaf145  ldloc.0
0xaf146  ldloc.s  9
0xaf148  ldstr    aPanoramaitem// "PanoramaItem"
0xaf14d  ldstr    aPanoramaitem// "PanoramaItem"
0xaf152  ldstr    aCompanypane// "CompanyPane"
0xaf157  ldnull
0xaf158  ldc.i4.2
0xaf159  newarr   [mscorlib]System.Object
0xaf15e  dup
0xaf15f  ldc.i4.0
0xaf160  ldstr    aCssclass// "CssClass"
0xaf165  stelem.ref
0xaf166  dup
0xaf167  ldc.i4.1
0xaf168  ldstr    aCompanypanecss// "companyPaneCssClass"
0xaf16d  stelem.ref
0xaf16e  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0xaf173  ldc.i4.1
0xaf174  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor
0xaf179  dup
0xaf17a  ldc.i4.0
0xaf17b  ldloc.s  0xB
0xaf17d  stelem.ref
0xaf17e  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::.ctor(string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor[])
0xaf183  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Insert(int32, var<u1>)
0xaf188  ldstr    aPanoramacontai// "PanoramaContainer"
0xaf18d  ldstr    aPanoramacontai// "PanoramaContainer"
0xaf192  ldstr    aSenderformitem// "SenderFormItemsPaneContainer"
0xaf197  ldnull
0xaf198  ldnull
0xaf199  ldloc.0
0xaf19a  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::ToArray()
0xaf19f  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::.ctor(string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor[])
0xaf1a4  ret
```
