# Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildRoleMenuBar

- ea: `0x1f2f0`
- end: `0x1f578`
- name: `Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildRoleMenuBar`
- size: `648`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1b610`

## callees

- `0x19fd0`
- `0x1a490`
- `0x1a5d0`
- `0x1c010`
- `0x1f2f0`
- `0x24210`
- `0x242b0`

## string_xrefs

- `0x1f369`: `MenuItem_Label_RemoveRoles`
- `0x1f378`: `RemoveRoles(`
- `0x1f3c8`: `openFormObj('addroles', `
- `0x1f4f4`: `, 'copyrole')`

## pseudocode

```c

```

## disassembly

```asm
0x1f2f0  ldc.i4.2
0x1f2f1  stloc.0
0x1f2f2  ldarg.0
0x1f2f3  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridType
0x1f2f8  stloc.1
0x1f2f9  ldloc.1
0x1f2fa  switch   loc_1F3FA, loc_1F314, loc_1F56E, loc_1F3FA
0x1f30f  br       loc_1F56E
0x1f314  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AssignRole()
0x1f319  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1f31e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f323  brfalse  loc_1F3E7
0x1f328  ldarg.0
0x1f329  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppGridMenuBar::_parentEntityAccessRights
0x1f32e  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanAppendTo()
0x1f333  brfalse  loc_1F3E7
0x1f338  ldarg.0
0x1f339  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x1f33e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x1f343  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x1f348  ldarg.0
0x1f349  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x1f34e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x1f353  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x1f358  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x1f35d  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x1f362  dup
0x1f363  ldarg.0
0x1f364  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1f369  ldstr    aMenuitemLabelR_3// "MenuItem_Label_RemoveRoles"
0x1f36e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f373  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x1f378  ldstr    aRemoveroles// "RemoveRoles("
0x1f37d  ldarg.0
0x1f37e  ldfld    string Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridClientId
0x1f383  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1f388  ldstr    asc_F5C96// ")"
0x1f38d  call     string [mscorlib]System.String::Concat(string, string, string)
0x1f392  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x1f397  ldarg.0
0x1f398  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x1f39d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x1f3a2  ldc.i4.0
0x1f3a3  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x1f3a8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Insert(int32, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x1f3ad  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x1f3b2  dup
0x1f3b3  ldarg.0
0x1f3b4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1f3b9  ldstr    aButtonLabelMan// "Button_Label_ManageRoles"
0x1f3be  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f3c3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x1f3c8  ldstr    aOpenformobjAdd// "openFormObj('addroles', "
0x1f3cd  ldarg.0
0x1f3ce  ldfld    string Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridClientId
0x1f3d3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1f3d8  ldstr    asc_F5C96// ")"
0x1f3dd  call     string [mscorlib]System.String::Concat(string, string, string)
0x1f3e2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x1f3e7  ldarg.0
0x1f3e8  call     instance int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityType()
0x1f3ed  ldc.i4.8
0x1f3ee  bne.un   loc_1F56E
0x1f3f3  ldc.i4.0
0x1f3f4  stloc.0
0x1f3f5  br       loc_1F56E
0x1f3fa  ldarg.0
0x1f3fb  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppGridMenuBar::_parentEntityAccessRights
0x1f400  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanAppendTo()
0x1f405  brtrue.s loc_1F412
0x1f407  ldarg.0
0x1f408  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridType
0x1f40d  brtrue   loc_1F504
0x1f412  ldarg.0
0x1f413  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1f418  ldc.i4.s 0x20
0x1f41a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1f41f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f424  brfalse  loc_1F504
0x1f429  ldarg.0
0x1f42a  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1f42f  ldc.i4.1
0x1f430  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1f435  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f43a  brfalse  loc_1F504
0x1f43f  ldarg.0
0x1f440  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1f445  ldc.i4   0x10000
0x1f44a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1f44f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f454  brfalse  loc_1F504
0x1f459  ldarg.0
0x1f45a  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1f45f  ldc.i4.2
0x1f460  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1f465  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f46a  brfalse  loc_1F504
0x1f46f  ldarg.0
0x1f470  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1f475  ldstr    aStaticBizRoles// "/_static/biz/roles/scripts/actions.js"
0x1f47a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1f47f  ldarg.0
0x1f480  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x1f485  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x1f48a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x1f48f  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x1f494  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x1f499  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x1f49e  dup
0x1f49f  ldarg.0
0x1f4a0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1f4a5  ldstr    aMenuitemLabelC_7// "MenuItem_Label_CloneRole"
0x1f4aa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f4af  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x1f4b4  ldc.i4.5
0x1f4b5  newarr   [mscorlib]System.String
0x1f4ba  dup
0x1f4bb  ldc.i4.0
0x1f4bc  ldstr    aDoaction// "doAction("
0x1f4c1  stelem.ref
0x1f4c2  dup
0x1f4c3  ldc.i4.1
0x1f4c4  ldarg.0
0x1f4c5  ldfld    string Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridClientId
0x1f4ca  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1f4cf  stelem.ref
0x1f4d0  dup
0x1f4d1  ldc.i4.2
0x1f4d2  ldstr    asc_117A44// ", "
0x1f4d7  stelem.ref
0x1f4d8  dup
0x1f4d9  ldc.i4.3
0x1f4da  ldc.i4   0x40C
0x1f4df  stloc.2
0x1f4e0  ldloca.s 2
0x1f4e2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f4e7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1f4ec  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1f4f1  stelem.ref
0x1f4f2  dup
0x1f4f3  ldc.i4.4
0x1f4f4  ldstr    aCopyrole// ", 'copyrole')"
0x1f4f9  stelem.ref
0x1f4fa  call     string [mscorlib]System.String::Concat(string[])
0x1f4ff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x1f504  ldarg.0
0x1f505  ldc.i4.7
0x1f506  newarr   [mscorlib]System.String
0x1f50b  dup
0x1f50c  ldc.i4.0
0x1f50d  ldstr    aLocaddrelatedt// "locAddRelatedToNonForm("
0x1f512  stelem.ref
0x1f513  dup
0x1f514  ldc.i4.1
0x1f515  ldc.i4   0x40C
0x1f51a  stloc.2
0x1f51b  ldloca.s 2
0x1f51d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f522  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1f527  stelem.ref
0x1f528  dup
0x1f529  ldc.i4.2
0x1f52a  ldstr    asc_11387C// ","
0x1f52f  stelem.ref
0x1f530  dup
0x1f531  ldc.i4.3
0x1f532  ldc.i4.s 0xA
0x1f534  stloc.2
0x1f535  ldloca.s 2
0x1f537  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f53c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1f541  stelem.ref
0x1f542  dup
0x1f543  ldc.i4.4
0x1f544  ldstr    asc_11AA82// ",'"
0x1f549  stelem.ref
0x1f54a  dup
0x1f54b  ldc.i4.5
0x1f54c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x1f551  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_BusinessId()
0x1f556  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x1f55b  stelem.ref
0x1f55c  dup
0x1f55d  ldc.i4.6
0x1f55e  ldstr    asc_11AA88// "', '')"
0x1f563  stelem.ref
0x1f564  call     string [mscorlib]System.String::Concat(string[])
0x1f569  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton(string onclickScript)
0x1f56e  ldarg.0
0x1f56f  ldloc.0
0x1f570  ldc.i4.0
0x1f571  ldc.i4.1
0x1f572  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport)
0x1f577  ret
```
