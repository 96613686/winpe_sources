# Microsoft.Crm.Web.Tools.SystemCustomization.DisplayStrings.DisplayStringListPage::ConfigureMenus

- ea: `0xb12b0`
- end: `0xb147e`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.DisplayStrings.DisplayStringListPage::ConfigureMenus`
- size: `462`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xb12b0`

## string_xrefs

- `0xb1325`: `Mscrm.SolutionComponentList.removeSolutionSubcomponent(`
- `0xb1360`: `/_imgs/solution/removecomponent.gif`
- `0xb13ba`: `MenuItem_Label_AddSubcomponents`
- `0xb144c`: `MenuItem_Label_AddSubcomponents`
- `0xb13cc`: `Mscrm.SolutionComponentList.manageSelectedEntitySubComponents(`
- `0xb143c`: `/_imgs/solution/addrequiredcomponents.gif`
- `0xb1456`: `btnAddSubcomponents`
- `0xb131b`: `MenuItem_Label_RemoveComponent`
- `0xb1370`: `Ribbon.Formeditor.Button.RemoveComponent.Description`
- `0xb137a`: `btnRemoveComponent`

## pseudocode

```c

```

## disassembly

```asm
0xb12b0  ldarg.0
0xb12b1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0xb12b6  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::IsManaged()
0xb12bb  brtrue.s loc_B12CA
0xb12bd  ldarg.0
0xb12be  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0xb12c3  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::get_IsParent()
0xb12c8  brfalse.s loc_B12E0
0xb12ca  ldarg.0
0xb12cb  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.Tools.SystemCustomization.DisplayStrings.DisplayStringListPage::gridDisplayStrings
0xb12d0  ldstr    aDisabledblclic// "disableDblClick"
0xb12d5  ldstr    a1// "1"
0xb12da  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0xb12df  ret
0xb12e0  ldloca.s 0
0xb12e2  ldarg.0
0xb12e3  ldfld    string Microsoft.Crm.Web.Tools.SystemCustomization.DisplayStrings.DisplayStringListPage::_entityId
0xb12e8  call     instance void [mscorlib]System.Guid::.ctor(string)
0xb12ed  ldarg.0
0xb12ee  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmMenuBar
0xb12f3  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar
0xb12f8  stloc.1
0xb12f9  ldarg.0
0xb12fa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0xb12ff  ldloc.0
0xb1300  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.SolutionUtil::AreSubcomponentsAddedSeperately(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext, valuetype [mscorlib]System.Guid)
0xb1305  brfalse  loc_B1471
0xb130a  ldarg.0
0xb130b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmMenuBar
0xb1310  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0xb1315  ldarg.0
0xb1316  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb131b  ldstr    aMenuitemLabelR_2// "MenuItem_Label_RemoveComponent"
0xb1320  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb1325  ldstr    aMscrmSolutionc_0// "Mscrm.SolutionComponentList.removeSolut"...
0xb132a  ldc.i4   0x1006
0xb132f  stloc.2
0xb1330  ldloca.s 2
0xb1332  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb1337  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xb133c  callvirt instance string [mscorlib]System.Object::ToString()
0xb1341  ldstr    asc_14E862// ")"
0xb1346  call     string [mscorlib]System.String::Concat(string, string, string)
0xb134b  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xb1350  ldc.i4.1
0xb1351  newarr   [mscorlib]System.Char
0xb1356  dup
0xb1357  ldc.i4.0
0xb1358  ldc.i4.s 0x2F
0xb135a  stelem.i2
0xb135b  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xb1360  ldstr    aImgsSolutionRe// "/_imgs/solution/removecomponent.gif"
0xb1365  call     string [mscorlib]System.String::Concat(string, string)
0xb136a  ldarg.0
0xb136b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb1370  ldstr    aRibbonFormedit_5// "Ribbon.Formeditor.Button.RemoveComponen"...
0xb1375  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb137a  ldstr    aBtnremovecompo// "btnRemoveComponent"
0xb137f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xb1384  pop
0xb1385  ldarg.0
0xb1386  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmMenuBar
0xb138b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0xb1390  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xb1395  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteCustomization()
0xb139a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb139f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb13a4  brfalse  loc_B1461
0xb13a9  ldarg.0
0xb13aa  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmMenuBar
0xb13af  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0xb13b4  ldarg.0
0xb13b5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb13ba  ldstr    aMenuitemLabelA_0// "MenuItem_Label_AddSubcomponents"
0xb13bf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb13c4  ldc.i4.7
0xb13c5  newarr   [mscorlib]System.Object
0xb13ca  dup
0xb13cb  ldc.i4.0
0xb13cc  ldstr    aMscrmSolutionc_2// "Mscrm.SolutionComponentList.manageSelec"...
0xb13d1  stelem.ref
0xb13d2  dup
0xb13d3  ldc.i4.1
0xb13d4  ldc.i4   0x2649
0xb13d9  stloc.2
0xb13da  ldloca.s 2
0xb13dc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb13e1  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xb13e6  callvirt instance string [mscorlib]System.Object::ToString()
0xb13eb  stelem.ref
0xb13ec  dup
0xb13ed  ldc.i4.2
0xb13ee  ldstr    asc_15BF70// ",'"
0xb13f3  stelem.ref
0xb13f4  dup
0xb13f5  ldc.i4.3
0xb13f6  ldloc.0
0xb13f7  box      [mscorlib]System.Guid
0xb13fc  stelem.ref
0xb13fd  dup
0xb13fe  ldc.i4.4
0xb13ff  ldstr    asc_14EC6A// "','"
0xb1404  stelem.ref
0xb1405  dup
0xb1406  ldc.i4.5
0xb1407  ldc.i4   0x1006
0xb140c  stloc.2
0xb140d  ldloca.s 2
0xb140f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb1414  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xb1419  stelem.ref
0xb141a  dup
0xb141b  ldc.i4.6
0xb141c  ldstr    asc_1235BC// "')"
0xb1421  stelem.ref
0xb1422  call     string [mscorlib]System.String::Concat(object[])
0xb1427  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xb142c  ldc.i4.1
0xb142d  newarr   [mscorlib]System.Char
0xb1432  dup
0xb1433  ldc.i4.0
0xb1434  ldc.i4.s 0x2F
0xb1436  stelem.i2
0xb1437  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xb143c  ldstr    aImgsSolutionAd// "/_imgs/solution/addrequiredcomponents.g"...
0xb1441  call     string [mscorlib]System.String::Concat(string, string)
0xb1446  ldarg.0
0xb1447  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb144c  ldstr    aMenuitemLabelA_0// "MenuItem_Label_AddSubcomponents"
0xb1451  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb1456  ldstr    aBtnaddsubcompo// "btnAddSubcomponents"
0xb145b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xb1460  pop
0xb1461  ldarg.0
0xb1462  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmMenuBar
0xb1467  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0xb146c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xb1471  ldloc.1
0xb1472  ldarg.0
0xb1473  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.Tools.SystemCustomization.DisplayStrings.DisplayStringListPage::gridDisplayStrings
0xb1478  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar::Execute(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid)
0xb147d  ret
```
