# Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::ConfigureMenus

- ea: `0xb5a50`
- end: `0xb5e38`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::ConfigureMenus`
- size: `1000`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0xb5a50`
- `0xb6030`

## string_xrefs

- `0xb5b6b`: `/_imgs/ico_16_delete.gif`
- `0xb5c2a`: `Mscrm.SolutionComponentList.removeSolutionSubcomponent(`
- `0xb5c65`: `/_imgs/solution/removecomponent.gif`
- `0xb5cb0`: `MenuItem_Label_AddSubcomponents`
- `0xb5d4c`: `MenuItem_Label_AddSubcomponents`
- `0xb5cc2`: `Mscrm.SolutionComponentList.manageSelectedEntitySubComponents(`
- `0xb5d3c`: `/_imgs/solution/addrequiredcomponents.gif`
- `0xb5d56`: `btnAddSubcomponents`
- `0xb5c20`: `MenuItem_Label_RemoveComponent`
- `0xb5c7a`: `btnRemoveComponent`
- `0xb5b76`: `Buttons.Delete.Tooltip`
- `0xb5b80`: `btnDeleteViews`
- `0xb5c70`: `Buttons.RemoveComponent.Tooltip`
- `0xb5b08`: `Buttons.Create.Tooltip`
- `0xb5ab6`: `cancreateattributes`
- `0xb5ae3`: `createAttributeAction();`
- `0xb5b12`: `btnCreateAttribute`
- `0xb5b51`: `dispatchAction(getSelectedAttributeOids(), _oConst.sDeleteAction);`
- `0xb5bbd`: `dispatchAction(getSelectedAttributeOids(), _oConst.sUpdateAction);`

## pseudocode

```c

```

## disassembly

```asm
0xb5a50  ldarg.0
0xb5a51  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::menuBar
0xb5a56  ldnull
0xb5a57  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_ShadowCssClass(string)
0xb5a5c  ldarg.0
0xb5a5d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::menuBar
0xb5a62  ldstr    aMsCrmActionbar// "ms-crm-ActionBar"
0xb5a67  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_CssClass(string)
0xb5a6c  ldarg.0
0xb5a6d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0xb5a72  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::IsManaged()
0xb5a77  brtrue.s loc_B5A86
0xb5a79  ldarg.0
0xb5a7a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0xb5a7f  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::get_IsParent()
0xb5a84  brfalse.s loc_B5A92
0xb5a86  ldarg.0
0xb5a87  ldstr    a1// "1"
0xb5a8c  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::disableDoubleClick
0xb5a91  ret
0xb5a92  ldarg.0
0xb5a93  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::_entityMD
0xb5a98  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomizable()
0xb5a9d  brfalse.s loc_B5B1D
0xb5a9f  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateAttribute()
0xb5aa4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb5aa9  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb5aae  brfalse.s loc_B5B1D
0xb5ab0  ldarg.0
0xb5ab1  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::_entityMD
0xb5ab6  ldstr    aCancreateattri// "cancreateattributes"
0xb5abb  ldarg.0
0xb5abc  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::_entityMD
0xb5ac1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanCreateAttributes()
0xb5ac6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ManagedPropertyCheckUtil::IsPropertyDisabled(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, string, bool)
0xb5acb  brtrue.s loc_B5B1D
0xb5acd  ldarg.0
0xb5ace  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::menuBar
0xb5ad3  ldarg.0
0xb5ad4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb5ad9  ldstr    aButtonLabelNew// "Button_Label_New"
0xb5ade  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb5ae3  ldstr    aCreateattribut// "createAttributeAction();"
0xb5ae8  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xb5aed  ldc.i4.1
0xb5aee  newarr   [mscorlib]System.Char
0xb5af3  dup
0xb5af4  ldc.i4.0
0xb5af5  ldc.i4.s 0x2F
0xb5af7  stelem.i2
0xb5af8  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xb5afd  ldstr    aImgsIco16Custo_0// "/_imgs/ico_16_customattribute.gif"
0xb5b02  call     string [mscorlib]System.String::Concat(string, string)
0xb5b07  ldarg.0
0xb5b08  ldstr    aButtonsCreateT// "Buttons.Create.Tooltip"
0xb5b0d  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::GetString(string name)
0xb5b12  ldstr    aBtncreateattri// "btnCreateAttribute"
0xb5b17  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xb5b1c  pop
0xb5b1d  ldarg.0
0xb5b1e  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::menuBar
0xb5b23  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xb5b28  ldarg.0
0xb5b29  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::_entityMD
0xb5b2e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomizable()
0xb5b33  brfalse.s loc_B5B8B
0xb5b35  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_DeleteAttribute()
0xb5b3a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb5b3f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb5b44  brfalse.s loc_B5B8B
0xb5b46  ldarg.0
0xb5b47  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::menuBar
0xb5b4c  ldsfld   string [mscorlib]System.String::Empty
0xb5b51  ldstr    aDispatchaction_16// "dispatchAction(getSelectedAttributeOids"...
0xb5b56  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xb5b5b  ldc.i4.1
0xb5b5c  newarr   [mscorlib]System.Char
0xb5b61  dup
0xb5b62  ldc.i4.0
0xb5b63  ldc.i4.s 0x2F
0xb5b65  stelem.i2
0xb5b66  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xb5b6b  ldstr    aImgsIco16Delet// "/_imgs/ico_16_delete.gif"
0xb5b70  call     string [mscorlib]System.String::Concat(string, string)
0xb5b75  ldarg.0
0xb5b76  ldstr    aButtonsDeleteT// "Buttons.Delete.Tooltip"
0xb5b7b  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::GetString(string name)
0xb5b80  ldstr    aBtndeleteviews// "btnDeleteViews"
0xb5b85  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xb5b8a  pop
0xb5b8b  ldarg.0
0xb5b8c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::menuBar
0xb5b91  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xb5b96  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteAttribute()
0xb5b9b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb5ba0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb5ba5  brfalse.s loc_B5BDD
0xb5ba7  ldarg.0
0xb5ba8  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::menuBar
0xb5bad  ldarg.0
0xb5bae  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb5bb3  ldstr    aMenuitemLabelB// "MenuItem_Label_BulkEdit"
0xb5bb8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb5bbd  ldstr    aDispatchaction_17// "dispatchAction(getSelectedAttributeOids"...
0xb5bc2  ldstr    asc_11EF2A// ""
0xb5bc7  ldarg.0
0xb5bc8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb5bcd  ldstr    aSystemcustomiz_441// "SystemCustomization.AttributeListPage.B"...
0xb5bd2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb5bd7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0xb5bdc  pop
0xb5bdd  ldarg.0
0xb5bde  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0xb5be3  ldarg.0
0xb5be4  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::_entityMD
0xb5be9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0xb5bee  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.SolutionUtil::AreSubcomponentsAddedSeperately(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext, valuetype [mscorlib]System.Guid)
0xb5bf3  brfalse  loc_B5D61
0xb5bf8  ldarg.0
0xb5bf9  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::menuBar
0xb5bfe  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xb5c03  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteCustomization()
0xb5c08  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb5c0d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb5c12  brfalse.s loc_B5C85
0xb5c14  ldarg.0
0xb5c15  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::menuBar
0xb5c1a  ldarg.0
0xb5c1b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb5c20  ldstr    aMenuitemLabelR_2// "MenuItem_Label_RemoveComponent"
0xb5c25  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb5c2a  ldstr    aMscrmSolutionc_0// "Mscrm.SolutionComponentList.removeSolut"...
0xb5c2f  ldc.i4   0x264A
0xb5c34  stloc.0
0xb5c35  ldloca.s 0
0xb5c37  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb5c3c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xb5c41  callvirt instance string [mscorlib]System.Object::ToString()
0xb5c46  ldstr    asc_14E862// ")"
0xb5c4b  call     string [mscorlib]System.String::Concat(string, string, string)
0xb5c50  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xb5c55  ldc.i4.1
0xb5c56  newarr   [mscorlib]System.Char
0xb5c5b  dup
0xb5c5c  ldc.i4.0
0xb5c5d  ldc.i4.s 0x2F
0xb5c5f  stelem.i2
0xb5c60  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xb5c65  ldstr    aImgsSolutionRe// "/_imgs/solution/removecomponent.gif"
0xb5c6a  call     string [mscorlib]System.String::Concat(string, string)
0xb5c6f  ldarg.0
0xb5c70  ldstr    aButtonsRemovec// "Buttons.RemoveComponent.Tooltip"
0xb5c75  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::GetString(string name)
0xb5c7a  ldstr    aBtnremovecompo// "btnRemoveComponent"
0xb5c7f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xb5c84  pop
0xb5c85  ldarg.0
0xb5c86  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::menuBar
0xb5c8b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xb5c90  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteCustomization()
0xb5c95  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb5c9a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb5c9f  brfalse  loc_B5D61
0xb5ca4  ldarg.0
0xb5ca5  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::menuBar
0xb5caa  ldarg.0
0xb5cab  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb5cb0  ldstr    aMenuitemLabelA_0// "MenuItem_Label_AddSubcomponents"
0xb5cb5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb5cba  ldc.i4.7
0xb5cbb  newarr   [mscorlib]System.Object
0xb5cc0  dup
0xb5cc1  ldc.i4.0
0xb5cc2  ldstr    aMscrmSolutionc_2// "Mscrm.SolutionComponentList.manageSelec"...
0xb5cc7  stelem.ref
0xb5cc8  dup
0xb5cc9  ldc.i4.1
0xb5cca  ldc.i4   0x2649
0xb5ccf  stloc.0
0xb5cd0  ldloca.s 0
0xb5cd2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb5cd7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xb5cdc  callvirt instance string [mscorlib]System.Object::ToString()
0xb5ce1  stelem.ref
0xb5ce2  dup
0xb5ce3  ldc.i4.2
0xb5ce4  ldstr    asc_15BF70// ",'"
0xb5ce9  stelem.ref
0xb5cea  dup
0xb5ceb  ldc.i4.3
0xb5cec  ldarg.0
0xb5ced  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::_entityMD
0xb5cf2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0xb5cf7  box      [mscorlib]System.Guid
0xb5cfc  stelem.ref
0xb5cfd  dup
0xb5cfe  ldc.i4.4
0xb5cff  ldstr    asc_14EC6A// "','"
0xb5d04  stelem.ref
0xb5d05  dup
0xb5d06  ldc.i4.5
0xb5d07  ldc.i4   0x264A
0xb5d0c  stloc.0
0xb5d0d  ldloca.s 0
0xb5d0f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb5d14  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xb5d19  stelem.ref
0xb5d1a  dup
0xb5d1b  ldc.i4.6
0xb5d1c  ldstr    asc_1235BC// "')"
0xb5d21  stelem.ref
0xb5d22  call     string [mscorlib]System.String::Concat(object[])
0xb5d27  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xb5d2c  ldc.i4.1
0xb5d2d  newarr   [mscorlib]System.Char
0xb5d32  dup
0xb5d33  ldc.i4.0
0xb5d34  ldc.i4.s 0x2F
0xb5d36  stelem.i2
0xb5d37  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xb5d3c  ldstr    aImgsSolutionAd// "/_imgs/solution/addrequiredcomponents.g"...
0xb5d41  call     string [mscorlib]System.String::Concat(string, string)
0xb5d46  ldarg.0
0xb5d47  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb5d4c  ldstr    aMenuitemLabelA_0// "MenuItem_Label_AddSubcomponents"
0xb5d51  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb5d56  ldstr    aBtnaddsubcompo// "btnAddSubcomponents"
0xb5d5b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xb5d60  pop
0xb5d61  ldarg.0
0xb5d62  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::menuBar
0xb5d67  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xb5d6c  ldarg.0
0xb5d6d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.AttributeListPage::menuBar
0xb5d72  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0xb5d77  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::.ctor()
0xb5d7c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0xb5d81  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup
0xb5d86  dup
0xb5d87  ldstr    aMoreactions// "MoreActions"
0xb5d8c  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xb5d91  dup
0xb5d92  ldarg.0
0xb5d93  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb5d98  ldstr    aMenuLabelMorea// "Menu_Label_MoreActions"
0xb5d9d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb5da2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0xb5da7  dup
0xb5da8  ldarg.0
0xb5da9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb5dae  ldstr    aMenuLabelMorea// "Menu_Label_MoreActions"
0xb5db3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb5db8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0xb5dbd  dup
0xb5dbe  ldc.i4.1
0xb5dbf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::set_DownArrow(bool)
0xb5dc4  dup
0xb5dc5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0xb5dca  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0xb5dcf  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0xb5dd4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0xb5dd9  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0xb5dde  dup
0xb5ddf  ldarg.0
0xb5de0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb5de5  ldstr    aMenuitemLabelS_2// "MenuItem_Label_ShowDependency"
0xb5dea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb5def  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0xb5df4  ldstr    aDispatchaction_18// "dispatchAction(getSelectedAttributeOid("...
0xb5df9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0xb5dfe  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0xb5e03  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0xb5e08  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0xb5e0d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0xb5e12  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0xb5e17  dup
0xb5e18  ldarg.0
0xb5e19  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb5e1e  ldstr    aMenuitemLabelM// "MenuItem_Label_ManagedProperties"
0xb5e23  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb5e28  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0xb5e2d  ldstr    aDispatchaction_19// "dispatchAction(getSelectedAttributeOid("...
0xb5e32  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0xb5e37  ret
```
