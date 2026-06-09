# Microsoft.Crm.Application.Controls.NavBar::ConfigureHeader

- ea: `0xa34a0`
- end: `0xa499e`
- name: `Microsoft.Crm.Application.Controls.NavBar::ConfigureHeader`
- size: `5374`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x5ff30`
- `0x5ff60`
- `0x5ff70`
- `0xa34a0`
- `0xa49a0`
- `0xa49f0`
- `0xa4a00`
- `0xa4a20`
- `0xa4a70`
- `0xa4aa0`
- `0xa4b70`
- `0xa4c30`
- `0xa4c70`
- `0xa55f0`
- `0xa5810`
- `0xa5c80`
- `0xa5cb0`
- `0xa5d70`

## string_xrefs

- `0xa3518`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0xa34d8`: `/_static/_common/scripts/InlineEditCommon.js`
- `0xa3d3e`: `sitemappath`
- `0xa34f8`: `/_static/_controls/GlobalQuickCreate/GlobalQuickCreateBehavior.js`
- `0xa3820`: `nav_interactive_service_hub`
- `0xa388d`: `nav_servicemanagement`
- `0xa425d`: `HasPrintPrivilege`
- `0xa427c`: `UserHasWritePrivilege`
- `0xa42f9`: `LOCID_CLOSE_GLOBAL_QUICKCREATE`
- `0xa4303`: `RefreshForm_CloseGlobalQuickCreate`
- `0xa4319`: `LOCID_SAVE_GLOBAL_QUICKCREATE`
- `0xa4323`: `QuickCreateSaveButtonText`
- `0xa4339`: `LOCID_CANCEL_GLOBAL_QUICKCREATE`
- `0xa4343`: `QuickCreateCancelButtonText`
- `0xa4359`: `LOCID_TITLE_GLOBAL_QUICKCREATE`
- `0xa4363`: `QuickCreate_TitlePrefix`
- `0xa43e3`: `Web.NavBar.SettingsOpenNavTour_Caption`
- `0xa4443`: `Web.NavBar.SettingsLearningPath_OptIn_Caption`
- `0xa4463`: `Web.NavBar.SettingsLearningPath_OptOut_Caption`
- `0xa4493`: `/Tools/PersonalSettings/cmds/cmd_update.aspx`
- `0xa4603`: `LOCID_QUICKCREATE_VIEWRECORD`
- `0xa4623`: `LOCID_QUICKCREATE_CREATEANOTHER`
- `0xa462d`: `Web.NavBar.QC_CreateAnother`
- `0xa4743`: `LOCID_QUICK_CREATE_DESC`
- `0xa474d`: `Web.NavBar.QuickCreate_Desc`
- `0xa47f0`: `Web.NavBar.QuickCreate_Title`
- `0xa480e`: `globalQuickCreateItems`
- `0xa482e`: `needToFetchQuickCreateItems`
- `0xa48d3`: `navTabButtonSettingsOptionsId`

## pseudocode

```c

```

## disassembly

```asm
0xa34a0  ldarg.0
0xa34a1  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0xa34a6  ldarg.0
0xa34a7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa34ac  ldc.i4.1
0xa34ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0xa34b2  ldarg.0
0xa34b3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa34b8  ldstr    aControlsNavbar// "/_controls/navbar/navbar.css.aspx"
0xa34bd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xa34c2  ldarg.0
0xa34c3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa34c8  ldstr    aControlsRefres// "/_controls/refreshform/flyoutdialog.css"...
0xa34cd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xa34d2  ldarg.0
0xa34d3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa34d8  ldstr    aStaticCommonSc_24// "/_static/_common/scripts/InlineEditComm"...
0xa34dd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xa34e2  ldarg.0
0xa34e3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa34e8  ldstr    aStaticControls_34// "/_static/_controls/inlineedit/InlineEdi"...
0xa34ed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xa34f2  ldarg.0
0xa34f3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa34f8  ldstr    aStaticControls_35// "/_static/_controls/GlobalQuickCreate/Gl"...
0xa34fd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xa3502  ldarg.0
0xa3503  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa3508  ldstr    aStaticControls_36// "/_static/_controls/NavBar/NavBar.js"
0xa350d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xa3512  ldarg.0
0xa3513  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa3518  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/jquery_ui_1.8."...
0xa351d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xa3522  ldarg.0
0xa3523  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa3528  ldstr    aRootGlobalmruA// "/_root/GlobalMRU.aspx?mdts="
0xa352d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa3532  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa3537  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_TimeStamp()
0xa353c  call     string [mscorlib]System.String::Concat(string, string)
0xa3541  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xa3546  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsLive()
0xa354b  brfalse.s loc_A3577
0xa354d  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xa3552  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xa3557  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AppSwitcherShell()
0xa355c  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0xa3561  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa3566  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa356b  brfalse.s loc_A3577
0xa356d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsRestrictedEnvironment()
0xa3572  ldc.i4.0
0xa3573  ceq
0xa3575  br.s     loc_A3578
0xa3577  ldc.i4.0
0xa3578  stloc.0
0xa3579  ldloc.0
0xa357a  brfalse.s loc_A358C
0xa357c  ldarg.0
0xa357d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa3582  ldstr    aStaticControls_37// "/_static/_controls/appswitchershell/app"...
0xa3587  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xa358c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xa3591  stloc.1
0xa3592  ldloc.1
0xa3593  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMap [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMap::GetSiteMapForUser(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser)
0xa3598  stloc.2
0xa3599  ldloc.1
0xa359a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0xa359f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xa35a4  stloc.3
0xa35a5  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::.ctor()
0xa35aa  dup
0xa35ab  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa35b0  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetDefaultLogoText(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa35b5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xa35ba  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::Caption
0xa35bf  dup
0xa35c0  ldstr    a1_0// "1"
0xa35c5  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::Id
0xa35ca  dup
0xa35cb  ldstr    aImgsDefaultima// "_imgs/DefaultImage.gif"
0xa35d0  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::ImageUrl
0xa35d5  dup
0xa35d6  ldstr    asc_F537C// ""
0xa35db  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::ColorAccent
0xa35e0  stloc.s  4
0xa35e2  ldc.i4.0
0xa35e3  stloc.s  5
0xa35e5  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xa35ea  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xa35ef  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_Theme()
0xa35f4  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0xa35f9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa35fe  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa3603  brfalse.s loc_A3608
0xa3605  ldc.i4.1
0xa3606  stloc.s  5
0xa3608  ldloc.2
0xa3609  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapAreaCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMap::get_Areas()
0xa360e  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xa3613  stloc.s  0xC
0xa3615  br       loc_A3C8F
0xa361a  ldloc.s  0xC
0xa361c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa3621  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapArea
0xa3626  stloc.s  0xD
0xa3628  ldloc.s  0xD
0xa362a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Controls.NavBar::AreaImageUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapArea area)
0xa362f  stloc.s  0xE
0xa3631  ldloc.s  0xD
0xa3633  call     string Microsoft.Crm.Application.Controls.NavBar::AreaColorAccent(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapArea area)
0xa3638  stloc.s  0xF
0xa363a  ldloc.s  0xD
0xa363c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_ToolTip()
0xa3641  callvirt instance string [mscorlib]System.String::Trim()
0xa3646  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa364b  brtrue.s loc_A3670
0xa364d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa3652  ldloc.s  0xD
0xa3654  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_ToolTip()
0xa3659  ldc.i4.1
0xa365a  newarr   [mscorlib]System.Object
0xa365f  dup
0xa3660  ldc.i4.0
0xa3661  ldloc.s  0xD
0xa3663  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_Title()
0xa3668  stelem.ref
0xa3669  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa366e  br.s     loc_A3677
0xa3670  ldloc.s  0xD
0xa3672  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_Title()
0xa3677  stloc.s  0x10
0xa3679  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::.ctor()
0xa367e  dup
0xa367f  ldloc.s  0x10
0xa3681  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::ToolTip
0xa3686  dup
0xa3687  ldloc.s  0xD
0xa3689  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_Title()
0xa368e  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::Caption
0xa3693  dup
0xa3694  ldloc.s  0xD
0xa3696  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapArea::get_Id()
0xa369b  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::Id
0xa36a0  dup
0xa36a1  ldloc.s  4
0xa36a3  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::Id
0xa36a8  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::ParentId
0xa36ad  dup
0xa36ae  ldloc.s  0xE
0xa36b0  callvirt instance string [mscorlib]System.Object::ToString()
0xa36b5  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::ImageUrl
0xa36ba  dup
0xa36bb  ldloc.s  0xF
0xa36bd  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::ColorAccent
0xa36c2  dup
0xa36c3  ldloc.s  0xD
0xa36c5  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapArea::get_UpdateBreadcrumb()
0xa36ca  stfld    bool [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::UpdateBreadcrumb
0xa36cf  stloc.s  0x11
0xa36d1  ldloc.s  0xD
0xa36d3  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapGroupCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapArea::get_Groups()
0xa36d8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xa36dd  stloc.s  0x12
0xa36df  br       loc_A3C5E
0xa36e4  ldloc.s  0x12
0xa36e6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa36eb  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapGroup
0xa36f0  stloc.s  0x13
0xa36f2  ldloc.s  0x13
0xa36f4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_ToolTip()
0xa36f9  callvirt instance string [mscorlib]System.String::Trim()
0xa36fe  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa3703  brtrue.s loc_A3728
0xa3705  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa370a  ldloc.s  0x13
0xa370c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_ToolTip()
0xa3711  ldc.i4.1
0xa3712  newarr   [mscorlib]System.Object
0xa3717  dup
0xa3718  ldc.i4.0
0xa3719  ldloc.s  0x13
0xa371b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_Title()
0xa3720  stelem.ref
0xa3721  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa3726  br.s     loc_A372F
0xa3728  ldloc.s  0x13
0xa372a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_Title()
0xa372f  stloc.s  0x14
0xa3731  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::.ctor()
0xa3736  dup
0xa3737  ldloc.s  0x14
0xa3739  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::ToolTip
0xa373e  dup
0xa373f  ldloc.s  0x13
0xa3741  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_Title()
0xa3746  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::Caption
0xa374b  dup
0xa374c  ldloc.s  0x13
0xa374e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapGroup::get_Id()
0xa3753  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::Id
0xa3758  dup
0xa3759  ldloc.s  0xD
0xa375b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapArea::get_Id()
0xa3760  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::ParentId
0xa3765  dup
0xa3766  ldstr    asc_F537C// ""
0xa376b  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::ColorAccent
0xa3770  dup
0xa3771  ldloc.s  0xD
0xa3773  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapArea::get_UpdateBreadcrumb()
0xa3778  stfld    bool [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NavBar.NavigationNode::UpdateBreadcrumb
0xa377d  stloc.s  0x15
0xa377f  ldloc.s  0x13
0xa3781  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubAreaCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapGroup::get_SubAreas()
0xa3786  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xa378b  stloc.s  0x16
0xa378d  br       loc_A3C2D
0xa3792  ldloc.s  0x16
0xa3794  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa3799  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea
0xa379e  stloc.s  0x17
0xa37a0  ldloc.s  0x13
0xa37a2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapGroup::get_Id()
0xa37a7  ldstr    aBusinessSettin// "Business_Setting"
0xa37ac  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa37b1  brfalse.s loc_A37E9
0xa37b3  ldloc.s  0x17
0xa37b5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea::get_Id()
0xa37ba  ldstr    aNavExternappma// "nav_externAppmanagement"
0xa37bf  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa37c4  brfalse.s loc_A37E9
0xa37c6  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xa37cb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xa37d0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OnePartyModel()
0xa37d5  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0xa37da  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa37df  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa37e4  brfalse  loc_A3C2D
0xa37e9  ldloc.s  0x13
0xa37eb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapGroup::get_Id()
0xa37f0  ldstr    aSystemSetting// "System_Setting"
0xa37f5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa37fa  brfalse.s loc_A3819
0xa37fc  ldloc.s  0x17
0xa37fe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea::get_Id()
0xa3803  ldstr    aCrmappOutlook// "crmapp_outlook"
0xa3808  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa380d  brfalse.s loc_A3819
0xa380f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsAppsForCrmSiteMapAllowed()
0xa3814  brfalse  loc_A3C2D
0xa3819  ldloc.s  0x17
0xa381b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea::get_Id()
0xa3820  ldstr    aNavInteractive// "nav_interactive_service_hub"
0xa3825  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa382a  brfalse.s loc_A383D
0xa382c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsUserSysAdminOrCustomizer()
0xa3831  brtrue.s loc_A383D
0xa3833  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsUserCSRManager()
0xa3838  brfalse  loc_A3C2D
0xa383d  ldloc.s  0x17
0xa383f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea::get_Id()
0xa3844  ldstr    aNavAppModules// "nav_app_modules"
0xa3849  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa384e  brfalse.s loc_A3873
0xa3850  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xa3855  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xa385a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AppModuleForOrganization()
0xa385f  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0xa3864  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa3869  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa386e  brfalse  loc_A3C2D
0xa3873  ldloc.s  0x13
0xa3875  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapGroup::get_Id()
0xa387a  ldstr    aBusinessSettin// "Business_Setting"
0xa387f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa3884  brfalse.s loc_A38A3
0xa3886  ldloc.s  0x17
0xa3888  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea::get_Id()
0xa388d  ldstr    aNavServicemana// "nav_servicemanagement"
0xa3892  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa3897  brfalse.s loc_A38A3
0xa3899  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsCRMOrganization()
0xa389e  brfalse  loc_A3C2D
0xa38a3  ldloc.s  0x17
0xa38a5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea::get_DynamicPage()
0xa38aa  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa38af  brfalse  loc_A3C2D
0xa38b4  ldloc.s  0x17
0xa38b6  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea::get_Url()
0xa38bb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_QueryString()
0xa38c0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa38c5  brtrue.s loc_A38E0
0xa38c7  ldloc.s  0x17
0xa38c9  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea::get_Url()
0xa38ce  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_QueryString()
0xa38d3  ldstr    aEtc_1// "etc="
0xa38d8  ldc.i4.5
  ... truncated ...
```
