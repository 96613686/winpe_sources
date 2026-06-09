# Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildListMemberViewMenuBar

- ea: `0x214e0`
- end: `0x21797`
- name: `Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildListMemberViewMenuBar`
- size: `695`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1b610`

## callees

- `0x19fd0`
- `0x1a490`
- `0x1a510`
- `0x1b380`
- `0x1b410`
- `0x1b4d0`
- `0x1c020`
- `0x214e0`
- `0x23fe0`
- `0x24210`
- `0x242b0`

## string_xrefs

- `0x215e7`: `OpenManageMembersWizard(`
- `0x21686`: `Ribbon.ListMember.RemoveFromList`
- `0x21690`: `removelistmembers`
- `0x216d6`: `Ribbon.ListMember.CopyListMember`
- `0x216e6`: `copylistmember`
- `0x2172f`: `Ribbon.ListMember.CreateOpportunityForMembers`
- `0x21739`: `createopportunity`

## pseudocode

```c

```

## disassembly

```asm
0x214e0  ldarg.0
0x214e1  call     instance int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityType()
0x214e6  pop
0x214e7  ldarg.0
0x214e8  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityId()
0x214ed  stloc.0
0x214ee  ldc.i4.0
0x214ef  stloc.1
0x214f0  ldc.i4.0
0x214f1  stloc.2
0x214f2  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.MailMergeUtility::.ctor()
0x214f7  ldloc.0
0x214f8  ldloca.s 1
0x214fa  ldloca.s 2
0x214fc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21501  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.MailMergeUtility::RetrieveListMemberTypeAndStatus(string, bool&, bool&, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x21506  stloc.3
0x21507  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x2150c  brfalse  loc_2178C
0x21511  ldloc.2
0x21512  brfalse  loc_21705
0x21517  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AppendToList()
0x2151c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21521  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x21526  brfalse  loc_21705
0x2152b  ldarg.0
0x2152c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppGridMenuBar::_parentEntityAccessRights
0x21531  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanAppendTo()
0x21536  brfalse  loc_21705
0x2153b  ldc.i4.0
0x2153c  stloc.s  4
0x2153e  ldloc.3
0x2153f  ldc.i4.1
0x21540  sub
0x21541  switch   loc_21558, loc_2156B, loc_2158F, loc_2157E
0x21556  br.s     loc_2158F
0x21558  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AppendAccount()
0x2155d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21562  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x21567  stloc.s  4
0x21569  br.s     loc_2158F
0x2156b  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AppendContact()
0x21570  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21575  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2157a  stloc.s  4
0x2157c  br.s     loc_2158F
0x2157e  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AppendLead()
0x21583  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21588  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2158d  stloc.s  4
0x2158f  ldloc.s  4
0x21591  brfalse  loc_21705
0x21596  ldloc.1
0x21597  brtrue   loc_216B0
0x2159c  ldarg.0
0x2159d  ldstr    aMaListsListqua// "ma/lists/listqualificationdialog/dlg_ma"...
0x215a2  call     instance valuetype WindowSize Microsoft.Crm.Application.Menus.AppGridMenuBar::GetWindowSize(string url)
0x215a7  stloc.s  5
0x215a9  ldarg.0
0x215aa  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x215af  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x215b4  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x215b9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x215be  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x215c3  stloc.s  6
0x215c5  ldloc.s  6
0x215c7  ldarg.0
0x215c8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x215cd  ldstr    aRibbonListmemb// "Ribbon.ListMember.ManageMembers"
0x215d2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x215d7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x215dc  ldloc.s  6
0x215de  ldc.i4.s 0xB
0x215e0  newarr   [mscorlib]System.Object
0x215e5  dup
0x215e6  ldc.i4.0
0x215e7  ldstr    aOpenmanagememb// "OpenManageMembersWizard("
0x215ec  stelem.ref
0x215ed  dup
0x215ee  ldc.i4.1
0x215ef  ldloc.3
0x215f0  box      [mscorlib]System.Int32
0x215f5  stelem.ref
0x215f6  dup
0x215f7  ldc.i4.2
0x215f8  ldstr    asc_117A44// ", "
0x215fd  stelem.ref
0x215fe  dup
0x215ff  ldc.i4.3
0x21600  ldarg.0
0x21601  ldfld    string Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridClientId
0x21606  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x2160b  stelem.ref
0x2160c  dup
0x2160d  ldc.i4.4
0x2160e  ldstr    asc_117A44// ", "
0x21613  stelem.ref
0x21614  dup
0x21615  ldc.i4.5
0x21616  ldloc.0
0x21617  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x2161c  stelem.ref
0x2161d  dup
0x2161e  ldc.i4.6
0x2161f  ldstr    asc_117A44// ", "
0x21624  stelem.ref
0x21625  dup
0x21626  ldc.i4.7
0x21627  ldloca.s 5
0x21629  ldflda   int32 WindowSize::Width
0x2162e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21633  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x21638  stelem.ref
0x21639  dup
0x2163a  ldc.i4.8
0x2163b  ldstr    asc_11C75C// " , "
0x21640  stelem.ref
0x21641  dup
0x21642  ldc.i4.s 9
0x21644  ldloca.s 5
0x21646  ldflda   int32 WindowSize::Height
0x2164b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21650  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x21655  stelem.ref
0x21656  dup
0x21657  ldc.i4.s 0xA
0x21659  ldstr    asc_F5C96// ")"
0x2165e  stelem.ref
0x2165f  call     string [mscorlib]System.String::Concat(object[])
0x21664  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x21669  ldloc.s  6
0x2166b  ldstr    aImgsIco16Manag// "/_imgs/ico_16_manage_members.gif"
0x21670  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21675  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2167a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x2167f  ldarg.0
0x21680  ldarg.0
0x21681  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x21686  ldstr    aRibbonListmemb_0// "Ribbon.ListMember.RemoveFromList"
0x2168b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21690  ldstr    aRemovelistmemb// "removelistmembers"
0x21695  ldstr    aWindowParentGe// "window.parent.$get('crmFormSubmit').crm"...
0x2169a  ldstr    aWindowParentGe_0// "window.parent.$get('crmFormSubmit').crm"...
0x2169f  ldc.i4.0
0x216a0  newarr   [mscorlib]System.String
0x216a5  ldc.i4.0
0x216a6  newarr   [mscorlib]System.String
0x216ab  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoActionEx(string name, string action, string parentId, string parentType, string[] queryStringParameters, string[] queryStringValues)
0x216b0  ldarg.0
0x216b1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x216b6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x216bb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x216c0  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x216c5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x216ca  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x216cf  dup
0x216d0  ldarg.0
0x216d1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x216d6  ldstr    aRibbonListmemb_1// "Ribbon.ListMember.CopyListMember"
0x216db  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x216e0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x216e5  ldarg.0
0x216e6  ldstr    aCopylistmember// "copylistmember"
0x216eb  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildDoActionScript(string action)
0x216f0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x216f5  ldarg.0
0x216f6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x216fb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x21700  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x21705  ldarg.0
0x21706  ldc.i4.0
0x21707  ldc.i4.0
0x21708  ldc.i4.1
0x21709  ldc.i4.1
0x2170a  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport, bool buttonPrint)
0x2170f  ldloc.3
0x21710  ldc.i4.1
0x21711  beq.s    loc_21717
0x21713  ldloc.3
0x21714  ldc.i4.2
0x21715  bne.un.s loc_2175A
0x21717  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateOpportunity()
0x2171c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21721  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x21726  brfalse.s loc_21796
0x21728  ldarg.0
0x21729  ldarg.0
0x2172a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x2172f  ldstr    aRibbonListmemb_2// "Ribbon.ListMember.CreateOpportunityForM"...
0x21734  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21739  ldstr    aCreateopportun// "createopportunity"
0x2173e  ldstr    aWindowParentGe// "window.parent.$get('crmFormSubmit').crm"...
0x21743  ldstr    aWindowParentGe_0// "window.parent.$get('crmFormSubmit').crm"...
0x21748  ldc.i4.0
0x21749  newarr   [mscorlib]System.String
0x2174e  ldc.i4.0
0x2174f  newarr   [mscorlib]System.String
0x21754  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoActionEx(string name, string action, string parentId, string parentType, string[] queryStringParameters, string[] queryStringValues)
0x21759  ret
0x2175a  ldloc.3
0x2175b  ldc.i4.4
0x2175c  bne.un.s loc_21796
0x2175e  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateLead()
0x21763  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21768  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2176d  brfalse.s loc_21796
0x2176f  ldarg.0
0x21770  ldarg.0
0x21771  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x21776  ldstr    aRibbonListmemb_3// "Ribbon.ListMember.ConvertLead"
0x2177b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21780  ldstr    aConvertlead// "convertlead"
0x21785  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x2178a  pop
0x2178b  ret
0x2178c  ldarg.0
0x2178d  ldc.i4.0
0x2178e  ldc.i4.0
0x2178f  ldc.i4.1
0x21790  ldc.i4.1
0x21791  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport, bool buttonPrint)
0x21796  ret
```
