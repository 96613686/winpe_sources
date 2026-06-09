# Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildImportMenuBar

- ea: `0x20370`
- end: `0x20572`
- name: `Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildImportMenuBar`
- size: `514`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1b610`

## callees

- `0x19fd0`
- `0x1a5f0`
- `0x1b410`
- `0x1c010`
- `0x20370`
- `0x23fe0`
- `0x24210`

## string_xrefs

- `0x204af`: `delete`
- `0x20450`: `; var url = Mscrm.CrmUri.create('/WebWizard/WizardContainer.aspx?WizardId=A0E9DC09-8730-4C97-A8B9-6F585C0C16F7');Xrm.Internal.openDialog(url.toString(), options, null, null, function(){auto(`
- `0x2049f`: `MenuItem_Label_DeletePopup`
- `0x204ee`: `MenuItem_Label_DeleteImported`
- `0x204fe`: `deleteimportedrecords`
- `0x2052e`: `MenuItem_Label_DeleteAllImported`
- `0x2053e`: `deleteallimportedrecords`

## pseudocode

```c

```

## disassembly

```asm
0x20370  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x20375  brfalse  loc_2054D
0x2037a  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateImport()
0x2037f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x20384  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x20389  brfalse  loc_20478
0x2038e  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_DeleteImport()
0x20393  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x20398  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2039d  brfalse  loc_20478
0x203a2  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadImport()
0x203a7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x203ac  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x203b1  brfalse  loc_20478
0x203b6  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteImport()
0x203bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x203c0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x203c5  brfalse  loc_20478
0x203ca  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateImportMap()
0x203cf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x203d4  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x203d9  brfalse  loc_20478
0x203de  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadImportMap()
0x203e3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x203e8  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x203ed  brfalse  loc_20478
0x203f2  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AppendToImportMap()
0x203f7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x203fc  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x20401  brfalse.s loc_20478
0x20403  ldarg.0
0x20404  ldstr    aToolsImportwiz// "tools/importwizard/importwizard.aspx"
0x20409  call     instance valuetype WindowSize Microsoft.Crm.Application.Menus.AppGridMenuBar::GetWindowSize(string url)
0x2040e  stloc.1
0x2040f  ldarg.0
0x20410  ldc.i4.7
0x20411  newarr   [mscorlib]System.Object
0x20416  dup
0x20417  ldc.i4.0
0x20418  ldstr    aVarOptionsNewX// "var options = new Xrm.DialogOptions();o"...
0x2041d  stelem.ref
0x2041e  dup
0x2041f  ldc.i4.1
0x20420  ldloca.s 1
0x20422  ldflda   int32 WindowSize::Width
0x20427  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2042c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x20431  stelem.ref
0x20432  dup
0x20433  ldc.i4.2
0x20434  ldstr    aOptionsHeight// ";options.height = "
0x20439  stelem.ref
0x2043a  dup
0x2043b  ldc.i4.3
0x2043c  ldloca.s 1
0x2043e  ldflda   int32 WindowSize::Height
0x20443  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20448  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2044d  stelem.ref
0x2044e  dup
0x2044f  ldc.i4.4
0x20450  ldstr    aVarUrlMscrmCrm// "; var url = Mscrm.CrmUri.create('/WebWi"...
0x20455  stelem.ref
0x20456  dup
0x20457  ldc.i4.5
0x20458  ldarg.0
0x20459  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x2045e  box      [mscorlib]System.Int32
0x20463  stelem.ref
0x20464  dup
0x20465  ldc.i4.6
0x20466  ldstr    asc_11B756// ");});"
0x2046b  stelem.ref
0x2046c  call     string [mscorlib]System.String::Concat(object[])
0x20471  ldnull
0x20472  ldnull
0x20473  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton(string onclickScript, string buttonTitle, string buttonTip)
0x20478  ldarg.0
0x20479  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x2047e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x20483  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x20488  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::.ctor()
0x2048d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x20492  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup
0x20497  stloc.0
0x20498  ldloc.0
0x20499  ldarg.0
0x2049a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x2049f  ldstr    aMenuitemLabelD_10// "MenuItem_Label_DeletePopup"
0x204a4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x204a9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x204ae  ldloc.0
0x204af  ldstr    aDelete// "delete"
0x204b4  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x204b9  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_BulkDelete()
0x204be  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x204c3  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x204c8  brfalse  loc_2054D
0x204cd  ldloc.0
0x204ce  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x204d3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x204d8  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x204dd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x204e2  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x204e7  dup
0x204e8  ldarg.0
0x204e9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x204ee  ldstr    aMenuitemLabelD_11// "MenuItem_Label_DeleteImported"
0x204f3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x204f8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x204fd  ldarg.0
0x204fe  ldstr    aDeleteimported// "deleteimportedrecords"
0x20503  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildDoActionScript(string action)
0x20508  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x2050d  ldloc.0
0x2050e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x20513  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x20518  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x2051d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x20522  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x20527  dup
0x20528  ldarg.0
0x20529  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x2052e  ldstr    aMenuitemLabelD_12// "MenuItem_Label_DeleteAllImported"
0x20533  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x20538  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x2053d  ldarg.0
0x2053e  ldstr    aDeleteallimpor// "deleteallimportedrecords"
0x20543  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildDoActionScript(string action)
0x20548  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x2054d  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_DeleteImport()
0x20552  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x20557  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2055c  brfalse.s loc_20568
0x2055e  ldarg.0
0x2055f  ldc.i4.7
0x20560  ldc.i4.0
0x20561  ldc.i4.1
0x20562  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport)
0x20567  ret
0x20568  ldarg.0
0x20569  ldc.i4.5
0x2056a  ldc.i4.0
0x2056b  ldc.i4.1
0x2056c  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport)
0x20571  ret
```
