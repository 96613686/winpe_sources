# Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.AlternateKeysListPage::ConfigureMenuButtonSubComponents

- ea: `0xbb370`
- end: `0xbb4e9`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.AlternateKeysListPage::ConfigureMenuButtonSubComponents`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xbb320`

## callees

- `0xbb370`

## string_xrefs

- `0xbb3ac`: `Mscrm.SolutionComponentList.removeSolutionSubcomponent(`
- `0xbb3e7`: `/_imgs/solution/removecomponent.gif`
- `0xbb437`: `MenuItem_Label_AddSubcomponents`
- `0xbb4d3`: `MenuItem_Label_AddSubcomponents`
- `0xbb449`: `Mscrm.SolutionComponentList.manageSelectedEntitySubComponents(`
- `0xbb4c3`: `/_imgs/solution/addrequiredcomponents.gif`
- `0xbb4dd`: `btnAddSubcomponents`
- `0xbb3a2`: `MenuItem_Label_RemoveComponent`
- `0xbb3f7`: `Ribbon.Formeditor.Button.RemoveComponent.Description`
- `0xbb401`: `btnRemoveComponent`

## pseudocode

```c

```

## disassembly

```asm
0xbb370  ldarg.0
0xbb371  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0xbb376  ldarg.0
0xbb377  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.AlternateKeysListPage::_entityMD
0xbb37c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0xbb381  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.SolutionUtil::AreSubcomponentsAddedSeperately(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext, valuetype [mscorlib]System.Guid)
0xbb386  brfalse  loc_BB4E8
0xbb38b  ldarg.0
0xbb38c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.AlternateKeysListPage::menuBar
0xbb391  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xbb396  ldarg.0
0xbb397  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.AlternateKeysListPage::menuBar
0xbb39c  ldarg.0
0xbb39d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xbb3a2  ldstr    aMenuitemLabelR_2// "MenuItem_Label_RemoveComponent"
0xbb3a7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbb3ac  ldstr    aMscrmSolutionc_0// "Mscrm.SolutionComponentList.removeSolut"...
0xbb3b1  ldc.i4   0x2654
0xbb3b6  stloc.0
0xbb3b7  ldloca.s 0
0xbb3b9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb3be  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb3c3  callvirt instance string [mscorlib]System.Object::ToString()
0xbb3c8  ldstr    asc_14E862// ")"
0xbb3cd  call     string [mscorlib]System.String::Concat(string, string, string)
0xbb3d2  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xbb3d7  ldc.i4.1
0xbb3d8  newarr   [mscorlib]System.Char
0xbb3dd  dup
0xbb3de  ldc.i4.0
0xbb3df  ldc.i4.s 0x2F
0xbb3e1  stelem.i2
0xbb3e2  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xbb3e7  ldstr    aImgsSolutionRe// "/_imgs/solution/removecomponent.gif"
0xbb3ec  call     string [mscorlib]System.String::Concat(string, string)
0xbb3f1  ldarg.0
0xbb3f2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xbb3f7  ldstr    aRibbonFormedit_5// "Ribbon.Formeditor.Button.RemoveComponen"...
0xbb3fc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbb401  ldstr    aBtnremovecompo// "btnRemoveComponent"
0xbb406  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xbb40b  pop
0xbb40c  ldarg.0
0xbb40d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.AlternateKeysListPage::menuBar
0xbb412  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xbb417  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteCustomization()
0xbb41c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbb421  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbb426  brfalse  loc_BB4E8
0xbb42b  ldarg.0
0xbb42c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.AlternateKeysListPage::menuBar
0xbb431  ldarg.0
0xbb432  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xbb437  ldstr    aMenuitemLabelA_0// "MenuItem_Label_AddSubcomponents"
0xbb43c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbb441  ldc.i4.7
0xbb442  newarr   [mscorlib]System.Object
0xbb447  dup
0xbb448  ldc.i4.0
0xbb449  ldstr    aMscrmSolutionc_2// "Mscrm.SolutionComponentList.manageSelec"...
0xbb44e  stelem.ref
0xbb44f  dup
0xbb450  ldc.i4.1
0xbb451  ldc.i4   0x2649
0xbb456  stloc.0
0xbb457  ldloca.s 0
0xbb459  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb45e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb463  callvirt instance string [mscorlib]System.Object::ToString()
0xbb468  stelem.ref
0xbb469  dup
0xbb46a  ldc.i4.2
0xbb46b  ldstr    asc_15BF70// ",'"
0xbb470  stelem.ref
0xbb471  dup
0xbb472  ldc.i4.3
0xbb473  ldarg.0
0xbb474  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.AlternateKeysListPage::_entityMD
0xbb479  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0xbb47e  box      [mscorlib]System.Guid
0xbb483  stelem.ref
0xbb484  dup
0xbb485  ldc.i4.4
0xbb486  ldstr    asc_14EC6A// "','"
0xbb48b  stelem.ref
0xbb48c  dup
0xbb48d  ldc.i4.5
0xbb48e  ldc.i4   0x2654
0xbb493  stloc.0
0xbb494  ldloca.s 0
0xbb496  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb49b  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb4a0  stelem.ref
0xbb4a1  dup
0xbb4a2  ldc.i4.6
0xbb4a3  ldstr    asc_1235BC// "')"
0xbb4a8  stelem.ref
0xbb4a9  call     string [mscorlib]System.String::Concat(object[])
0xbb4ae  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xbb4b3  ldc.i4.1
0xbb4b4  newarr   [mscorlib]System.Char
0xbb4b9  dup
0xbb4ba  ldc.i4.0
0xbb4bb  ldc.i4.s 0x2F
0xbb4bd  stelem.i2
0xbb4be  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xbb4c3  ldstr    aImgsSolutionAd// "/_imgs/solution/addrequiredcomponents.g"...
0xbb4c8  call     string [mscorlib]System.String::Concat(string, string)
0xbb4cd  ldarg.0
0xbb4ce  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xbb4d3  ldstr    aMenuitemLabelA_0// "MenuItem_Label_AddSubcomponents"
0xbb4d8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbb4dd  ldstr    aBtnaddsubcompo// "btnAddSubcomponents"
0xbb4e2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xbb4e7  pop
0xbb4e8  ret
```
