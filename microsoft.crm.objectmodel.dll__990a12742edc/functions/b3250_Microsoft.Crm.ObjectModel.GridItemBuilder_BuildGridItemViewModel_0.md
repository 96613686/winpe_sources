# Microsoft.Crm.ObjectModel.GridItemBuilder::BuildGridItemViewModel_0

- ea: `0xb3250`
- end: `0xb35f9`
- name: `Microsoft.Crm.ObjectModel.GridItemBuilder::BuildGridItemViewModel_0`
- size: `937`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0xb3240`
- `0xb5530`

## callees

- `0x19b50`
- `0xb1260`
- `0xb3250`
- `0xb3610`
- `0xb3630`
- `0xb4010`
- `0xb58d0`
- `0xb5920`
- `0xb5a70`
- `0xb9d00`

## string_xrefs

- `0xb34f9`: `Command`
- `0xb3531`: `Command`
- `0xb35ad`: `ShortPressCommandName`
- `0xb3536`: `UrlLauncherCommand`
- `0xb34fe`: `SkypeUrlLauncherCommand`
- `0xb34ca`: `PartyListRead`
- `0xb34e7`: `PhoneReadOnly`
- `0xb351f`: `EmailReadOnly`
- `0xb35b2`: `SharepointDocumentLauncherCommand`

## pseudocode

```c

```

## disassembly

```asm
0xb3250  ldarg.2
0xb3251  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0xb3256  ldarg.0
0xb3257  callvirt instance int32 Microsoft.Crm.ObjectModel.ListQueryWrapper::get_AssociatedEntityType()
0xb325c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0xb3261  stloc.0
0xb3262  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::.ctor()
0xb3267  stloc.1
0xb3268  ldloc.0
0xb3269  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xb326e  ldstr    aSyncerror// "syncerror"
0xb3273  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb3278  brtrue.s loc_B3282
0xb327a  ldarg.0
0xb327b  call     class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.ObjectModel.ListItemBuilder::RetrieveFieldNodes(class Microsoft.Crm.ObjectModel.ListQueryWrapper listQuery)
0xb3280  br.s     loc_B3288
0xb3282  ldarg.0
0xb3283  call     class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.ObjectModel.ListItemBuilder::RetrieveSyncErrorFieldNodes(class Microsoft.Crm.ObjectModel.ListQueryWrapper listQuery)
0xb3288  stloc.2
0xb3289  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<string>::.ctor()
0xb328e  stloc.3
0xb328f  ldarg.0
0xb3290  callvirt instance int32 Microsoft.Crm.ObjectModel.ListQueryWrapper::get_AssociatedEntityType()
0xb3295  ldc.i4   0x2523
0xb329a  bne.un   loc_B331F
0xb329f  ldarg.1
0xb32a0  brfalse.s loc_B32E5
0xb32a2  ldloc.1
0xb32a3  ldstr    aLabel_0// "Label"
0xb32a8  ldstr    aFonticon// "fonticon"
0xb32ad  ldnull
0xb32ae  ldnull
0xb32af  ldc.i4.2
0xb32b0  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor
0xb32b5  dup
0xb32b6  ldc.i4.0
0xb32b7  ldstr    aData// "Data"
0xb32bc  ldsfld   string [mscorlib]System.String::Empty
0xb32c1  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xb32c6  stelem.ref
0xb32c7  dup
0xb32c8  ldc.i4.1
0xb32c9  ldstr    aWidth_0// "Width"
0xb32ce  ldstr    a40// "40"
0xb32d3  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xb32d8  stelem.ref
0xb32d9  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.DescriptorBuilder::CreateControlOnlyViewModelDescriptor(string, string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[])
0xb32de  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0xb32e3  br.s     loc_B3314
0xb32e5  ldloc.1
0xb32e6  ldstr    aImage_0// "Image"
0xb32eb  ldstr    aFonticon// "fonticon"
0xb32f0  ldnull
0xb32f1  ldnull
0xb32f2  ldc.i4.1
0xb32f3  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor
0xb32f8  dup
0xb32f9  ldc.i4.0
0xb32fa  ldstr    aImageclassname// "ImageClassName"
0xb32ff  ldstr    aIconclassname// "iconclassname"
0xb3304  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ReferencePropertyDescriptor::.ctor(string, string)
0xb3309  stelem.ref
0xb330a  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.DescriptorBuilder::CreateControlOnlyViewModelDescriptor(string, string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[])
0xb330f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0xb3314  ldloc.3
0xb3315  ldstr    aFonticon// "fonticon"
0xb331a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb331f  ldc.i4.0
0xb3320  stloc.s  5
0xb3322  br       loc_B3587
0xb3327  ldloc.2
0xb3328  ldloc.s  5
0xb332a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xb332f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb3334  ldstr    aName// "name"
0xb3339  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb333e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xb3343  stloc.s  6
0xb3345  ldstr    a0_2// "0"
0xb334a  stloc.s  7
0xb334c  ldnull
0xb334d  stloc.s  8
0xb334f  ldloc.2
0xb3350  ldloc.s  5
0xb3352  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xb3357  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb335c  ldstr    aWidth// "width"
0xb3361  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb3366  brfalse.s loc_B3386
0xb3368  ldloc.2
0xb3369  ldloc.s  5
0xb336b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xb3370  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb3375  ldstr    aWidth// "width"
0xb337a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb337f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xb3384  stloc.s  7
0xb3386  ldloc.2
0xb3387  ldloc.s  5
0xb3389  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xb338e  call     bool Microsoft.Crm.ObjectModel.ListItemBuilder::IsFieldHidden(class [System.Xml]System.Xml.XmlNode field)
0xb3393  brfalse.s loc_B33AD
0xb3395  ldloc.0
0xb3396  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsInteractionCentricEnabled()
0xb339b  brfalse.s loc_B33AD
0xb339d  ldarg.0
0xb339e  callvirt instance valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor Microsoft.Crm.ObjectModel.ConverterBase::get_FormFactor()
0xb33a3  ldc.i4.3
0xb33a4  bne.un.s loc_B33AD
0xb33a6  ldstr    a0_2// "0"
0xb33ab  stloc.s  7
0xb33ad  ldloc.2
0xb33ae  ldloc.s  5
0xb33b0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xb33b5  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb33ba  ldstr    aLabelid// "LabelId"
0xb33bf  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb33c4  brfalse.s loc_B33EA
0xb33c6  ldloc.2
0xb33c7  ldloc.s  5
0xb33c9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xb33ce  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb33d3  ldstr    aLabelid// "LabelId"
0xb33d8  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb33dd  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xb33e2  ldarg.2
0xb33e3  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xb33e8  stloc.s  8
0xb33ea  ldarg.0
0xb33eb  ldloc.0
0xb33ec  ldloc.s  6
0xb33ee  ldarg.2
0xb33ef  ldloca.s 9
0xb33f1  ldloca.s 0xA
0xb33f3  callvirt instance bool Microsoft.Crm.ObjectModel.ListQueryWrapper::TryGetFieldAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, string fieldName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata& attributeMetadata, [out] string& displayName)
0xb33f8  brfalse  loc_B3581
0xb33fd  ldloc.0
0xb33fe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0xb3403  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_LogicalName()
0xb3408  ldstr    aActivitypointe_1// "activitypointer"
0xb340d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb3412  brtrue.s loc_B342B
0xb3414  ldloc.0
0xb3415  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0xb341a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_LogicalName()
0xb341f  ldstr    aEmail// "email"
0xb3424  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb3429  brfalse.s loc_B343C
0xb342b  ldloc.s  6
0xb342d  ldstr    aDescription// "description"
0xb3432  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb3437  brtrue   loc_B3581
0xb343c  ldarg.1
0xb343d  brfalse.s loc_B3485
0xb343f  ldstr    aLabel_0// "Label"
0xb3444  ldloc.s  6
0xb3446  ldnull
0xb3447  ldnull
0xb3448  ldc.i4.2
0xb3449  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor
0xb344e  dup
0xb344f  ldc.i4.0
0xb3450  ldstr    aData// "Data"
0xb3455  ldloc.s  8
0xb3457  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb345c  brtrue.s loc_B3462
0xb345e  ldloc.s  8
0xb3460  br.s     loc_B3464
0xb3462  ldloc.s  0xA
0xb3464  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xb3469  stelem.ref
0xb346a  dup
0xb346b  ldc.i4.1
0xb346c  ldstr    aWidth_0// "Width"
0xb3471  ldloc.s  7
0xb3473  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xb3478  stelem.ref
0xb3479  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.DescriptorBuilder::CreateControlOnlyViewModelDescriptor(string, string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[])
0xb347e  stloc.s  0xB
0xb3480  br       loc_B356D
0xb3485  ldloc.s  9
0xb3487  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata
0xb348c  stloc.s  0xC
0xb348e  ldstr    aLabel_0// "Label"
0xb3493  stloc.s  0xD
0xb3495  ldnull
0xb3496  stloc.s  0xE
0xb3498  ldloc.s  0xC
0xb349a  brfalse.s loc_B34D3
0xb349c  ldloc.s  0xC
0xb349e  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata::get_LookupTypes()
0xb34a3  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::get_Count()
0xb34a8  ldc.i4.0
0xb34a9  ble.s    loc_B34D3
0xb34ab  ldloc.s  0xC
0xb34ad  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0xb34b2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0xb34b7  ldstr    aPartylist// "partylist"
0xb34bc  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb34c1  brtrue.s loc_B34CA
0xb34c3  ldstr    aNavigationbutt// "NavigationButton"
0xb34c8  br.s     loc_B34CF
0xb34ca  ldstr    aPartylistread// "PartyListRead"
0xb34cf  stloc.s  0xD
0xb34d1  br.s     loc_B3541
0xb34d3  ldloc.s  9
0xb34d5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0xb34da  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StringAttributeFormats::get_Phone()
0xb34df  ldc.i4.5
0xb34e0  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xb34e5  brtrue.s loc_B350B
0xb34e7  ldstr    aPhonereadonly// "PhoneReadOnly"
0xb34ec  stloc.s  0xD
0xb34ee  ldc.i4.1
0xb34ef  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor
0xb34f4  stloc.s  0xE
0xb34f6  ldloc.s  0xE
0xb34f8  ldc.i4.0
0xb34f9  ldstr    aCommand_0// "Command"
0xb34fe  ldstr    aSkypeurllaunch// "SkypeUrlLauncherCommand"
0xb3503  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xb3508  stelem.ref
0xb3509  br.s     loc_B3541
0xb350b  ldloc.s  9
0xb350d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0xb3512  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StringAttributeFormats::get_Email()
0xb3517  ldc.i4.5
0xb3518  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xb351d  brtrue.s loc_B3541
0xb351f  ldstr    aEmailreadonly// "EmailReadOnly"
0xb3524  stloc.s  0xD
0xb3526  ldc.i4.1
0xb3527  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor
0xb352c  stloc.s  0xE
0xb352e  ldloc.s  0xE
0xb3530  ldc.i4.0
0xb3531  ldstr    aCommand_0// "Command"
0xb3536  ldstr    aUrllaunchercom// "UrlLauncherCommand"
0xb353b  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xb3540  stelem.ref
0xb3541  ldloc.s  9
0xb3543  call     bool Microsoft.Crm.ObjectModel.AttributeMetadataHelper::IsOptionSet(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata)
0xb3548  brtrue.s loc_B354E
0xb354a  ldloc.s  6
0xb354c  br.s     loc_B355A
0xb354e  ldloc.s  6
0xb3550  ldsfld   string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FieldFormat::Label
0xb3555  call     string [mscorlib]System.String::Concat(string, string)
0xb355a  stloc.s  0xF
0xb355c  ldloc.s  0xD
0xb355e  ldloc.s  6
0xb3560  ldloc.s  0xF
0xb3562  ldloc.s  0xA
0xb3564  ldloc.s  0xE
0xb3566  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.DescriptorBuilder::CreateControlOnlyViewModelDescriptor(string, string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[])
0xb356b  stloc.s  0xB
0xb356d  ldloc.s  0xB
0xb356f  brfalse.s loc_B3581
0xb3571  ldloc.1
0xb3572  ldloc.s  0xB
0xb3574  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0xb3579  ldloc.3
0xb357a  ldloc.s  6
0xb357c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb3581  ldloc.s  5
0xb3583  ldc.i4.1
0xb3584  add
0xb3585  stloc.s  5
0xb3587  ldloc.s  5
0xb3589  ldloc.2
0xb358a  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0xb358f  blt      loc_B3327
0xb3594  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::.ctor()
0xb3599  stloc.s  4
0xb359b  ldarg.0
0xb359c  callvirt instance int32 Microsoft.Crm.ObjectModel.ListQueryWrapper::get_AssociatedEntityType()
0xb35a1  ldc.i4   0x2523
0xb35a6  bne.un.s loc_B35C1
0xb35a8  ldarg.1
0xb35a9  brtrue.s loc_B35C1
0xb35ab  ldloc.s  4
0xb35ad  ldstr    aShortpresscomm// "ShortPressCommandName"
0xb35b2  ldstr    aSharepointdocu_1// "SharepointDocumentLauncherCommand"
0xb35b7  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xb35bc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xb35c1  ldstr    aListitem// "ListItem"
0xb35c6  ldnull
0xb35c7  ldarg.0
0xb35c8  callvirt instance string Microsoft.Crm.ObjectModel.ListQueryWrapper::get_ViewName()
0xb35cd  ldstr    aListItem// "_List Item"
0xb35d2  call     string [mscorlib]System.String::Concat(string, string)
0xb35d7  ldloc.s  4
0xb35d9  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::ToArray()
0xb35de  ldnull
0xb35df  ldloc.1
0xb35e0  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::ToArray()
0xb35e5  ldloc.0
0xb35e6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xb35eb  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::.ctor(string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor[], string)
0xb35f0  ldarg.3
  ... truncated ...
```
