# Microsoft.Crm.Application.Controls.NavBar::BuildQuickCreateActivities

- ea: `0xa52a0`
- end: `0xa5591`
- name: `Microsoft.Crm.Application.Controls.NavBar::BuildQuickCreateActivities`
- size: `753`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x46e50`
- `0xa4c30`
- `0xa4c70`
- `0xa4ed0`
- `0xa5210`
- `0xa52a0`
- `0xa55a0`
- `0xa57f0`

## string_xrefs

- `0xa52ad`: `Task_32.png`
- `0xa544e`: `GlobalQuickCreateAction`
- `0xa5548`: `GlobalQuickCreateAction`

## pseudocode

```c

```

## disassembly

```asm
0xa52a0  ldc.i4.4
0xa52a1  newarr   class [mscorlib]System.Tuple`2<int32, string>
0xa52a6  dup
0xa52a7  ldc.i4.0
0xa52a8  ldc.i4   0x1074
0xa52ad  ldstr    aTask32Png// "Task_32.png"
0xa52b2  newobj   instance void class [mscorlib]System.Tuple`2<int32, string>::.ctor(var<u1>, !!T0)
0xa52b7  stelem.ref
0xa52b8  dup
0xa52b9  ldc.i4.1
0xa52ba  ldc.i4   0x1072
0xa52bf  ldstr    aPhonecall32Png// "PhoneCall_32.png"
0xa52c4  newobj   instance void class [mscorlib]System.Tuple`2<int32, string>::.ctor(var<u1>, !!T0)
0xa52c9  stelem.ref
0xa52ca  dup
0xa52cb  ldc.i4.2
0xa52cc  ldc.i4   0x106A
0xa52d1  ldstr    aEmail32Png// "Email_32.png"
0xa52d6  newobj   instance void class [mscorlib]System.Tuple`2<int32, string>::.ctor(var<u1>, !!T0)
0xa52db  stelem.ref
0xa52dc  dup
0xa52dd  ldc.i4.3
0xa52de  ldc.i4   0x1069
0xa52e3  ldstr    aAppointment32P// "Appointment_32.png"
0xa52e8  newobj   instance void class [mscorlib]System.Tuple`2<int32, string>::.ctor(var<u1>, !!T0)
0xa52ed  stelem.ref
0xa52ee  stloc.0
0xa52ef  call     class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::get_CustomActivitiesByName()
0xa52f4  stloc.1
0xa52f5  ldloc.0
0xa52f6  ldlen
0xa52f7  conv.i4
0xa52f8  ldloc.1
0xa52f9  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Count()
0xa52fe  add
0xa52ff  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode>::.ctor(int32)
0xa5304  stloc.2
0xa5305  ldsfld   string [mscorlib]System.String::Empty
0xa530a  stloc.3
0xa530b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xa5310  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xa5315  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_Theme()
0xa531a  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0xa531f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa5324  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa5329  stloc.s  4
0xa532b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa5330  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa5335  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_CurrentAppId()
0xa533a  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility::IsAppContext(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, valuetype [mscorlib]System.Guid)
0xa533f  stloc.s  5
0xa5341  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0xa5346  stloc.s  6
0xa5348  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0xa534d  stloc.s  7
0xa534f  ldloc.s  5
0xa5351  brfalse.s loc_A5364
0xa5353  ldarg.0
0xa5354  ldloc.0
0xa5355  call     class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Application.Controls.NavBar::FilterDefaultActivitiesGuids(class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext org, class [mscorlib]System.Tuple`2<int32, string>[] defaultActivities)
0xa535a  stloc.s  6
0xa535c  ldloc.1
0xa535d  call     class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Application.Controls.NavBar::FilterCustomActivitiesGuids(class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata> entities)
0xa5362  stloc.s  7
0xa5364  ldloc.0
0xa5365  stloc.s  8
0xa5367  ldc.i4.0
0xa5368  stloc.s  9
0xa536a  br       loc_A5481
0xa536f  ldloc.s  8
0xa5371  ldloc.s  9
0xa5373  ldelem.ref
0xa5374  stloc.s  0xA
0xa5376  ldarg.0
0xa5377  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa537c  ldloc.s  0xA
0xa537e  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, string>::get_Item1()
0xa5383  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xa5388  stloc.s  0xB
0xa538a  ldloc.s  5
0xa538c  brfalse.s loc_A53A6
0xa538e  ldloc.s  6
0xa5390  ldloc.s  0xB
0xa5392  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0xa5397  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_EntityId()
0xa539c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0xa53a1  brfalse  loc_A547B
0xa53a6  ldloc.s  0xB
0xa53a8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0xa53ad  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_LogicalName()
0xa53b2  ldc.i4.0
0xa53b3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa53b8  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa53bd  brfalse  loc_A547B
0xa53c2  ldloc.s  4
0xa53c4  brfalse.s loc_A53DA
0xa53c6  ldloc.s  0xA
0xa53c8  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, string>::get_Item1()
0xa53cd  ldc.i4.0
0xa53ce  ldc.i4.0
0xa53cf  ldloc.s  4
0xa53d1  ldarg.1
0xa53d2  call     string Microsoft.Crm.Application.Controls.NavBar::EntityColor(int32 entityTypeCode, bool isCustomEntity, bool isDashboard, bool isThemeFeatureEnabled, class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> colorDictionary)
0xa53d7  stloc.3
0xa53d8  br.s     loc_A53E0
0xa53da  ldstr    aAbb4c2// "#ABB4C2"
0xa53df  stloc.3
0xa53e0  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::.ctor()
0xa53e5  dup
0xa53e6  ldarg.0
0xa53e7  ldloc.s  0xA
0xa53e9  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, string>::get_Item1()
0xa53ee  call     string Microsoft.Crm.Application.Controls.NavBar::GetEntityDisplayName(class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext org, int32 etc)
0xa53f3  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::Caption
0xa53f8  dup
0xa53f9  ldloc.s  0xA
0xa53fb  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, string>::get_Item1()
0xa5400  stloc.s  0xD
0xa5402  ldloca.s 0xD
0xa5404  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa5409  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa540e  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::Id
0xa5413  dup
0xa5414  ldstr    aImgsNavbarActi// "/_imgs/NavBar/ActionImgs/"
0xa5419  ldloc.s  0xA
0xa541b  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, string>::get_Item2()
0xa5420  call     string [mscorlib]System.String::Concat(string, string)
0xa5425  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa542a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa542f  callvirt instance string [mscorlib]System.Object::ToString()
0xa5434  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::ImageUrl
0xa5439  dup
0xa543a  ldloc.3
0xa543b  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::ColorAccent
0xa5440  dup
0xa5441  ldc.i4.2
0xa5442  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNodeType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::NodeType
0xa5447  dup
0xa5448  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationAction::.ctor()
0xa544d  dup
0xa544e  ldstr    aGlobalquickcre_0// "GlobalQuickCreateAction"
0xa5453  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationAction::ActionType
0xa5458  dup
0xa5459  ldloc.s  0xA
0xa545b  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, string>::get_Item1()
0xa5460  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationAction::EntityTypeCode
0xa5465  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationAction [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::Action
0xa546a  stloc.s  0xC
0xa546c  ldloc.s  0xC
0xa546e  call     void Microsoft.Crm.Application.Controls.NavBar::SetStripeImage(class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode node)
0xa5473  ldloc.2
0xa5474  ldloc.s  0xC
0xa5476  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode>::Add(var<u1>)
0xa547b  ldloc.s  9
0xa547d  ldc.i4.1
0xa547e  add
0xa547f  stloc.s  9
0xa5481  ldloc.s  9
0xa5483  ldloc.s  8
0xa5485  ldlen
0xa5486  conv.i4
0xa5487  blt      loc_A536F
0xa548c  ldloc.1
0xa548d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::GetEnumerator()
0xa5492  stloc.s  0xE
0xa5494  br       loc_A5575
0xa5499  ldloc.s  0xE
0xa549b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Current()
0xa54a0  stloc.s  0xF
0xa54a2  ldloc.s  5
0xa54a4  brfalse.s loc_A54BE
0xa54a6  ldloc.s  7
0xa54a8  ldloc.s  0xF
0xa54aa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0xa54af  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_EntityId()
0xa54b4  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0xa54b9  brfalse  loc_A5575
0xa54be  ldloc.s  0xF
0xa54c0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsQuickCreateEnabled()
0xa54c5  brfalse  loc_A5575
0xa54ca  ldloc.s  0xF
0xa54cc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0xa54d1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_LogicalName()
0xa54d6  ldc.i4.0
0xa54d7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa54dc  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa54e1  brfalse  loc_A5575
0xa54e6  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::.ctor()
0xa54eb  dup
0xa54ec  ldloc.s  0xF
0xa54ee  ldc.i4.1
0xa54ef  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0xa54f4  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::Caption
0xa54f9  dup
0xa54fa  ldloc.s  0xF
0xa54fc  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xa5501  stloc.s  9
0xa5503  ldloca.s 9
0xa5505  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa550a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa550f  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::Id
0xa5514  dup
0xa5515  ldloc.s  0xF
0xa5517  ldc.i4.6
0xa5518  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconWebResourceName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType)
0xa551d  ldloc.s  0xF
0xa551f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0xa5524  ldloc.s  0xF
0xa5526  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsBPFEntity()
0xa552b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Controls.NavBar::GetCustomEntityIconWebResourceUri(string webResourceName, [opt] bool isActivity, [opt] bool isBPFEntity)
0xa5530  callvirt instance string [mscorlib]System.Object::ToString()
0xa5535  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::ImageUrl
0xa553a  dup
0xa553b  ldc.i4.2
0xa553c  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNodeType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::NodeType
0xa5541  dup
0xa5542  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationAction::.ctor()
0xa5547  dup
0xa5548  ldstr    aGlobalquickcre_0// "GlobalQuickCreateAction"
0xa554d  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationAction::ActionType
0xa5552  dup
0xa5553  ldloc.s  0xF
0xa5555  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xa555a  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationAction::EntityTypeCode
0xa555f  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationAction [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::Action
0xa5564  stloc.s  0x10
0xa5566  ldloc.s  0x10
0xa5568  call     void Microsoft.Crm.Application.Controls.NavBar::SetStripeImage(class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode node)
0xa556d  ldloc.2
0xa556e  ldloc.s  0x10
0xa5570  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode>::Add(var<u1>)
0xa5575  ldloc.s  0xE
0xa5577  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa557c  brtrue   loc_A5499
0xa5581  leave.s  loc_A558F
0xa5583  ldloc.s  0xE
0xa5585  brfalse.s loc_A558E
0xa5587  ldloc.s  0xE
0xa5589  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa558e  endfinally
0xa558f  ldloc.2
0xa5590  ret
```
