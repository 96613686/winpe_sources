# Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildEquipmentMenuBar

- ea: `0x1e7e0`
- end: `0x1ea29`
- name: `Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildEquipmentMenuBar`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1b610`

## callees

- `0x19fd0`
- `0x1a490`
- `0x1a510`
- `0x1a5d0`
- `0x1b410`
- `0x1c010`
- `0x1e7e0`
- `0x1ffb0`
- `0x24210`

## string_xrefs

- `0x1e850`: `MenuItem_Label_Delete`
- `0x1e803`: `delete`
- `0x1e820`: `/_imgs/ico_16_delete.gif`
- `0x1e83a`: `_MBdoActioncrmGrid4000delete`

## pseudocode

```c

```

## disassembly

```asm
0x1e7e0  ldarg.0
0x1e7e1  call     instance bool Microsoft.Crm.Application.Menus.AppGridMenuBar::get_IsCustomRelationship()
0x1e7e6  brtrue   loc_1EA19
0x1e7eb  ldarg.0
0x1e7ec  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1e7f1  ldc.i4   0x10000
0x1e7f6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e7fb  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e800  brfalse.s loc_1E87B
0x1e802  ldarg.0
0x1e803  ldstr    aDelete// "delete"
0x1e808  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildDoActionScript(string action)
0x1e80d  stloc.1
0x1e80e  ldarg.0
0x1e80f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_deleteButton
0x1e814  ldloc.1
0x1e815  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x1e81a  ldarg.0
0x1e81b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_deleteButton
0x1e820  ldstr    aImgsIco16Delet// "/_imgs/ico_16_delete.gif"
0x1e825  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e82a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e82f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x1e834  ldarg.0
0x1e835  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_deleteButton
0x1e83a  ldstr    aMbdoactioncrmg// "_MBdoActioncrmGrid4000delete"
0x1e83f  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1e844  ldarg.0
0x1e845  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_deleteButton
0x1e84a  ldarg.0
0x1e84b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1e850  ldstr    aMenuitemLabelD_1// "MenuItem_Label_Delete"
0x1e855  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e85a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x1e85f  ldarg.0
0x1e860  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_deleteButton
0x1e865  ldc.i4.1
0x1e866  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x1e86b  ldarg.0
0x1e86c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x1e871  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x1e876  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x1e87b  ldarg.0
0x1e87c  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1e881  ldc.i4.2
0x1e882  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e887  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e88c  brfalse  loc_1E916
0x1e891  ldarg.0
0x1e892  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x1e897  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x1e89c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x1e8a1  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x1e8a6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x1e8ab  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x1e8b0  dup
0x1e8b1  ldarg.0
0x1e8b2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1e8b7  ldstr    aMenuitemLabelC_5// "MenuItem_Label_ChangeBusiness"
0x1e8bc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e8c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x1e8c6  ldc.i4.5
0x1e8c7  newarr   [mscorlib]System.String
0x1e8cc  dup
0x1e8cd  ldc.i4.0
0x1e8ce  ldstr    aDoaction// "doAction("
0x1e8d3  stelem.ref
0x1e8d4  dup
0x1e8d5  ldc.i4.1
0x1e8d6  ldarg.0
0x1e8d7  ldfld    string Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridClientId
0x1e8dc  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1e8e1  stelem.ref
0x1e8e2  dup
0x1e8e3  ldc.i4.2
0x1e8e4  ldstr    asc_117A44// ", "
0x1e8e9  stelem.ref
0x1e8ea  dup
0x1e8eb  ldc.i4.3
0x1e8ec  ldc.i4   0xFA0
0x1e8f1  stloc.2
0x1e8f2  ldloca.s 2
0x1e8f4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e8f9  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1e8fe  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1e903  stelem.ref
0x1e904  dup
0x1e905  ldc.i4.4
0x1e906  ldstr    aChangeorg_0// ", 'changeorg')"
0x1e90b  stelem.ref
0x1e90c  call     string [mscorlib]System.String::Concat(string[])
0x1e911  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x1e916  ldc.i4   0xFA0
0x1e91b  ldc.i4.s 0x20
0x1e91d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e922  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e927  brfalse  loc_1EA19
0x1e92c  ldarg.0
0x1e92d  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridType
0x1e932  ldc.i4.1
0x1e933  bne.un.s loc_1E9AA
0x1e935  ldarg.0
0x1e936  call     instance int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityType()
0x1e93b  ldc.i4.s 0xA
0x1e93d  bne.un   loc_1EA19
0x1e942  ldarg.0
0x1e943  ldc.i4.7
0x1e944  newarr   [mscorlib]System.String
0x1e949  dup
0x1e94a  ldc.i4.0
0x1e94b  ldstr    aLocaddrelatedt// "locAddRelatedToNonForm("
0x1e950  stelem.ref
0x1e951  dup
0x1e952  ldc.i4.1
0x1e953  ldc.i4   0xFA0
0x1e958  stloc.2
0x1e959  ldloca.s 2
0x1e95b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e960  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1e965  stelem.ref
0x1e966  dup
0x1e967  ldc.i4.2
0x1e968  ldstr    asc_11387C// ","
0x1e96d  stelem.ref
0x1e96e  dup
0x1e96f  ldc.i4.3
0x1e970  ldc.i4.s 0xA
0x1e972  stloc.2
0x1e973  ldloca.s 2
0x1e975  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e97a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1e97f  stelem.ref
0x1e980  dup
0x1e981  ldc.i4.4
0x1e982  ldstr    asc_11387C// ","
0x1e987  stelem.ref
0x1e988  dup
0x1e989  ldc.i4.5
0x1e98a  ldarg.0
0x1e98b  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityId()
0x1e990  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1e995  stelem.ref
0x1e996  dup
0x1e997  ldc.i4.6
0x1e998  ldstr    asc_117846// ", '')"
0x1e99d  stelem.ref
0x1e99e  call     string [mscorlib]System.String::Concat(string[])
0x1e9a3  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton(string onclickScript)
0x1e9a8  br.s     loc_1EA19
0x1e9aa  ldarg.0
0x1e9ab  ldc.i4.7
0x1e9ac  newarr   [mscorlib]System.String
0x1e9b1  dup
0x1e9b2  ldc.i4.0
0x1e9b3  ldstr    aLocaddrelatedt// "locAddRelatedToNonForm("
0x1e9b8  stelem.ref
0x1e9b9  dup
0x1e9ba  ldc.i4.1
0x1e9bb  ldc.i4   0xFA0
0x1e9c0  stloc.2
0x1e9c1  ldloca.s 2
0x1e9c3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e9c8  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1e9cd  stelem.ref
0x1e9ce  dup
0x1e9cf  ldc.i4.2
0x1e9d0  ldstr    asc_11387C// ","
0x1e9d5  stelem.ref
0x1e9d6  dup
0x1e9d7  ldc.i4.3
0x1e9d8  ldc.i4.s 0xA
0x1e9da  stloc.2
0x1e9db  ldloca.s 2
0x1e9dd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e9e2  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1e9e7  stelem.ref
0x1e9e8  dup
0x1e9e9  ldc.i4.4
0x1e9ea  ldstr    asc_11387C// ","
0x1e9ef  stelem.ref
0x1e9f0  dup
0x1e9f1  ldc.i4.5
0x1e9f2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x1e9f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_BusinessId()
0x1e9fc  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x1ea01  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1ea06  stelem.ref
0x1ea07  dup
0x1ea08  ldc.i4.6
0x1ea09  ldstr    asc_117846// ", '')"
0x1ea0e  stelem.ref
0x1ea0f  call     string [mscorlib]System.String::Concat(string[])
0x1ea14  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton(string onclickScript)
0x1ea19  ldc.i4   0x400
0x1ea1e  stloc.0
0x1ea1f  ldarg.0
0x1ea20  ldloc.0
0x1ea21  ldc.i4.0
0x1ea22  ldc.i4.1
0x1ea23  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport)
0x1ea28  ret
```
