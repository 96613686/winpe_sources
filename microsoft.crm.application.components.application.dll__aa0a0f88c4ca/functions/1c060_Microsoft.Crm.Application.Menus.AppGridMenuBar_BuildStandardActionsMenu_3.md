# Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu_3

- ea: `0x1c060`
- end: `0x1c953`
- name: `Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu_3`
- size: `2291`
- prototype: ``
- caller_count: `5`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x1c040`
- `0x1d850`
- `0x1f810`
- `0x1fcb0`
- `0x233b0`

## callees

- `0x19f10`
- `0x19fb0`
- `0x19fd0`
- `0x1a490`
- `0x1a5c0`
- `0x1ae30`
- `0x1af40`
- `0x1afa0`
- `0x1b0a0`
- `0x1b140`
- `0x1b1c0`
- `0x1b380`
- `0x1b390`
- `0x1b3d0`
- `0x1b410`
- `0x1b4d0`
- `0x1c060`
- `0x1ca50`
- `0x1ce50`
- `0x1cf10`
- `0x1cf60`
- `0x1d6a0`
- `0x1d770`
- `0x24210`

## string_xrefs

- `0x1c54e`: `MenuItem_Label_Copy_Shortcut`
- `0x1c45e`: `MenuItem_Label_Complete`
- `0x1c468`: `completeactivity`
- `0x1c55d`: `copyshortcut`

## pseudocode

```c

```

## disassembly

```asm
0x1c060  ldarg.0
0x1c061  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppGridMenuBar::_parentEntityAccessRights
0x1c066  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanAppendTo()
0x1c06b  brtrue.s loc_1C07A
0x1c06d  ldc.i4   0x3F2
0x1c072  ldarg.0
0x1c073  call     instance int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityType()
0x1c078  bne.un.s loc_1C08A
0x1c07a  ldarg.0
0x1c07b  ldfld    bool Microsoft.Crm.Application.Menus.AppGridMenuBar::_buttonNew
0x1c080  ldarg.2
0x1c081  and
0x1c082  brfalse.s loc_1C08A
0x1c084  ldarg.0
0x1c085  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton()
0x1c08a  ldarg.0
0x1c08b  call     instance bool Microsoft.Crm.Application.Menus.AppGridMenuBar::get_DisplayActions()
0x1c090  brfalse  loc_1C7C4
0x1c095  ldarg.1
0x1c096  ldc.i4.4
0x1c097  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x1c09c  brfalse.s loc_1C0BC
0x1c09e  ldarg.0
0x1c09f  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1c0a4  ldc.i4   0x80000
0x1c0a9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c0ae  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c0b3  brfalse.s loc_1C0BC
0x1c0b5  ldarg.0
0x1c0b6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddAssignButton()
0x1c0bb  pop
0x1c0bc  ldarg.0
0x1c0bd  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridType
0x1c0c2  ldc.i4.2
0x1c0c3  bne.un   loc_1C156
0x1c0c8  ldarg.0
0x1c0c9  ldfld    bool Microsoft.Crm.Application.Menus.AppGridMenuBar::_showDisassociation
0x1c0ce  brfalse  loc_1C156
0x1c0d3  ldarg.0
0x1c0d4  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppGridMenuBar::_parentEntityAccessRights
0x1c0d9  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanAppendTo()
0x1c0de  brfalse  loc_1C17D
0x1c0e3  ldarg.0
0x1c0e4  ldarg.0
0x1c0e5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1c0ea  ldstr    aMenuitemLabelD_2// "MenuItem_Label_Disassociate"
0x1c0ef  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1c0f4  ldstr    aDisassociate// "disassociate"
0x1c0f9  ldstr    aWindowParentGe// "window.parent.$get('crmFormSubmit').crm"...
0x1c0fe  ldstr    aWindowParentGe_0// "window.parent.$get('crmFormSubmit').crm"...
0x1c103  ldc.i4.2
0x1c104  newarr   [mscorlib]System.String
0x1c109  dup
0x1c10a  ldc.i4.0
0x1c10b  ldstr    aAssociationnam// "associationName"
0x1c110  stelem.ref
0x1c111  dup
0x1c112  ldc.i4.1
0x1c113  ldstr    aRoleord// "roleOrd"
0x1c118  stelem.ref
0x1c119  ldc.i4.2
0x1c11a  newarr   [mscorlib]System.String
0x1c11f  dup
0x1c120  ldc.i4.0
0x1c121  ldarg.0
0x1c122  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Menus.AppGridMenuBar::_grid
0x1c127  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x1c12c  ldstr    aRelname// "relName"
0x1c131  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1c136  stelem.ref
0x1c137  dup
0x1c138  ldc.i4.1
0x1c139  ldarg.0
0x1c13a  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Menus.AppGridMenuBar::_grid
0x1c13f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x1c144  ldstr    aRoleord// "roleOrd"
0x1c149  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1c14e  stelem.ref
0x1c14f  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoActionEx(string name, string action, string parentId, string parentType, string[] queryStringParameters, string[] queryStringValues)
0x1c154  br.s     loc_1C17D
0x1c156  ldarg.1
0x1c157  ldc.i4.2
0x1c158  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x1c15d  brfalse.s loc_1C17D
0x1c15f  ldarg.0
0x1c160  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1c165  ldc.i4   0x10000
0x1c16a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c16f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c174  brfalse.s loc_1C17D
0x1c176  ldarg.0
0x1c177  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddDeleteButton()
0x1c17c  pop
0x1c17d  ldarg.1
0x1c17e  ldc.i4   0x100
0x1c183  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x1c188  brfalse  loc_1C20F
0x1c18d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x1c192  brfalse.s loc_1C20F
0x1c194  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_Merge()
0x1c199  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c19e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c1a3  brfalse.s loc_1C20F
0x1c1a5  ldarg.0
0x1c1a6  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1c1ab  ldc.i4.2
0x1c1ac  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c1b1  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c1b6  brfalse.s loc_1C20F
0x1c1b8  ldarg.0
0x1c1b9  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_mergeButton
0x1c1be  ldarg.0
0x1c1bf  ldstr    aMerge// "merge"
0x1c1c4  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildDoActionScript(string action)
0x1c1c9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x1c1ce  ldarg.0
0x1c1cf  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_mergeButton
0x1c1d4  ldstr    aImgsIco16Merge// "/_imgs/ico_16_merge.gif"
0x1c1d9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c1de  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c1e3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x1c1e8  ldarg.0
0x1c1e9  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_mergeButton
0x1c1ee  ldarg.0
0x1c1ef  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1c1f4  ldstr    aMenuitemLabelM// "MenuItem_Label_Merge"
0x1c1f9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1c1fe  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x1c203  ldarg.0
0x1c204  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_mergeButton
0x1c209  ldc.i4.1
0x1c20a  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x1c20f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c214  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c219  ldarg.0
0x1c21a  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1c21f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0x1c224  stloc.1
0x1c225  ldloc.1
0x1c226  brfalse.s loc_1C241
0x1c228  ldloc.1
0x1c229  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsConnectionsEnabled()
0x1c22e  brfalse.s loc_1C241
0x1c230  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateConnection()
0x1c235  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c23a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c23f  br.s     loc_1C242
0x1c241  ldc.i4.0
0x1c242  ldarg.s  7
0x1c244  and
0x1c245  brfalse.s loc_1C255
0x1c247  ldarg.0
0x1c248  ldfld    bool Microsoft.Crm.Application.Menus.AppGridMenuBar::FromDuplicateRefreshForm
0x1c24d  brtrue.s loc_1C255
0x1c24f  ldarg.0
0x1c250  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddConnectionButton()
0x1c255  ldarg.1
0x1c256  ldc.i4   0x80
0x1c25b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x1c260  brfalse.s loc_1C2A2
0x1c262  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_BulkEdit()
0x1c267  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c26c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c271  brfalse.s loc_1C2A2
0x1c273  ldarg.0
0x1c274  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1c279  ldc.i4.2
0x1c27a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c27f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c284  brfalse.s loc_1C2A2
0x1c286  ldarg.0
0x1c287  ldarg.0
0x1c288  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1c28d  ldstr    aMenuitemLabelB// "MenuItem_Label_BulkEdit"
0x1c292  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1c297  ldstr    aBulkedit// "bulkedit"
0x1c29c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x1c2a1  pop
0x1c2a2  ldarg.1
0x1c2a3  ldc.i4.1
0x1c2a4  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x1c2a9  brfalse.s loc_1C2E5
0x1c2ab  ldarg.0
0x1c2ac  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1c2b1  ldc.i4   0x40000
0x1c2b6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c2bb  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c2c0  brfalse.s loc_1C2E5
0x1c2c2  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x1c2c7  brfalse.s loc_1C2E5
0x1c2c9  ldarg.0
0x1c2ca  ldarg.0
0x1c2cb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1c2d0  ldstr    aMenuitemLabelS_6// "MenuItem_Label_Share"
0x1c2d5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1c2da  ldstr    aShare// "share"
0x1c2df  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x1c2e4  pop
0x1c2e5  ldarg.1
0x1c2e6  ldc.i4.s 0x10
0x1c2e8  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x1c2ed  brfalse.s loc_1C356
0x1c2ef  ldarg.0
0x1c2f0  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1c2f5  ldc.i4.2
0x1c2f6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c2fb  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c300  brfalse.s loc_1C356
0x1c302  ldarg.0
0x1c303  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1c308  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsActivityObject(int32)
0x1c30d  brfalse.s loc_1C32D
0x1c30f  ldarg.0
0x1c310  ldarg.0
0x1c311  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1c316  ldstr    aMenuitemLabelA_5// "MenuItem_Label_Activity_Close"
0x1c31b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1c320  ldstr    aDeactivate// "deactivate"
0x1c325  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x1c32a  pop
0x1c32b  br.s     loc_1C356
0x1c32d  ldarg.0
0x1c32e  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1c333  ldc.i4   0x1068
0x1c338  beq.s    loc_1C356
0x1c33a  ldarg.0
0x1c33b  ldarg.0
0x1c33c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1c341  ldstr    aMenuitemLabelD_0// "MenuItem_Label_Deactivate"
0x1c346  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1c34b  ldstr    aDeactivate// "deactivate"
0x1c350  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x1c355  pop
0x1c356  ldarg.1
0x1c357  ldc.i4.s 0x40
0x1c359  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x1c35e  brfalse.s loc_1C38F
0x1c360  ldarg.0
0x1c361  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1c366  ldc.i4.2
0x1c367  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c36c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c371  brfalse.s loc_1C38F
0x1c373  ldarg.0
0x1c374  ldarg.0
0x1c375  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1c37a  ldstr    aMenuitemLabelC_2// "MenuItem_Label_Cancel"
0x1c37f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1c384  ldstr    aCancel// "cancel"
0x1c389  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x1c38e  pop
0x1c38f  ldarg.1
0x1c390  ldc.i4   0x2000
0x1c395  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x1c39a  brfalse.s loc_1C3E8
0x1c39c  ldc.i4.5
0x1c39d  ldc.i4.2
0x1c39e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c3a3  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c3a8  brfalse.s loc_1C3E8
0x1c3aa  ldc.i4.5
0x1c3ab  ldc.i4.4
0x1c3ac  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c3b1  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c3b6  brfalse.s loc_1C3E8
0x1c3b8  ldarg.0
0x1c3b9  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1c3be  ldc.i4.s 0x10
0x1c3c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c3c5  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c3ca  brfalse.s loc_1C3E8
0x1c3cc  ldarg.0
0x1c3cd  ldarg.0
0x1c3ce  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1c3d3  ldstr    aMenuitemLabelA_6// "MenuItem_Label_AddNotes"
0x1c3d8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1c3dd  ldstr    aAddnotes// "addnotes"
0x1c3e2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x1c3e7  pop
0x1c3e8  ldarg.1
0x1c3e9  ldc.i4   0x4000
0x1c3ee  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x1c3f3  brfalse.s loc_1C437
0x1c3f5  ldarg.0
0x1c3f6  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1c3fb  ldc.i4.2
0x1c3fc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c401  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c406  brfalse.s loc_1C437
0x1c408  ldarg.0
0x1c409  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1c40e  ldc.i4.4
0x1c40f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c414  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c419  brfalse.s loc_1C437
0x1c41b  ldarg.0
0x1c41c  ldarg.0
0x1c41d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1c422  ldstr    aMenuitemLabelS_7// "MenuItem_Label_SetRegarding"
0x1c427  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
  ... truncated ...
```
