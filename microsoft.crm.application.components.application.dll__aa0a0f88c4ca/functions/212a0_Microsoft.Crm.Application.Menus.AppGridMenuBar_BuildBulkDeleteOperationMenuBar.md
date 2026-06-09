# Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildBulkDeleteOperationMenuBar

- ea: `0x212a0`
- end: `0x2149a`
- name: `Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildBulkDeleteOperationMenuBar`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1b610`

## callees

- `0x19fd0`
- `0x1b380`
- `0x1c010`
- `0x212a0`
- `0x23fe0`
- `0x24210`
- `0x242b0`
- `0x46e30`

## string_xrefs

- `0x212af`: `LOCID_POSTPONE_BULKDELETE_JOB`
- `0x212ba`: `Error_Message.BulkdeleteJob.State.Completed`
- `0x212e9`: `tools/bulkdeletewizard/bulkdeletewizard.aspx`
- `0x21334`: `; var url = Mscrm.CrmUri.create('/WebWizard/WizardContainer.aspx?WizardId=A50E9478-8EC9-45ab-B927-FDFFF64A0729');Xrm.Internal.openDialog(url.toString(), options, null, null, function(){auto(`
- `0x213cc`: `_MIopenStdDlgBulkDeleteWizard`
- `0x21430`: `Menu_Label_Completed_AsyncOperation`
- `0x2143a`: `bulkDeleteCancel`
- `0x2144c`: `Menu_Label_Ready_AsyncOperation`
- `0x21456`: `bulkDeleteResume`
- `0x21472`: `bulkDeletePostpone`
- `0x2148e`: `bulkDeletePause`

## pseudocode

```c

```

## disassembly

```asm
0x212a0  ldarg.0
0x212a1  ldc.i4.0
0x212a2  ldc.i4.0
0x212a3  ldc.i4.1
0x212a4  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport)
0x212a9  ldarg.0
0x212aa  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x212af  ldstr    aLocidPostponeB// "LOCID_POSTPONE_BULKDELETE_JOB"
0x212b4  ldarg.0
0x212b5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x212ba  ldstr    aErrorMessageBu// "Error_Message.BulkdeleteJob.State.Compl"...
0x212bf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x212c4  ldc.i4.0
0x212c5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x212ca  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x212cf  brfalse  loc_213FD
0x212d4  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_BulkDelete()
0x212d9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x212de  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x212e3  brfalse  loc_213FD
0x212e8  ldarg.0
0x212e9  ldstr    aToolsBulkdelet// "tools/bulkdeletewizard/bulkdeletewizard"...
0x212ee  call     instance valuetype WindowSize Microsoft.Crm.Application.Menus.AppGridMenuBar::GetWindowSize(string url)
0x212f3  stloc.0
0x212f4  ldc.i4.7
0x212f5  newarr   [mscorlib]System.Object
0x212fa  dup
0x212fb  ldc.i4.0
0x212fc  ldstr    aVarOptionsNewX// "var options = new Xrm.DialogOptions();o"...
0x21301  stelem.ref
0x21302  dup
0x21303  ldc.i4.1
0x21304  ldloca.s 0
0x21306  ldflda   int32 WindowSize::Width
0x2130b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21310  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x21315  stelem.ref
0x21316  dup
0x21317  ldc.i4.2
0x21318  ldstr    aOptionsHeight// ";options.height = "
0x2131d  stelem.ref
0x2131e  dup
0x2131f  ldc.i4.3
0x21320  ldloca.s 0
0x21322  ldflda   int32 WindowSize::Height
0x21327  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2132c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x21331  stelem.ref
0x21332  dup
0x21333  ldc.i4.4
0x21334  ldstr    aVarUrlMscrmCrm_0// "; var url = Mscrm.CrmUri.create('/WebWi"...
0x21339  stelem.ref
0x2133a  dup
0x2133b  ldc.i4.5
0x2133c  ldc.i4   0x125C
0x21341  box      [mscorlib]System.Int32
0x21346  stelem.ref
0x21347  dup
0x21348  ldc.i4.6
0x21349  ldstr    asc_11B756// ");});"
0x2134e  stelem.ref
0x2134f  call     string [mscorlib]System.String::Concat(object[])
0x21354  stloc.1
0x21355  ldarg.0
0x21356  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x2135b  ldc.i4.1
0x2135c  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0x21361  stloc.2
0x21362  ldarg.0
0x21363  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x21368  ldc.i4.0
0x21369  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2136e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x21373  stloc.3
0x21374  ldarg.0
0x21375  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x2137a  ldstr    aMenuitemLabelN// "MenuItem_Label_New"
0x2137f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21384  stloc.s  4
0x21386  ldarg.0
0x21387  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x2138c  ldstr    aMenuitemToolti_0// "MenuItem_ToolTip_NewObject"
0x21391  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21396  ldc.i4.1
0x21397  newarr   [mscorlib]System.Object
0x2139c  dup
0x2139d  ldc.i4.0
0x2139e  ldloc.2
0x2139f  ldarg.0
0x213a0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x213a5  ldstr    aMenuitemToolti_1// "MenuItem_ToolTip_NewObject_Casing"
0x213aa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x213af  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetCasedDisplayText(string, string)
0x213b4  stelem.ref
0x213b5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x213ba  stloc.s  5
0x213bc  ldarg.0
0x213bd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x213c2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x213c7  ldc.i4.0
0x213c8  ldloc.s  4
0x213ca  ldloc.s  5
0x213cc  ldstr    aMiopenstddlgbu// "_MIopenStdDlgBulkDeleteWizard"
0x213d1  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor(string, string, string)
0x213d6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Insert(int32, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x213db  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x213e0  dup
0x213e1  ldloc.1
0x213e2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x213e7  dup
0x213e8  ldloc.s  5
0x213ea  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x213ef  dup
0x213f0  ldloc.s  4
0x213f2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x213f7  ldloc.3
0x213f8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x213fd  ldarg.0
0x213fe  ldarg.0
0x213ff  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x21404  ldstr    aMenuLabelModif// "Menu_Label_ModifyRecurrence"
0x21409  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2140e  ldstr    aModifyrecurren// "modifyrecurrence"
0x21413  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x21418  pop
0x21419  ldarg.0
0x2141a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x2141f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x21424  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x21429  ldarg.0
0x2142a  ldarg.0
0x2142b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x21430  ldstr    aMenuLabelCompl// "Menu_Label_Completed_AsyncOperation"
0x21435  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2143a  ldstr    aBulkdeletecanc// "bulkDeleteCancel"
0x2143f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x21444  pop
0x21445  ldarg.0
0x21446  ldarg.0
0x21447  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x2144c  ldstr    aMenuLabelReady// "Menu_Label_Ready_AsyncOperation"
0x21451  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21456  ldstr    aBulkdeleteresu// "bulkDeleteResume"
0x2145b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x21460  pop
0x21461  ldarg.0
0x21462  ldarg.0
0x21463  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x21468  ldstr    aMenuLabelSuspe// "Menu_Label_Suspended_AsyncOperation"
0x2146d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21472  ldstr    aBulkdeletepost// "bulkDeletePostpone"
0x21477  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x2147c  pop
0x2147d  ldarg.0
0x2147e  ldarg.0
0x2147f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x21484  ldstr    aMenuLabelPause// "Menu_Label_Paused_AsyncOperation"
0x21489  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2148e  ldstr    aBulkdeletepaus// "bulkDeletePause"
0x21493  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x21498  pop
0x21499  ret
```
