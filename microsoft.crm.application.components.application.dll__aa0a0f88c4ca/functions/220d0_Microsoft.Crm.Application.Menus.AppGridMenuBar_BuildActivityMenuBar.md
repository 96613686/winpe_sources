# Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildActivityMenuBar

- ea: `0x220d0`
- end: `0x22307`
- name: `Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildActivityMenuBar`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b610`

## callees

- `0x19f10`
- `0x19fd0`
- `0x1a490`
- `0x1a5c0`
- `0x1a5d0`
- `0x1a5f0`
- `0x1b410`
- `0x1c010`
- `0x220d0`
- `0x22310`
- `0x24210`
- `0x46e30`

## string_xrefs

- `0x2221b`: `RunFunctionFromParentOrSelf('locAssocObj',Task,'subtype=planningtasks',`
- `0x22286`: `Tab_Label_New_PlanningTask_Tooltip`
- `0x222cd`: `MenuItem_Label_CloseTemplate`
- `0x222f7`: `changeTaskstate`

## pseudocode

```c

```

## disassembly

```asm
0x220d0  ldarg.0
0x220d1  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppGridMenuBar::_parentEntityAccessRights
0x220d6  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanAppendTo()
0x220db  brtrue.s loc_220ED
0x220dd  ldc.i4   0x440
0x220e2  ldarg.0
0x220e3  call     instance int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityType()
0x220e8  bne.un   loc_22180
0x220ed  ldarg.0
0x220ee  ldfld    bool Microsoft.Crm.Application.Menus.AppGridMenuBar::_buttonNew
0x220f3  brfalse  loc_22180
0x220f8  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateActivity()
0x220fd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x22102  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x22107  brfalse.s loc_22180
0x22109  ldarg.0
0x2210a  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode Microsoft.Crm.Application.Menus.AppGridMenuBar::get_GridType()
0x2210f  brfalse.s loc_22137
0x22111  ldarg.0
0x22112  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode Microsoft.Crm.Application.Menus.AppGridMenuBar::get_GridType()
0x22117  brfalse.s loc_22180
0x22119  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AppendActivity()
0x2211e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x22123  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x22128  brfalse.s loc_22180
0x2212a  ldarg.0
0x2212b  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Menus.AppGridMenuBar::_parentEntityAccessRights
0x22130  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanAppendTo()
0x22135  brfalse.s loc_22180
0x22137  ldarg.0
0x22138  call     instance int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityType()
0x2213d  ldc.i4   0x1132
0x22142  bne.un.s loc_2214B
0x22144  ldarg.0
0x22145  ldc.i4.0
0x22146  stfld    bool Microsoft.Crm.Application.Menus.AppGridMenuBar::_buttonNew
0x2214b  ldarg.0
0x2214c  ldfld    bool Microsoft.Crm.Application.Menus.AppGridMenuBar::_buttonNew
0x22151  brfalse.s loc_22180
0x22153  ldarg.0
0x22154  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x22159  ldc.i4   0x1068
0x2215e  beq.s    loc_22168
0x22160  ldarg.0
0x22161  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode Microsoft.Crm.Application.Menus.AppGridMenuBar::get_GridType()
0x22166  brtrue.s loc_2217A
0x22168  ldarg.0
0x22169  ldc.i4   0x1068
0x2216e  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Script::BuildOpenObject(int32)
0x22173  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton(string onclickScript)
0x22178  br.s     loc_22180
0x2217a  ldarg.0
0x2217b  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton()
0x22180  ldc.i4.s 0x20
0x22182  stloc.0
0x22183  ldarg.0
0x22184  ldfld    bool Microsoft.Crm.Application.Menus.AppGridMenuBar::_buttonNew
0x22189  brtrue.s loc_2219B
0x2218b  ldarg.0
0x2218c  ldfld    bool Microsoft.Crm.Application.Menus.AppGridMenuBar::_buttonExport
0x22191  brtrue.s loc_2219B
0x22193  ldarg.0
0x22194  ldfld    bool Microsoft.Crm.Application.Menus.AppGridMenuBar::_buttonPrint
0x22199  brfalse.s loc_221BD
0x2219b  ldarg.0
0x2219c  call     instance int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityType()
0x221a1  ldc.i4   0x1132
0x221a6  bne.un.s loc_221B0
0x221a8  ldc.i4   0x410
0x221ad  stloc.0
0x221ae  br.s     loc_221BD
0x221b0  ldarg.0
0x221b1  ldarg.0
0x221b2  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x221b7  call     instance valuetype Microsoft.Crm.Application.Menus.GridActionParameters Microsoft.Crm.Application.Menus.AppGridMenuBar::GetValidActivityGridActions(int32 activityObjectTypeCode)
0x221bc  stloc.0
0x221bd  ldarg.0
0x221be  ldloc.0
0x221bf  ldc.i4.0
0x221c0  ldc.i4.1
0x221c1  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport)
0x221c6  ldarg.0
0x221c7  call     instance int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityType()
0x221cc  ldc.i4   0x1130
0x221d1  bne.un   loc_22306
0x221d6  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AppendToCampaign()
0x221db  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x221e0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x221e5  brfalse  loc_22295
0x221ea  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AppendActivity()
0x221ef  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x221f4  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x221f9  brfalse  loc_22295
0x221fe  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateActivity()
0x22203  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x22208  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2220d  brfalse  loc_22295
0x22212  ldarg.0
0x22213  ldc.i4.5
0x22214  newarr   [mscorlib]System.String
0x22219  dup
0x2221a  ldc.i4.0
0x2221b  ldstr    aRunfunctionfro_12// "RunFunctionFromParentOrSelf('locAssocOb"...
0x22220  stelem.ref
0x22221  dup
0x22222  ldc.i4.1
0x22223  ldarg.0
0x22224  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Menus.AppGridMenuBar::_grid
0x22229  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x2222e  ldstr    aRelname// "relName"
0x22233  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x22238  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x2223d  stelem.ref
0x2223e  dup
0x2223f  ldc.i4.2
0x22240  ldstr    asc_117A44// ", "
0x22245  stelem.ref
0x22246  dup
0x22247  ldc.i4.3
0x22248  ldarg.0
0x22249  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Menus.AppGridMenuBar::_grid
0x2224e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x22253  ldstr    aRoleord// "roleOrd"
0x22258  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2225d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x22262  stelem.ref
0x22263  dup
0x22264  ldc.i4.4
0x22265  ldstr    asc_11632C// ");"
0x2226a  stelem.ref
0x2226b  call     string [mscorlib]System.String::Concat(string[])
0x22270  ldarg.0
0x22271  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x22276  ldstr    aTabLabelNew// "Tab_Label_New"
0x2227b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22280  ldarg.0
0x22281  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x22286  ldstr    aTabLabelNewPla// "Tab_Label_New_PlanningTask_Tooltip"
0x2228b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22290  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::AddNewButton(string onclickScript, string buttonTitle, string buttonTip)
0x22295  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteActivity()
0x2229a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2229f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x222a4  brfalse.s loc_22306
0x222a6  ldarg.0
0x222a7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x222ac  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x222b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x222b6  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x222bb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x222c0  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x222c5  stloc.1
0x222c6  ldloc.1
0x222c7  ldarg.0
0x222c8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x222cd  ldstr    aMenuitemLabelC_8// "MenuItem_Label_CloseTemplate"
0x222d2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x222d7  ldc.i4.1
0x222d8  newarr   [mscorlib]System.Object
0x222dd  dup
0x222de  ldc.i4.0
0x222df  ldc.i4   0x1074
0x222e4  ldc.i4.1
0x222e5  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0x222ea  stelem.ref
0x222eb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x222f0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x222f5  ldloc.1
0x222f6  ldarg.0
0x222f7  ldstr    aChangetaskstat// "changeTaskstate"
0x222fc  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildDoActionScript(string action)
0x22301  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x22306  ret
```
