# Microsoft.Crm.Web.Tools.SystemCustomization.HierarchyRules.HierarchyRulesListPage::ConfigureMenuButtonSubComponents

- ea: `0xac240`
- end: `0xac3b9`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.HierarchyRules.HierarchyRulesListPage::ConfigureMenuButtonSubComponents`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xac1e0`

## callees

- `0xac240`

## string_xrefs

- `0xac27c`: `Mscrm.SolutionComponentList.removeSolutionSubcomponent(`
- `0xac2b7`: `/_imgs/solution/removecomponent.gif`
- `0xac307`: `MenuItem_Label_AddSubcomponents`
- `0xac3a3`: `MenuItem_Label_AddSubcomponents`
- `0xac319`: `Mscrm.SolutionComponentList.manageSelectedEntitySubComponents(`
- `0xac393`: `/_imgs/solution/addrequiredcomponents.gif`
- `0xac3ad`: `btnAddSubcomponents`
- `0xac272`: `MenuItem_Label_RemoveComponent`
- `0xac2c7`: `Ribbon.Formeditor.Button.RemoveComponent.Description`
- `0xac2d1`: `btnRemoveComponent`

## pseudocode

```c

```

## disassembly

```asm
0xac240  ldarg.0
0xac241  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0xac246  ldarg.0
0xac247  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.HierarchyRules.HierarchyRulesListPage::_entityMD
0xac24c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0xac251  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.SolutionUtil::AreSubcomponentsAddedSeperately(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext, valuetype [mscorlib]System.Guid)
0xac256  brfalse  loc_AC3B8
0xac25b  ldarg.0
0xac25c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.HierarchyRules.HierarchyRulesListPage::menuBar
0xac261  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xac266  ldarg.0
0xac267  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.HierarchyRules.HierarchyRulesListPage::menuBar
0xac26c  ldarg.0
0xac26d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xac272  ldstr    aMenuitemLabelR_2// "MenuItem_Label_RemoveComponent"
0xac277  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xac27c  ldstr    aMscrmSolutionc_0// "Mscrm.SolutionComponentList.removeSolut"...
0xac281  ldc.i4   0x2288
0xac286  stloc.0
0xac287  ldloca.s 0
0xac289  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xac28e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xac293  callvirt instance string [mscorlib]System.Object::ToString()
0xac298  ldstr    asc_14E862// ")"
0xac29d  call     string [mscorlib]System.String::Concat(string, string, string)
0xac2a2  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xac2a7  ldc.i4.1
0xac2a8  newarr   [mscorlib]System.Char
0xac2ad  dup
0xac2ae  ldc.i4.0
0xac2af  ldc.i4.s 0x2F
0xac2b1  stelem.i2
0xac2b2  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xac2b7  ldstr    aImgsSolutionRe// "/_imgs/solution/removecomponent.gif"
0xac2bc  call     string [mscorlib]System.String::Concat(string, string)
0xac2c1  ldarg.0
0xac2c2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xac2c7  ldstr    aRibbonFormedit_5// "Ribbon.Formeditor.Button.RemoveComponen"...
0xac2cc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xac2d1  ldstr    aBtnremovecompo// "btnRemoveComponent"
0xac2d6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xac2db  pop
0xac2dc  ldarg.0
0xac2dd  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.HierarchyRules.HierarchyRulesListPage::menuBar
0xac2e2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xac2e7  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteCustomization()
0xac2ec  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xac2f1  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xac2f6  brfalse  loc_AC3B8
0xac2fb  ldarg.0
0xac2fc  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.HierarchyRules.HierarchyRulesListPage::menuBar
0xac301  ldarg.0
0xac302  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xac307  ldstr    aMenuitemLabelA_0// "MenuItem_Label_AddSubcomponents"
0xac30c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xac311  ldc.i4.7
0xac312  newarr   [mscorlib]System.Object
0xac317  dup
0xac318  ldc.i4.0
0xac319  ldstr    aMscrmSolutionc_2// "Mscrm.SolutionComponentList.manageSelec"...
0xac31e  stelem.ref
0xac31f  dup
0xac320  ldc.i4.1
0xac321  ldc.i4   0x2649
0xac326  stloc.0
0xac327  ldloca.s 0
0xac329  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xac32e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xac333  callvirt instance string [mscorlib]System.Object::ToString()
0xac338  stelem.ref
0xac339  dup
0xac33a  ldc.i4.2
0xac33b  ldstr    asc_15BF70// ",'"
0xac340  stelem.ref
0xac341  dup
0xac342  ldc.i4.3
0xac343  ldarg.0
0xac344  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.HierarchyRules.HierarchyRulesListPage::_entityMD
0xac349  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0xac34e  box      [mscorlib]System.Guid
0xac353  stelem.ref
0xac354  dup
0xac355  ldc.i4.4
0xac356  ldstr    asc_14EC6A// "','"
0xac35b  stelem.ref
0xac35c  dup
0xac35d  ldc.i4.5
0xac35e  ldc.i4   0x2288
0xac363  stloc.0
0xac364  ldloca.s 0
0xac366  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xac36b  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xac370  stelem.ref
0xac371  dup
0xac372  ldc.i4.6
0xac373  ldstr    asc_1235BC// "')"
0xac378  stelem.ref
0xac379  call     string [mscorlib]System.String::Concat(object[])
0xac37e  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xac383  ldc.i4.1
0xac384  newarr   [mscorlib]System.Char
0xac389  dup
0xac38a  ldc.i4.0
0xac38b  ldc.i4.s 0x2F
0xac38d  stelem.i2
0xac38e  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xac393  ldstr    aImgsSolutionAd// "/_imgs/solution/addrequiredcomponents.g"...
0xac398  call     string [mscorlib]System.String::Concat(string, string)
0xac39d  ldarg.0
0xac39e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xac3a3  ldstr    aMenuitemLabelA_0// "MenuItem_Label_AddSubcomponents"
0xac3a8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xac3ad  ldstr    aBtnaddsubcompo// "btnAddSubcomponents"
0xac3b2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xac3b7  pop
0xac3b8  ret
```
