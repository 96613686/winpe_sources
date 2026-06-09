# Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildTeamMenuBar

- ea: `0x1f810`
- end: `0x1fc2b`
- name: `Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildTeamMenuBar`
- size: `1051`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1b610`

## callees

- `0x19fd0`
- `0x1a490`
- `0x1a510`
- `0x1a5d0`
- `0x1a5e0`
- `0x1a5f0`
- `0x1b380`
- `0x1b410`
- `0x1b510`
- `0x1c010`
- `0x1c060`
- `0x1f810`
- `0x1fff0`
- `0x24210`

## string_xrefs

- `0x1fa49`: `MenuItem_Label_RemoveMembers`
- `0x1fb17`: `MenuItem_Label_RemoveMembers`
- `0x1f8dd`: `MenuItem_Label_RemoveFromTeam`
- `0x1f8ec`: `RemoveTeam(`
- `0x1f95a`: `Menu_Label_AddTeamsFromFieldSecurityProfile`
- `0x1f96a`: `Menu_Label_Tooltip_AddTeamsFromFieldSecurityProfile`
- `0x1f985`: `Menu_Label_RemoveTeams`
- `0x1f98f`: `/_imgs/ico_16_removeteam.png`
- `0x1fa53`: `removefromteam`
- `0x1fb21`: `removefromteam`

## pseudocode

```c

```

## disassembly

```asm
0x1f810  ldc.i4.0
0x1f811  stloc.0
0x1f812  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateTeam()
0x1f817  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1f81c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f821  brfalse  loc_1FC0E
0x1f826  ldarg.0
0x1f827  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppGridMenuBar::_parentEntityAccessRights
0x1f82c  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanAppendTo()
0x1f831  brfalse  loc_1FC0E
0x1f836  ldarg.0
0x1f837  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridType
0x1f83c  stloc.1
0x1f83d  ldloc.1
0x1f83e  switch   loc_1FAE0, loc_1F858, loc_1FBFF, loc_1FAE0
0x1f853  br       loc_1FBFF
0x1f858  ldarg.0
0x1f859  call     instance int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityType()
0x1f85e  stloc.2
0x1f85f  ldloc.2
0x1f860  ldc.i4.8
0x1f861  beq.s    loc_1F873
0x1f863  ldloc.2
0x1f864  ldc.i4   0x4B0
0x1f869  beq      loc_1F910
0x1f86e  br       loc_1FA15
0x1f873  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteTeam()
0x1f878  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1f87d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f882  brfalse  loc_1FBFF
0x1f887  ldarg.0
0x1f888  ldstr    aModifymembersh// "ModifyMembership(null, "
0x1f88d  ldarg.0
0x1f88e  ldfld    string Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridClientId
0x1f893  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1f898  ldstr    aOidActionAddTe// ", _oId, ACTION_ADD, Team, '&filterdefau"...
0x1f89d  call     string [mscorlib]System.String::Concat(string, string, string)
0x1f8a2  ldarg.0
0x1f8a3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1f8a8  ldstr    aButtonLabelJoi_0// "Button_Label_JoinTeam"
0x1f8ad  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f8b2  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton(string onclickScript, string buttonTitle)
0x1f8b7  ldarg.0
0x1f8b8  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x1f8bd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x1f8c2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x1f8c7  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x1f8cc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x1f8d1  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x1f8d6  dup
0x1f8d7  ldarg.0
0x1f8d8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1f8dd  ldstr    aMenuitemLabelR_4// "MenuItem_Label_RemoveFromTeam"
0x1f8e2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f8e7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x1f8ec  ldstr    aRemoveteam// "RemoveTeam("
0x1f8f1  ldarg.0
0x1f8f2  ldfld    string Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridClientId
0x1f8f7  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1f8fc  ldstr    asc_F5C96// ")"
0x1f901  call     string [mscorlib]System.String::Concat(string, string, string)
0x1f906  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x1f90b  br       loc_1FBFF
0x1f910  ldarg.0
0x1f911  ldc.i4.5
0x1f912  newarr   [mscorlib]System.String
0x1f917  dup
0x1f918  ldc.i4.0
0x1f919  ldstr    aRunfunctionfro_2// "RunFunctionFromParentOrSelf('locAssocOb"...
0x1f91e  stelem.ref
0x1f91f  dup
0x1f920  ldc.i4.1
0x1f921  ldarg.0
0x1f922  ldflda   int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1f927  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f92c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1f931  stelem.ref
0x1f932  dup
0x1f933  ldc.i4.2
0x1f934  ldstr    asc_117ADC// ",'',"
0x1f939  stelem.ref
0x1f93a  dup
0x1f93b  ldc.i4.3
0x1f93c  ldstr    aTeamprofilesAs// "teamprofiles_association"
0x1f941  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1f946  stelem.ref
0x1f947  dup
0x1f948  ldc.i4.4
0x1f949  ldstr    a2// ", 2);"
0x1f94e  stelem.ref
0x1f94f  call     string [mscorlib]System.String::Concat(string[])
0x1f954  ldarg.0
0x1f955  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1f95a  ldstr    aMenuLabelAddte// "Menu_Label_AddTeamsFromFieldSecurityPro"...
0x1f95f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f964  ldarg.0
0x1f965  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1f96a  ldstr    aMenuLabelToolt_0// "Menu_Label_Tooltip_AddTeamsFromFieldSec"...
0x1f96f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f974  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton(string onclickScript, string buttonTitle, string buttonTip)
0x1f979  ldarg.0
0x1f97a  ldstr    asc_F537C// ""
0x1f97f  ldarg.0
0x1f980  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1f985  ldstr    aMenuLabelRemov_0// "Menu_Label_RemoveTeams"
0x1f98a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f98f  ldstr    aImgsIco16Remov_0// "/_imgs/ico_16_removeteam.png"
0x1f994  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1f999  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f99e  ldstr    aDisassociate// "disassociate"
0x1f9a3  ldstr    aWindowParentGe// "window.parent.$get('crmFormSubmit').crm"...
0x1f9a8  ldstr    aWindowParentGe_0// "window.parent.$get('crmFormSubmit').crm"...
0x1f9ad  ldc.i4.2
0x1f9ae  newarr   [mscorlib]System.String
0x1f9b3  dup
0x1f9b4  ldc.i4.0
0x1f9b5  ldstr    aAssociationnam// "associationName"
0x1f9ba  stelem.ref
0x1f9bb  dup
0x1f9bc  ldc.i4.1
0x1f9bd  ldstr    aRoleord// "roleOrd"
0x1f9c2  stelem.ref
0x1f9c3  ldc.i4.2
0x1f9c4  newarr   [mscorlib]System.String
0x1f9c9  dup
0x1f9ca  ldc.i4.0
0x1f9cb  ldarg.0
0x1f9cc  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Menus.AppGridMenuBar::_grid
0x1f9d1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x1f9d6  ldstr    aRelname// "relName"
0x1f9db  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1f9e0  stelem.ref
0x1f9e1  dup
0x1f9e2  ldc.i4.1
0x1f9e3  ldarg.0
0x1f9e4  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Menus.AppGridMenuBar::_grid
0x1f9e9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x1f9ee  ldstr    aRoleord// "roleOrd"
0x1f9f3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1f9f8  stelem.ref
0x1f9f9  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddButtonDoActionEx(string name, string tooltip, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri icon, string action, string parentId, string parentType, string[] queryStringParameters, string[] queryStringValues)
0x1f9fe  ldarg.0
0x1f9ff  ldc.i4   0x400
0x1fa04  ldc.i4.0
0x1fa05  ldc.i4.1
0x1fa06  ldc.i4.1
0x1fa07  ldc.i4.0
0x1fa08  ldc.i4.0
0x1fa09  ldc.i4.0
0x1fa0a  ldc.i4.0
0x1fa0b  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport, bool buttonPrint, bool buttonReports, bool actionDeDupe, bool actionConnection, bool actionWorkflow)
0x1fa10  br       loc_1FBFF
0x1fa15  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteTeam()
0x1fa1a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1fa1f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1fa24  brfalse.s loc_1FA5E
0x1fa26  ldarg.0
0x1fa27  ldarg.0
0x1fa28  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1fa2d  ldstr    aMenuLabelAddme// "Menu_Label_AddMembers"
0x1fa32  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fa37  ldstr    aAddtoteam// "addtoteam"
0x1fa3c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x1fa41  pop
0x1fa42  ldarg.0
0x1fa43  ldarg.0
0x1fa44  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1fa49  ldstr    aMenuitemLabelR_0// "MenuItem_Label_RemoveMembers"
0x1fa4e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fa53  ldstr    aRemovefromteam// "removefromteam"
0x1fa58  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x1fa5d  pop
0x1fa5e  ldloc.2
0x1fa5f  ldc.i4.s 0xA
0x1fa61  beq.s    loc_1FA74
0x1fa63  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x1fa68  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_BusinessId()
0x1fa6d  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x1fa72  br.s     loc_1FA7A
0x1fa74  ldarg.0
0x1fa75  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityId()
0x1fa7a  stloc.3
0x1fa7b  ldarg.0
0x1fa7c  ldc.i4.7
0x1fa7d  newarr   [mscorlib]System.String
0x1fa82  dup
0x1fa83  ldc.i4.0
0x1fa84  ldstr    aLocaddrelatedt// "locAddRelatedToNonForm("
0x1fa89  stelem.ref
0x1fa8a  dup
0x1fa8b  ldc.i4.1
0x1fa8c  ldc.i4.s 9
0x1fa8e  stloc.s  4
0x1fa90  ldloca.s 4
0x1fa92  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1fa97  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1fa9c  stelem.ref
0x1fa9d  dup
0x1fa9e  ldc.i4.2
0x1fa9f  ldstr    asc_11387C// ","
0x1faa4  stelem.ref
0x1faa5  dup
0x1faa6  ldc.i4.3
0x1faa7  ldc.i4.s 0xA
0x1faa9  stloc.s  4
0x1faab  ldloca.s 4
0x1faad  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1fab2  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1fab7  stelem.ref
0x1fab8  dup
0x1fab9  ldc.i4.4
0x1faba  ldstr    asc_11387C// ","
0x1fabf  stelem.ref
0x1fac0  dup
0x1fac1  ldc.i4.5
0x1fac2  ldloc.3
0x1fac3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1fac8  stelem.ref
0x1fac9  dup
0x1faca  ldc.i4.6
0x1facb  ldstr    asc_117846// ", '')"
0x1fad0  stelem.ref
0x1fad1  call     string [mscorlib]System.String::Concat(string[])
0x1fad6  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton(string onclickScript)
0x1fadb  br       loc_1FBFF
0x1fae0  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteTeam()
0x1fae5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1faea  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1faef  brfalse  loc_1FB92
0x1faf4  ldarg.0
0x1faf5  ldarg.0
0x1faf6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1fafb  ldstr    aMenuLabelAddme// "Menu_Label_AddMembers"
0x1fb00  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fb05  ldstr    aAddtoteam// "addtoteam"
0x1fb0a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x1fb0f  pop
0x1fb10  ldarg.0
0x1fb11  ldarg.0
0x1fb12  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1fb17  ldstr    aMenuitemLabelR_0// "MenuItem_Label_RemoveMembers"
0x1fb1c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fb21  ldstr    aRemovefromteam// "removefromteam"
0x1fb26  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x1fb2b  pop
0x1fb2c  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AssignRole()
0x1fb31  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1fb36  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1fb3b  brfalse.s loc_1FB92
0x1fb3d  ldarg.0
0x1fb3e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x1fb43  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x1fb48  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x1fb4d  ldarg.0
0x1fb4e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x1fb53  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x1fb58  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x1fb5d  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x1fb62  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x1fb67  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x1fb6c  dup
0x1fb6d  ldarg.0
0x1fb6e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1fb73  ldstr    aMenuitemManage// "MenuItem_Manage_Roles"
0x1fb78  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fb7d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x1fb82  ldarg.0
0x1fb83  ldstr    aRole// "role"
0x1fb88  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildDoActionScript(string action)
0x1fb8d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x1fb92  ldarg.0
0x1fb93  ldc.i4.7
0x1fb94  newarr   [mscorlib]System.String
0x1fb99  dup
0x1fb9a  ldc.i4.0
0x1fb9b  ldstr    aLocaddrelatedt// "locAddRelatedToNonForm("
0x1fba0  stelem.ref
0x1fba1  dup
0x1fba2  ldc.i4.1
0x1fba3  ldc.i4.s 9
0x1fba5  stloc.s  4
0x1fba7  ldloca.s 4
0x1fba9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1fbae  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1fbb3  stelem.ref
0x1fbb4  dup
0x1fbb5  ldc.i4.2
0x1fbb6  ldstr    asc_11387C// ","
0x1fbbb  stelem.ref
0x1fbbc  dup
0x1fbbd  ldc.i4.3
0x1fbbe  ldc.i4.s 0xA
0x1fbc0  stloc.s  4
0x1fbc2  ldloca.s 4
0x1fbc4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1fbc9  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1fbce  stelem.ref
0x1fbcf  dup
0x1fbd0  ldc.i4.4
0x1fbd1  ldstr    asc_11AA82// ",'"
  ... truncated ...
```
