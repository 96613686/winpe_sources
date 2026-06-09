# Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildCampaignMenuBar

- ea: `0x20c30`
- end: `0x20fa5`
- name: `Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildCampaignMenuBar`
- size: `885`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1b610`

## callees

- `0x19ea0`
- `0x19ec0`
- `0x1a490`
- `0x1a510`
- `0x1a5e0`
- `0x1c010`
- `0x1fff0`
- `0x20c30`
- `0x24210`
- `0x242b0`

## string_xrefs

- `0x20f53`: `Ribbon.campaign.NewTemplate`
- `0x20f63`: `openObjEx(Campaign, null, null, '?template=1');`
- `0x20f6e`: `/_imgs/ico_16_template.gif`
- `0x20f88`: `Ribbon.campaign.NewTemplate.ToolTip`

## pseudocode

```c

```

## disassembly

```asm
0x20c30  ldc.i4.0
0x20c31  stloc.0
0x20c32  ldc.i4.0
0x20c33  stloc.1
0x20c34  ldarg.0
0x20c35  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridType
0x20c3a  ldc.i4.2
0x20c3b  bne.un   loc_20E60
0x20c40  ldsfld   string [mscorlib]System.String::Empty
0x20c45  stloc.3
0x20c46  ldsfld   string [mscorlib]System.String::Empty
0x20c4b  stloc.s  4
0x20c4d  ldarg.0
0x20c4e  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::get_RelationshipName()
0x20c53  stloc.s  5
0x20c55  ldloc.s  5
0x20c57  ldstr    aCampaigncampai// "campaigncampaign_association"
0x20c5c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x20c61  brtrue.s loc_20C79
0x20c63  ldloc.s  5
0x20c65  ldstr    aCampaignlistAs// "campaignlist_association"
0x20c6a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x20c6f  brtrue   loc_20D38
0x20c74  br       loc_20E0F
0x20c79  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AppendCampaign()
0x20c7e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x20c83  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x20c88  brfalse  loc_20E3D
0x20c8d  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AppendToCampaign()
0x20c92  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x20c97  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x20c9c  brfalse  loc_20E3D
0x20ca1  ldarg.0
0x20ca2  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppGridMenuBar::_parentEntityAccessRights
0x20ca7  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanAppend()
0x20cac  brfalse  loc_20E3D
0x20cb1  ldarg.0
0x20cb2  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppGridMenuBar::_parentEntityAccessRights
0x20cb7  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanAppendTo()
0x20cbc  brfalse  loc_20E3D
0x20cc1  ldc.i4.5
0x20cc2  newarr   [mscorlib]System.String
0x20cc7  dup
0x20cc8  ldc.i4.0
0x20cc9  ldstr    aRunfunctionfro_10// "RunFunctionFromParentOrSelf('locAssocOb"...
0x20cce  stelem.ref
0x20ccf  dup
0x20cd0  ldc.i4.1
0x20cd1  ldarg.0
0x20cd2  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Menus.AppGridMenuBar::_grid
0x20cd7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x20cdc  ldstr    aRelname// "relName"
0x20ce1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x20ce6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x20ceb  stelem.ref
0x20cec  dup
0x20ced  ldc.i4.2
0x20cee  ldstr    asc_117A44// ", "
0x20cf3  stelem.ref
0x20cf4  dup
0x20cf5  ldc.i4.3
0x20cf6  ldarg.0
0x20cf7  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Menus.AppGridMenuBar::_grid
0x20cfc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x20d01  ldstr    aRoleord// "roleOrd"
0x20d06  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x20d0b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x20d10  stelem.ref
0x20d11  dup
0x20d12  ldc.i4.4
0x20d13  ldstr    asc_11632C// ");"
0x20d18  stelem.ref
0x20d19  call     string [mscorlib]System.String::Concat(string[])
0x20d1e  stloc.3
0x20d1f  ldarg.0
0x20d20  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x20d25  ldstr    aMenuLabelAddex// "Menu_Label_AddExiting"
0x20d2a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x20d2f  stloc.s  4
0x20d31  ldc.i4.1
0x20d32  stloc.1
0x20d33  br       loc_20E3D
0x20d38  ldc.i4.0
0x20d39  stloc.s  6
0x20d3b  ldc.i4.0
0x20d3c  stloc.s  7
0x20d3e  ldarg.0
0x20d3f  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityId()
0x20d44  stloc.s  8
0x20d46  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.MailMergeUtility::.ctor()
0x20d4b  ldloc.s  8
0x20d4d  ldloca.s 7
0x20d4f  ldloca.s 6
0x20d51  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x20d56  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.MailMergeUtility::RetrieveListMemberTypeAndStatus(string, bool&, bool&, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x20d5b  pop
0x20d5c  ldloc.s  6
0x20d5e  brfalse  loc_20E3D
0x20d63  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AppendList()
0x20d68  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x20d6d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x20d72  brfalse  loc_20E3D
0x20d77  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AppendToCampaign()
0x20d7c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x20d81  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x20d86  brfalse  loc_20E3D
0x20d8b  ldarg.0
0x20d8c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppGridMenuBar::_parentEntityAccessRights
0x20d91  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanAppend()
0x20d96  brfalse  loc_20E3D
0x20d9b  ldc.i4.5
0x20d9c  newarr   [mscorlib]System.String
0x20da1  dup
0x20da2  ldc.i4.0
0x20da3  ldstr    aRunfunctionfro_11// "RunFunctionFromParentOrSelf('locAssocOb"...
0x20da8  stelem.ref
0x20da9  dup
0x20daa  ldc.i4.1
0x20dab  ldarg.0
0x20dac  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Menus.AppGridMenuBar::_grid
0x20db1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x20db6  ldstr    aRelname// "relName"
0x20dbb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x20dc0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x20dc5  stelem.ref
0x20dc6  dup
0x20dc7  ldc.i4.2
0x20dc8  ldstr    asc_117A44// ", "
0x20dcd  stelem.ref
0x20dce  dup
0x20dcf  ldc.i4.3
0x20dd0  ldarg.0
0x20dd1  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Menus.AppGridMenuBar::_grid
0x20dd6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x20ddb  ldstr    aRoleord// "roleOrd"
0x20de0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x20de5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x20dea  stelem.ref
0x20deb  dup
0x20dec  ldc.i4.4
0x20ded  ldstr    asc_11632C// ");"
0x20df2  stelem.ref
0x20df3  call     string [mscorlib]System.String::Concat(string[])
0x20df8  stloc.3
0x20df9  ldarg.0
0x20dfa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x20dff  ldstr    aRibbonListAddt// "Ribbon.list.AddToCampaign"
0x20e04  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x20e09  stloc.s  4
0x20e0b  ldc.i4.1
0x20e0c  stloc.1
0x20e0d  br.s     loc_20E3D
0x20e0f  ldarg.0
0x20e10  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::get_CurrentTabId()
0x20e15  ldstr    aAreacampaignsi// "areaCampaignsInSFA"
0x20e1a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x20e1f  brfalse.s loc_20E2A
0x20e21  ldsfld   string [mscorlib]System.String::Empty
0x20e26  stloc.s  4
0x20e28  br.s     loc_20E3D
0x20e2a  ldarg.0
0x20e2b  call     instance bool Microsoft.Crm.Application.Menus.AppGridMenuBar::get_WasSystemRelationshipSpecified()
0x20e30  brtrue.s loc_20E3D
0x20e32  ldc.i4.0
0x20e33  ldstr    aInvalidTabset// "Invalid tabSet."
0x20e38  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x20e3d  ldloc.3
0x20e3e  brfalse.s loc_20E62
0x20e40  ldloc.3
0x20e41  callvirt instance int32 [mscorlib]System.String::get_Length()
0x20e46  brfalse.s loc_20E62
0x20e48  ldloc.s  4
0x20e4a  brfalse.s loc_20E62
0x20e4c  ldloc.s  4
0x20e4e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x20e53  brfalse.s loc_20E62
0x20e55  ldarg.0
0x20e56  ldloc.3
0x20e57  ldloc.s  4
0x20e59  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton(string onclickScript, string buttonTitle)
0x20e5e  br.s     loc_20E62
0x20e60  ldc.i4.1
0x20e61  stloc.0
0x20e62  ldarg.0
0x20e63  call     instance int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityType()
0x20e68  stloc.2
0x20e69  ldloc.2
0x20e6a  ldc.i4.1
0x20e6b  beq.s    loc_20E75
0x20e6d  ldloc.2
0x20e6e  ldc.i4.2
0x20e6f  beq.s    loc_20E75
0x20e71  ldloc.2
0x20e72  ldc.i4.4
0x20e73  bne.un.s loc_20EA0
0x20e75  ldarg.0
0x20e76  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridType
0x20e7b  ldc.i4.2
0x20e7c  bne.un.s loc_20E8F
0x20e7e  ldarg.0
0x20e7f  call     instance bool Microsoft.Crm.Application.Menus.AppGridMenuBar::get_WasSystemRelationshipSpecified()
0x20e84  brfalse.s loc_20E8F
0x20e86  ldarg.0
0x20e87  ldc.i4.1
0x20e88  stfld    bool Microsoft.Crm.Application.Menus.AppGridMenuBar::_showDisassociation
0x20e8d  br.s     loc_20E96
0x20e8f  ldarg.0
0x20e90  ldc.i4.0
0x20e91  stfld    bool Microsoft.Crm.Application.Menus.AppGridMenuBar::_showDisassociation
0x20e96  ldarg.0
0x20e97  ldc.i4.0
0x20e98  ldloc.0
0x20e99  ldc.i4.1
0x20e9a  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport)
0x20e9f  ret
0x20ea0  ldloc.2
0x20ea1  ldc.i4   0x10CC
0x20ea6  bne.un.s loc_20EE0
0x20ea8  ldloc.1
0x20ea9  brfalse.s loc_20EB5
0x20eab  ldarg.0
0x20eac  ldc.i4.2
0x20ead  ldloc.0
0x20eae  ldc.i4.1
0x20eaf  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport)
0x20eb4  ret
0x20eb5  ldarg.0
0x20eb6  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridType
0x20ebb  ldc.i4.2
0x20ebc  bne.un.s loc_20ECF
0x20ebe  ldarg.0
0x20ebf  call     instance bool Microsoft.Crm.Application.Menus.AppGridMenuBar::get_WasSystemRelationshipSpecified()
0x20ec4  brfalse.s loc_20ECF
0x20ec6  ldarg.0
0x20ec7  ldc.i4.1
0x20ec8  stfld    bool Microsoft.Crm.Application.Menus.AppGridMenuBar::_showDisassociation
0x20ecd  br.s     loc_20ED6
0x20ecf  ldarg.0
0x20ed0  ldc.i4.0
0x20ed1  stfld    bool Microsoft.Crm.Application.Menus.AppGridMenuBar::_showDisassociation
0x20ed6  ldarg.0
0x20ed7  ldc.i4.0
0x20ed8  ldloc.0
0x20ed9  ldc.i4.1
0x20eda  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport)
0x20edf  ret
0x20ee0  ldloc.2
0x20ee1  ldc.i4   0x1130
0x20ee6  bne.un.s loc_20F20
0x20ee8  ldloc.1
0x20ee9  brfalse.s loc_20EF5
0x20eeb  ldarg.0
0x20eec  ldc.i4.2
0x20eed  ldloc.0
0x20eee  ldc.i4.1
0x20eef  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport)
0x20ef4  ret
0x20ef5  ldarg.0
0x20ef6  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridType
0x20efb  ldc.i4.2
0x20efc  bne.un.s loc_20F0F
0x20efe  ldarg.0
0x20eff  call     instance bool Microsoft.Crm.Application.Menus.AppGridMenuBar::get_WasSystemRelationshipSpecified()
0x20f04  brfalse.s loc_20F0F
0x20f06  ldarg.0
0x20f07  ldc.i4.1
0x20f08  stfld    bool Microsoft.Crm.Application.Menus.AppGridMenuBar::_showDisassociation
0x20f0d  br.s     loc_20F16
0x20f0f  ldarg.0
0x20f10  ldc.i4.0
0x20f11  stfld    bool Microsoft.Crm.Application.Menus.AppGridMenuBar::_showDisassociation
0x20f16  ldarg.0
0x20f17  ldc.i4.0
0x20f18  ldloc.0
0x20f19  ldc.i4.1
0x20f1a  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport)
0x20f1f  ret
0x20f20  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateCampaign()
0x20f25  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x20f2a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x20f2f  brfalse.s loc_20F97
0x20f31  ldarg.0
0x20f32  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x20f37  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x20f3c  ldc.i4.1
0x20f3d  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x20f42  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Insert(int32, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x20f47  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x20f4c  dup
0x20f4d  ldarg.0
0x20f4e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x20f53  ldstr    aRibbonCampaign// "Ribbon.campaign.NewTemplate"
0x20f58  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x20f5d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x20f62  dup
0x20f63  ldstr    aOpenobjexCampa// "openObjEx(Campaign, null, null, '?templ"...
0x20f68  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x20f6d  dup
0x20f6e  ldstr    aImgsIco16Templ// "/_imgs/ico_16_template.gif"
0x20f73  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
  ... truncated ...
```
