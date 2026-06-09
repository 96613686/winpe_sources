# Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildResourceMenuBar

- ea: `0x1ec20`
- end: `0x1ef5f`
- name: `Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildResourceMenuBar`
- size: `831`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1b610`

## callees

- `0x19fd0`
- `0x1a510`
- `0x1a5d0`
- `0x1a5e0`
- `0x1a600`
- `0x1ae30`
- `0x1c010`
- `0x1ec20`
- `0x24210`

## string_xrefs

- `0x1edeb`: `RemoveMembers(`
- `0x1ecfc`: `MenuItem_Label_RemoveResources`
- `0x1ed0c`: `RemoveItems(`
- `0x1ed2b`: `mnuRemove`
- `0x1eddc`: `MenuItem_Label_RemoveSiteMembers`

## pseudocode

```c

```

## disassembly

```asm
0x1ec20  ldarg.0
0x1ec21  ldfld    string Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridViewId
0x1ec26  ldstr    aB5ca46bdEf0c48// "{B5CA46BD-EF0C-48A2-8211-5777BC0FEADD}"
0x1ec2b  ldc.i4.5
0x1ec2c  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1ec31  brtrue   loc_1ED3A
0x1ec36  ldc.i4   0xFA2
0x1ec3b  ldc.i4.s 0x20
0x1ec3d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ec42  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ec47  brfalse  loc_1EF55
0x1ec4c  ldc.i4.0
0x1ec4d  stloc.0
0x1ec4e  ldc.i4.1
0x1ec4f  newarr   [mscorlib]System.String
0x1ec54  dup
0x1ec55  ldc.i4.0
0x1ec56  ldstr    aGrouptypecode// "grouptypecode"
0x1ec5b  stelem.ref
0x1ec5c  stloc.1
0x1ec5d  ldstr    aConstraintbase// "constraintbasedgroup"
0x1ec62  ldarg.0
0x1ec63  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityId()
0x1ec68  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1ec6d  ldloc.1
0x1ec6e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ec73  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ec78  stloc.2
0x1ec79  ldloc.2
0x1ec7a  ldstr    aGrouptypecode// "grouptypecode"
0x1ec7f  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1ec84  brfalse.s loc_1EC9A
0x1ec86  ldloc.2
0x1ec87  ldstr    aGrouptypecode// "grouptypecode"
0x1ec8c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1ec91  unbox.any [mscorlib]System.Int32
0x1ec96  brtrue.s loc_1EC9A
0x1ec98  ldc.i4.1
0x1ec99  stloc.0
0x1ec9a  ldloc.0
0x1ec9b  brfalse  loc_1EF55
0x1eca0  ldarg.0
0x1eca1  ldstr    aModifyitemsNul// "ModifyItems(null, "
0x1eca6  ldarg.0
0x1eca7  ldfld    string Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridClientId
0x1ecac  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1ecb1  ldstr    aOidActionAdd// ", _oId, ACTION_ADD)"
0x1ecb6  call     string [mscorlib]System.String::Concat(string, string, string)
0x1ecbb  ldarg.0
0x1ecbc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1ecc1  ldstr    aButtonLabelAdd// "Button_Label_AddMembers"
0x1ecc6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1eccb  ldnull
0x1eccc  ldstr    aMnunew// "mnuNew"
0x1ecd1  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton(string onclickScript, string buttonTitle, string buttonTip, string id)
0x1ecd6  ldarg.0
0x1ecd7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x1ecdc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x1ece1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x1ece6  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x1eceb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x1ecf0  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x1ecf5  dup
0x1ecf6  ldarg.0
0x1ecf7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1ecfc  ldstr    aMenuitemLabelR_1// "MenuItem_Label_RemoveResources"
0x1ed01  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1ed06  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x1ed0b  dup
0x1ed0c  ldstr    aRemoveitems// "RemoveItems("
0x1ed11  ldarg.0
0x1ed12  ldfld    string Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridClientId
0x1ed17  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1ed1c  ldstr    aOid_2// ", _oId)"
0x1ed21  call     string [mscorlib]System.String::Concat(string, string, string)
0x1ed26  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x1ed2b  ldstr    aMnuremove// "mnuRemove"
0x1ed30  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1ed35  br       loc_1EF55
0x1ed3a  ldarg.0
0x1ed3b  ldfld    string Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridViewId
0x1ed40  ldstr    a43997469F8f04a// "{43997469-F8F0-4ABD-87EE-2194F731A6B2}"
0x1ed45  ldc.i4.5
0x1ed46  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1ed4b  brtrue   loc_1EE0F
0x1ed50  ldc.i4.8
0x1ed51  ldc.i4.2
0x1ed52  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ed57  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ed5c  brtrue.s loc_1ED73
0x1ed5e  ldc.i4   0xFA0
0x1ed63  ldc.i4.2
0x1ed64  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ed69  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ed6e  brfalse  loc_1EF55
0x1ed73  ldc.i4   0xFA9
0x1ed78  ldc.i4.s 0x10
0x1ed7a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ed7f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ed84  brfalse.s loc_1EDB6
0x1ed86  ldarg.0
0x1ed87  ldstr    aAddmembers// "AddMembers("
0x1ed8c  ldarg.0
0x1ed8d  ldfld    string Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridClientId
0x1ed92  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1ed97  ldstr    aOid_2// ", _oId)"
0x1ed9c  call     string [mscorlib]System.String::Concat(string, string, string)
0x1eda1  ldarg.0
0x1eda2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1eda7  ldstr    aButtonLabelAdd_0// "Button_Label_AddSiteMembers"
0x1edac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1edb1  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton(string onclickScript, string buttonTitle)
0x1edb6  ldarg.0
0x1edb7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x1edbc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x1edc1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x1edc6  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x1edcb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x1edd0  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x1edd5  dup
0x1edd6  ldarg.0
0x1edd7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1eddc  ldstr    aMenuitemLabelR_2// "MenuItem_Label_RemoveSiteMembers"
0x1ede1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1ede6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x1edeb  ldstr    aRemovemembers// "RemoveMembers("
0x1edf0  ldarg.0
0x1edf1  ldfld    string Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridClientId
0x1edf6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1edfb  ldstr    aOid_2// ", _oId)"
0x1ee00  call     string [mscorlib]System.String::Concat(string, string, string)
0x1ee05  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x1ee0a  br       loc_1EF55
0x1ee0f  ldarg.0
0x1ee10  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1ee15  ldc.i4   0x10000
0x1ee1a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ee1f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ee24  brfalse.s loc_1EE3D
0x1ee26  ldarg.0
0x1ee27  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddDeleteButton()
0x1ee2c  pop
0x1ee2d  ldarg.0
0x1ee2e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x1ee33  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x1ee38  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x1ee3d  ldarg.0
0x1ee3e  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1ee43  ldc.i4.2
0x1ee44  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ee49  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ee4e  brfalse  loc_1EED8
0x1ee53  ldarg.0
0x1ee54  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x1ee59  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x1ee5e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x1ee63  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x1ee68  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x1ee6d  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x1ee72  dup
0x1ee73  ldarg.0
0x1ee74  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1ee79  ldstr    aMenuitemLabelC_5// "MenuItem_Label_ChangeBusiness"
0x1ee7e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1ee83  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x1ee88  ldc.i4.5
0x1ee89  newarr   [mscorlib]System.String
0x1ee8e  dup
0x1ee8f  ldc.i4.0
0x1ee90  ldstr    aDoaction// "doAction("
0x1ee95  stelem.ref
0x1ee96  dup
0x1ee97  ldc.i4.1
0x1ee98  ldarg.0
0x1ee99  ldfld    string Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridClientId
0x1ee9e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1eea3  stelem.ref
0x1eea4  dup
0x1eea5  ldc.i4.2
0x1eea6  ldstr    asc_117A44// ", "
0x1eeab  stelem.ref
0x1eeac  dup
0x1eead  ldc.i4.3
0x1eeae  ldc.i4   0xFA0
0x1eeb3  stloc.3
0x1eeb4  ldloca.s 3
0x1eeb6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1eebb  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1eec0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1eec5  stelem.ref
0x1eec6  dup
0x1eec7  ldc.i4.4
0x1eec8  ldstr    aChangeorg_0// ", 'changeorg')"
0x1eecd  stelem.ref
0x1eece  call     string [mscorlib]System.String::Concat(string[])
0x1eed3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x1eed8  ldc.i4   0xFA2
0x1eedd  ldc.i4.s 0x20
0x1eedf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1eee4  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1eee9  brfalse.s loc_1EF55
0x1eeeb  ldarg.0
0x1eeec  ldc.i4.7
0x1eeed  newarr   [mscorlib]System.String
0x1eef2  dup
0x1eef3  ldc.i4.0
0x1eef4  ldstr    aLocaddrelatedt// "locAddRelatedToNonForm("
0x1eef9  stelem.ref
0x1eefa  dup
0x1eefb  ldc.i4.1
0x1eefc  ldc.i4   0xFA2
0x1ef01  stloc.3
0x1ef02  ldloca.s 3
0x1ef04  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ef09  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1ef0e  stelem.ref
0x1ef0f  dup
0x1ef10  ldc.i4.2
0x1ef11  ldstr    asc_11387C// ","
0x1ef16  stelem.ref
0x1ef17  dup
0x1ef18  ldc.i4.3
0x1ef19  ldc.i4.s 0xA
0x1ef1b  stloc.3
0x1ef1c  ldloca.s 3
0x1ef1e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ef23  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1ef28  stelem.ref
0x1ef29  dup
0x1ef2a  ldc.i4.4
0x1ef2b  ldstr    asc_11AA82// ",'"
0x1ef30  stelem.ref
0x1ef31  dup
0x1ef32  ldc.i4.5
0x1ef33  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x1ef38  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_BusinessId()
0x1ef3d  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x1ef42  stelem.ref
0x1ef43  dup
0x1ef44  ldc.i4.6
0x1ef45  ldstr    asc_11AA88// "', '')"
0x1ef4a  stelem.ref
0x1ef4b  call     string [mscorlib]System.String::Concat(string[])
0x1ef50  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton(string onclickScript)
0x1ef55  ldarg.0
0x1ef56  ldc.i4.0
0x1ef57  ldc.i4.0
0x1ef58  ldc.i4.1
0x1ef59  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport)
0x1ef5e  ret
```
