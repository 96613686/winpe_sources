# Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.BusinessRulesListPageHandler::ConfigureMenuButtonSubComponents

- ea: `0xb1fc0`
- end: `0xb2121`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.BusinessRulesListPageHandler::ConfigureMenuButtonSubComponents`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0xb1f50`

## callees

- `0xb1e20`
- `0xb1fc0`

## string_xrefs

- `0xb1ffb`: `Mscrm.SolutionComponentList.removeSolutionSubcomponent(`
- `0xb2036`: `/_imgs/solution/removecomponent.gif`
- `0xb207a`: `MenuItem_Label_AddSubcomponents`
- `0xb210b`: `MenuItem_Label_AddSubcomponents`
- `0xb208c`: `Mscrm.SolutionComponentList.manageSelectedEntitySubComponents(`
- `0xb20fc`: `/_imgs/solution/addrequiredcomponents.gif`
- `0xb2115`: `btnAddSubcomponents`
- `0xb1ff1`: `MenuItem_Label_RemoveComponent`
- `0xb2045`: `Ribbon.Formeditor.Button.RemoveComponent.Description`
- `0xb204f`: `btnRemoveComponent`

## pseudocode

```c

```

## disassembly

```asm
0xb1fc0  ldarg.2
0xb1fc1  brtrue.s loc_B1FC4
0xb1fc3  ret
0xb1fc4  ldarg.0
0xb1fc5  ldsfld   string PageParameters::EntityId
0xb1fca  ldc.i4.1
0xb1fcb  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.BusinessRulesListPageHandler::ParseGuidFromHttpRequest(string parameterName, bool required)
0xb1fd0  stloc.0
0xb1fd1  ldloca.s 1
0xb1fd3  ldloc.0
0xb1fd4  call     instance void [mscorlib]System.Guid::.ctor(string)
0xb1fd9  ldarg.2
0xb1fda  ldloc.1
0xb1fdb  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.SolutionUtil::AreSubcomponentsAddedSeperately(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext, valuetype [mscorlib]System.Guid)
0xb1fe0  brfalse  loc_B2120
0xb1fe5  ldarg.1
0xb1fe6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xb1feb  ldarg.1
0xb1fec  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb1ff1  ldstr    aMenuitemLabelR_2// "MenuItem_Label_RemoveComponent"
0xb1ff6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb1ffb  ldstr    aMscrmSolutionc_0// "Mscrm.SolutionComponentList.removeSolut"...
0xb2000  ldc.i4   0x125F
0xb2005  stloc.2
0xb2006  ldloca.s 2
0xb2008  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb200d  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xb2012  callvirt instance string [mscorlib]System.Object::ToString()
0xb2017  ldstr    asc_14E862// ")"
0xb201c  call     string [mscorlib]System.String::Concat(string, string, string)
0xb2021  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xb2026  ldc.i4.1
0xb2027  newarr   [mscorlib]System.Char
0xb202c  dup
0xb202d  ldc.i4.0
0xb202e  ldc.i4.s 0x2F
0xb2030  stelem.i2
0xb2031  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xb2036  ldstr    aImgsSolutionRe// "/_imgs/solution/removecomponent.gif"
0xb203b  call     string [mscorlib]System.String::Concat(string, string)
0xb2040  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb2045  ldstr    aRibbonFormedit_5// "Ribbon.Formeditor.Button.RemoveComponen"...
0xb204a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb204f  ldstr    aBtnremovecompo// "btnRemoveComponent"
0xb2054  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xb2059  pop
0xb205a  ldarg.1
0xb205b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xb2060  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteCustomization()
0xb2065  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb206a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb206f  brfalse  loc_B2120
0xb2074  ldarg.1
0xb2075  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb207a  ldstr    aMenuitemLabelA_0// "MenuItem_Label_AddSubcomponents"
0xb207f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb2084  ldc.i4.7
0xb2085  newarr   [mscorlib]System.Object
0xb208a  dup
0xb208b  ldc.i4.0
0xb208c  ldstr    aMscrmSolutionc_2// "Mscrm.SolutionComponentList.manageSelec"...
0xb2091  stelem.ref
0xb2092  dup
0xb2093  ldc.i4.1
0xb2094  ldc.i4   0x2649
0xb2099  stloc.2
0xb209a  ldloca.s 2
0xb209c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb20a1  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xb20a6  callvirt instance string [mscorlib]System.Object::ToString()
0xb20ab  stelem.ref
0xb20ac  dup
0xb20ad  ldc.i4.2
0xb20ae  ldstr    asc_15BF70// ",'"
0xb20b3  stelem.ref
0xb20b4  dup
0xb20b5  ldc.i4.3
0xb20b6  ldloc.1
0xb20b7  box      [mscorlib]System.Guid
0xb20bc  stelem.ref
0xb20bd  dup
0xb20be  ldc.i4.4
0xb20bf  ldstr    asc_14EC6A// "','"
0xb20c4  stelem.ref
0xb20c5  dup
0xb20c6  ldc.i4.5
0xb20c7  ldc.i4   0x125F
0xb20cc  stloc.2
0xb20cd  ldloca.s 2
0xb20cf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb20d4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xb20d9  stelem.ref
0xb20da  dup
0xb20db  ldc.i4.6
0xb20dc  ldstr    asc_1235BC// "')"
0xb20e1  stelem.ref
0xb20e2  call     string [mscorlib]System.String::Concat(object[])
0xb20e7  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xb20ec  ldc.i4.1
0xb20ed  newarr   [mscorlib]System.Char
0xb20f2  dup
0xb20f3  ldc.i4.0
0xb20f4  ldc.i4.s 0x2F
0xb20f6  stelem.i2
0xb20f7  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xb20fc  ldstr    aImgsSolutionAd// "/_imgs/solution/addrequiredcomponents.g"...
0xb2101  call     string [mscorlib]System.String::Concat(string, string)
0xb2106  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb210b  ldstr    aMenuitemLabelA_0// "MenuItem_Label_AddSubcomponents"
0xb2110  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb2115  ldstr    aBtnaddsubcompo// "btnAddSubcomponents"
0xb211a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xb211f  pop
0xb2120  ret
```
