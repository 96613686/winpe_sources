# Microsoft.Crm.Application.Menus.AppFormMenuBar::BuildActionsMenu

- ea: `0x18c40`
- end: `0x19236`
- name: `Microsoft.Crm.Application.Menus.AppFormMenuBar::BuildActionsMenu`
- size: `1526`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x17d60`

## callees

- `0x18940`
- `0x18c40`
- `0x19240`
- `0x192e0`
- `0x193a0`
- `0x19630`
- `0x19a50`
- `0x24210`
- `0x242a0`
- `0x242b0`
- `0x243f0`
- `0x26470`
- `0x264c0`
- `0x26510`
- `0x26560`
- `0x26ba0`
- `0x46e30`
- `0x8d1a0`
- `0x8d790`

## string_xrefs

- `0x18dbb`: `_deleteActionEnabled`
- `0x18dd2`: `MenuItem_Label_DeleteObject`
- `0x18e00`: `onActionMenuClick('delete', `
- `0x18ec7`: `Mscrm.CommandBarActions.assignObject(`
- `0x1917b`: `MenuItem_Label_Copy_Shortcut`

## pseudocode

```c

```

## disassembly

```asm
0x18c40  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::.ctor()
0x18c45  stloc.0
0x18c46  ldloc.0
0x18c47  ldstr    aAction// "action"
0x18c4c  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x18c51  ldloc.0
0x18c52  ldstr    aImgsMnuActions// "/_imgs/mnu_actions.gif"
0x18c57  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18c5c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18c61  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x18c66  ldloc.0
0x18c67  ldarg.0
0x18c68  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x18c6d  ldstr    aMenuLabelActio// "Menu_Label_Actions"
0x18c72  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18c77  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x18c7c  ldloc.0
0x18c7d  ldloc.0
0x18c7e  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x18c83  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x18c88  ldloc.0
0x18c89  ldc.i4.1
0x18c8a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::set_DownArrow(bool)
0x18c8f  ldloc.0
0x18c90  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x18c95  stloc.1
0x18c96  ldarg.0
0x18c97  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x18c9c  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x18ca1  callvirt instance valuetype Microsoft.Crm.Application.Forms.FormState Microsoft.Crm.Application.Forms.AppForm::get_State()
0x18ca6  ldc.i4.2
0x18ca7  bne.un   loc_19235
0x18cac  ldarg.0
0x18cad  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppFormMenuBar::_privileges
0x18cb2  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanAppendTo()
0x18cb7  brfalse  loc_18D8F
0x18cbc  ldc.i4.0
0x18cbd  stloc.s  4
0x18cbf  ldarg.0
0x18cc0  ldfld    bool Microsoft.Crm.Application.Menus.AppFormMenuBar::_isEntityEnabled
0x18cc5  brfalse.s loc_18CE7
0x18cc7  ldarg.0
0x18cc8  ldc.i4.1
0x18cc9  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormActionParameters actionParameter)
0x18cce  brtrue.s loc_18CDD
0x18cd0  ldarg.0
0x18cd1  ldc.i4   0x80
0x18cd6  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormActionParameters actionParameter)
0x18cdb  brfalse.s loc_18CE7
0x18cdd  ldarg.0
0x18cde  ldloc.1
0x18cdf  call     instance void Microsoft.Crm.Application.Menus.AppFormMenuBar::BuildActivitiesSubmenu(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu actMenu)
0x18ce4  ldc.i4.1
0x18ce5  stloc.s  4
0x18ce7  ldarg.0
0x18ce8  ldc.i4.8
0x18ce9  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormActionParameters actionParameter)
0x18cee  brfalse  loc_18D7C
0x18cf3  ldarg.0
0x18cf4  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x18cf9  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18cfe  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsIosDevice(class [System.Web]System.Web.HttpRequest)
0x18d03  brtrue.s loc_18D7C
0x18d05  ldloc.1
0x18d06  ldarg.0
0x18d07  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x18d0c  ldstr    aMenuLabelAddan// "Menu_Label_AddAnAttachMent"
0x18d11  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18d16  ldstr    aLocaddobjto// "locAddObjTo("
0x18d1b  ldc.i4.5
0x18d1c  stloc.s  5
0x18d1e  ldloca.s 5
0x18d20  ldstr    aD// "D"
0x18d25  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18d2a  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x18d2f  ldstr    asc_11632C// ");"
0x18d34  call     string [mscorlib]System.String::Concat(string, string, string)
0x18d39  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x18d3e  pop
0x18d3f  ldloc.1
0x18d40  ldarg.0
0x18d41  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x18d46  ldstr    aMenuLabelAddaf// "Menu_Label_AddAFile"
0x18d4b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18d50  ldstr    aLocaddfileto// "locAddFileTo("
0x18d55  ldc.i4.5
0x18d56  stloc.s  5
0x18d58  ldloca.s 5
0x18d5a  ldstr    aD// "D"
0x18d5f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18d64  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x18d69  ldstr    asc_11632C// ");"
0x18d6e  call     string [mscorlib]System.String::Concat(string, string, string)
0x18d73  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x18d78  pop
0x18d79  ldc.i4.1
0x18d7a  stloc.s  4
0x18d7c  ldarg.0
0x18d7d  ldloc.1
0x18d7e  ldc.i4.s 0x40
0x18d80  call     instance void Microsoft.Crm.Application.Menus.AppMenuBar::RaiseMenuReadyEvent(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu menu, int32 menuId)
0x18d85  ldloc.s  4
0x18d87  brfalse.s loc_18D8F
0x18d89  ldloc.1
0x18d8a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x18d8f  ldarg.0
0x18d90  ldc.i4.2
0x18d91  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormActionParameters actionParameter)
0x18d96  brfalse  loc_18E38
0x18d9b  ldarg.0
0x18d9c  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x18da1  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x18da6  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.AppForm::get_CurrentEntity()
0x18dab  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_IsInstanceCustomizable()
0x18db0  brfalse  loc_18E38
0x18db5  ldarg.0
0x18db6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x18dbb  ldstr    aDeleteactionen// "_deleteActionEnabled"
0x18dc0  ldc.i4.1
0x18dc1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x18dc6  ldloc.1
0x18dc7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18dcc  ldarg.0
0x18dcd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x18dd2  ldstr    aMenuitemLabelD// "MenuItem_Label_DeleteObject"
0x18dd7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18ddc  ldc.i4.1
0x18ddd  newarr   [mscorlib]System.Object
0x18de2  dup
0x18de3  ldc.i4.0
0x18de4  ldarg.0
0x18de5  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x18dea  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x18def  callvirt instance int32 Microsoft.Crm.Application.Forms.AppForm::get_EntityTypeCode()
0x18df4  ldc.i4.1
0x18df5  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0x18dfa  stelem.ref
0x18dfb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18e00  ldstr    aOnactionmenucl// "onActionMenuClick('delete', "
0x18e05  ldarg.0
0x18e06  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x18e0b  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x18e10  callvirt instance int32 Microsoft.Crm.Application.Forms.AppForm::get_EntityTypeCode()
0x18e15  stloc.s  5
0x18e17  ldloca.s 5
0x18e19  ldstr    aD// "D"
0x18e1e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18e23  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x18e28  ldstr    asc_11632C// ");"
0x18e2d  call     string [mscorlib]System.String::Concat(string, string, string)
0x18e32  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x18e37  pop
0x18e38  ldarg.0
0x18e39  ldloc.1
0x18e3a  ldc.i4.s 0x20
0x18e3c  call     instance void Microsoft.Crm.Application.Menus.AppMenuBar::RaiseMenuReadyEvent(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu menu, int32 menuId)
0x18e41  ldloc.1
0x18e42  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x18e47  ldarg.0
0x18e48  ldc.i4.4
0x18e49  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormActionParameters actionParameter)
0x18e4e  brfalse  loc_18EFF
0x18e53  ldarg.0
0x18e54  ldarg.0
0x18e55  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x18e5a  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x18e5f  callvirt instance int32 Microsoft.Crm.Application.Forms.AppForm::get_EntityTypeCode()
0x18e64  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::IsClientApiMissingForEntity(int32 EntityTypeCode)
0x18e69  brfalse.s loc_18EB6
0x18e6b  ldloc.1
0x18e6c  ldarg.0
0x18e6d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x18e72  ldstr    aMenuLabelAssig// "Menu_Label_Assign"
0x18e77  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18e7c  ldstr    aMscrmFormactio// "Mscrm.FormAction.assignObject("
0x18e81  ldarg.0
0x18e82  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x18e87  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x18e8c  callvirt instance int32 Microsoft.Crm.Application.Forms.AppForm::get_EntityTypeCode()
0x18e91  stloc.s  5
0x18e93  ldloca.s 5
0x18e95  ldstr    aD// "D"
0x18e9a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18e9f  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x18ea4  ldstr    asc_F5C96// ")"
0x18ea9  call     string [mscorlib]System.String::Concat(string, string, string)
0x18eae  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x18eb3  pop
0x18eb4  br.s     loc_18EFF
0x18eb6  ldloc.1
0x18eb7  ldarg.0
0x18eb8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x18ebd  ldstr    aMenuLabelAssig// "Menu_Label_Assign"
0x18ec2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18ec7  ldstr    aMscrmCommandba_1// "Mscrm.CommandBarActions.assignObject("
0x18ecc  ldarg.0
0x18ecd  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x18ed2  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x18ed7  callvirt instance int32 Microsoft.Crm.Application.Forms.AppForm::get_EntityTypeCode()
0x18edc  stloc.s  5
0x18ede  ldloca.s 5
0x18ee0  ldstr    aD// "D"
0x18ee5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18eea  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x18eef  ldstr    asc_F5C96// ")"
0x18ef4  call     string [mscorlib]System.String::Concat(string, string, string)
0x18ef9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x18efe  pop
0x18eff  ldarg.0
0x18f00  ldc.i4.s 0x10
0x18f02  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::CheckParameter(valuetype Microsoft.Crm.Application.Menus.FormActionParameters actionParameter)
0x18f07  brfalse.s loc_18F52
0x18f09  ldloc.1
0x18f0a  ldarg.0
0x18f0b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x18f10  ldstr    aMenuLabelShare// "Menu_Label_Share"
0x18f15  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18f1a  ldstr    aOnactionmenucl_0// "onActionMenuClick('share', "
0x18f1f  ldarg.0
0x18f20  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x18f25  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x18f2a  callvirt instance int32 Microsoft.Crm.Application.Forms.AppForm::get_EntityTypeCode()
0x18f2f  stloc.s  5
0x18f31  ldloca.s 5
0x18f33  ldstr    aD// "D"
0x18f38  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18f3d  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x18f42  ldstr    asc_F5C96// ")"
0x18f47  call     string [mscorlib]System.String::Concat(string, string, string)
0x18f4c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x18f51  pop
0x18f52  ldarg.0
0x18f53  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x18f58  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x18f5d  callvirt instance int32 Microsoft.Crm.Application.Forms.AppForm::get_EntityTypeCode()
0x18f62  stloc.2
0x18f63  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18f68  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x18f6d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x18f72  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18f77  ldloc.2
0x18f78  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0x18f7d  stloc.3
0x18f7e  ldloc.3
0x18f7f  brfalse.s loc_18FF2
0x18f81  ldloc.3
0x18f82  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCollaboration()
0x18f87  brfalse.s loc_18FF2
0x18f89  ldloc.2
0x18f8a  ldc.i4.s 0x10
0x18f8c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18f91  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18f96  brfalse.s loc_18FF2
0x18f98  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AppendToQueue()
0x18f9d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18fa2  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18fa7  brfalse.s loc_18FF2
0x18fa9  ldloc.1
0x18faa  ldarg.0
0x18fab  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x18fb0  ldstr    aMenuitemLabelA// "MenuItem_Label_AddToQueue"
0x18fb5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18fba  ldstr    aAddtoqueue// "addToQueue("
0x18fbf  ldarg.0
0x18fc0  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x18fc5  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x18fca  callvirt instance int32 Microsoft.Crm.Application.Forms.AppForm::get_EntityTypeCode()
0x18fcf  stloc.s  5
0x18fd1  ldloca.s 5
0x18fd3  ldstr    aD// "D"
0x18fd8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18fdd  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x18fe2  ldstr    asc_F5C96// ")"
0x18fe7  call     string [mscorlib]System.String::Concat(string, string, string)
0x18fec  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x18ff1  pop
0x18ff2  ldloc.3
0x18ff3  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x18ff8  ldstr    aConnectionrole// "connectionrole"
0x18ffd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19002  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19007  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x1900c  bne.un   loc_190E6
0x19011  ldarg.0
0x19012  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x19017  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x1901c  callvirt instance valuetype Microsoft.Crm.Application.Forms.FormState Microsoft.Crm.Application.Forms.AppForm::get_State()
0x19021  ldc.i4.2
0x19022  bne.un   loc_190E6
0x19027  ldarg.0
0x19028  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x1902d  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x19032  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.AppForm::get_Entity()
0x19037  ldstr    aStatecode// "statecode"
0x1903c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19041  castclass [mscorlib]System.String
0x19046  ldstr    aInactive// "Inactive"
0x1904b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19050  brfalse.s loc_1909D
0x19052  ldloc.1
  ... truncated ...
```
