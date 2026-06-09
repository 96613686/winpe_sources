# Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::ConfigureMenus

- ea: `0x9ea30`
- end: `0x9eea0`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::ConfigureMenus`
- size: `1136`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x9ea30`
- `0x9ef20`

## string_xrefs

- `0x9ec2b`: `/_imgs/ico_16_delete.gif`
- `0x9ec8c`: `Mscrm.SolutionComponentList.removeSolutionSubcomponent(`
- `0x9ecc7`: `/_imgs/solution/removecomponent.gif`
- `0x9ed12`: `MenuItem_Label_AddSubcomponents`
- `0x9edae`: `MenuItem_Label_AddSubcomponents`
- `0x9ed24`: `Mscrm.SolutionComponentList.manageSelectedEntitySubComponents(`
- `0x9ed9e`: `/_imgs/solution/addrequiredcomponents.gif`
- `0x9edb8`: `btnAddSubcomponents`
- `0x9ec82`: `MenuItem_Label_RemoveComponent`
- `0x9ecdc`: `btnRemoveComponent`
- `0x9eba5`: `btnCreateView`
- `0x9ec45`: `btnDeleteViews`
- `0x9ecd2`: `Buttons.RemoveComponent.Tooltip`
- `0x9eb2d`: `cancreatecharts`
- `0x9eb71`: `createVisualization();`
- `0x9eb9b`: `SystemCustomization.Visualizations.Buttons.Create.Tooltip`
- `0x9ec11`: `dispatchAction(getSelectedVisualizationOid(), _oConst.sDeleteAction);`
- `0x9ec3b`: `SystemCustomization.Visualizations.Buttons.Delete.Tooltip`

## pseudocode

```c

```

## disassembly

```asm
0x9ea30  ldarg.0
0x9ea31  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::menuBar
0x9ea36  ldnull
0x9ea37  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_ShadowCssClass(string)
0x9ea3c  ldarg.0
0x9ea3d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::menuBar
0x9ea42  ldstr    aMsCrmActionbar// "ms-crm-ActionBar"
0x9ea47  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_CssClass(string)
0x9ea4c  ldarg.0
0x9ea4d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0x9ea52  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::IsManaged()
0x9ea57  brtrue.s loc_9EA66
0x9ea59  ldarg.0
0x9ea5a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0x9ea5f  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::get_IsParent()
0x9ea64  brfalse.s loc_9EA72
0x9ea66  ldarg.0
0x9ea67  ldstr    a1// "1"
0x9ea6c  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::disableDoubleClick
0x9ea71  ret
0x9ea72  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::.ctor()
0x9ea77  stloc.0
0x9ea78  ldloc.0
0x9ea79  ldstr    aMoreactions// "MoreActions"
0x9ea7e  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x9ea83  ldloc.0
0x9ea84  ldarg.0
0x9ea85  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ea8a  ldstr    aMenuLabelMorea// "Menu_Label_MoreActions"
0x9ea8f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ea94  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9ea99  ldloc.0
0x9ea9a  ldarg.0
0x9ea9b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9eaa0  ldstr    aMenuLabelMorea// "Menu_Label_MoreActions"
0x9eaa5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9eaaa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x9eaaf  ldloc.0
0x9eab0  ldc.i4.1
0x9eab1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::set_DownArrow(bool)
0x9eab6  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteCustomization()
0x9eabb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9eac0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9eac5  brfalse.s loc_9EB12
0x9eac7  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteSavedQueryVisualizations()
0x9eacc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9ead1  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9ead6  brfalse.s loc_9EB12
0x9ead8  ldloc.0
0x9ead9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x9eade  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9eae3  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x9eae8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9eaed  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x9eaf2  dup
0x9eaf3  ldarg.0
0x9eaf4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9eaf9  ldstr    aMenuitemLabelB// "MenuItem_Label_BulkEdit"
0x9eafe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9eb03  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9eb08  ldstr    aDispatchaction_6// "dispatchAction(getSelectedVisualization"...
0x9eb0d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x9eb12  ldarg.0
0x9eb13  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::_entityMD
0x9eb18  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x9eb1d  ldc.i4   0x7DB
0x9eb22  beq      loc_9EC5B
0x9eb27  ldarg.0
0x9eb28  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::_entityMD
0x9eb2d  ldstr    aCancreatechart// "cancreatecharts"
0x9eb32  ldarg.0
0x9eb33  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::_entityMD
0x9eb38  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanCreateCharts()
0x9eb3d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ManagedPropertyCheckUtil::IsPropertyDisabled(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, string, bool)
0x9eb42  brtrue   loc_9EBEA
0x9eb47  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateSavedQueryVisualizations()
0x9eb4c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9eb51  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9eb56  brfalse  loc_9EBEA
0x9eb5b  ldarg.0
0x9eb5c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::menuBar
0x9eb61  ldarg.0
0x9eb62  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9eb67  ldstr    aButtonLabelNew// "Button_Label_New"
0x9eb6c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9eb71  ldstr    aCreatevisualiz// "createVisualization();"
0x9eb76  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x9eb7b  ldc.i4.1
0x9eb7c  newarr   [mscorlib]System.Char
0x9eb81  dup
0x9eb82  ldc.i4.0
0x9eb83  ldc.i4.s 0x2F
0x9eb85  stelem.i2
0x9eb86  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x9eb8b  ldstr    aImgsIco161111P// "/_imgs/ico_16_1111.png"
0x9eb90  call     string [mscorlib]System.String::Concat(string, string)
0x9eb95  ldarg.0
0x9eb96  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9eb9b  ldstr    aSystemcustomiz_303// "SystemCustomization.Visualizations.Butt"...
0x9eba0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9eba5  ldstr    aBtncreateview// "btnCreateView"
0x9ebaa  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x9ebaf  pop
0x9ebb0  ldloc.0
0x9ebb1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x9ebb6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9ebbb  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x9ebc0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9ebc5  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x9ebca  dup
0x9ebcb  ldarg.0
0x9ebcc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ebd1  ldstr    aSystemcustomiz_304// "SystemCustomization.Visualizations.Menu"...
0x9ebd6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ebdb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9ebe0  ldstr    aImportvisualiz// "importVisualization();"
0x9ebe5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x9ebea  ldarg.0
0x9ebeb  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::menuBar
0x9ebf0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x9ebf5  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_DeleteSavedQueryVisualizations()
0x9ebfa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9ebff  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9ec04  brfalse.s loc_9EC50
0x9ec06  ldarg.0
0x9ec07  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::menuBar
0x9ec0c  ldsfld   string [mscorlib]System.String::Empty
0x9ec11  ldstr    aDispatchaction_7// "dispatchAction(getSelectedVisualization"...
0x9ec16  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x9ec1b  ldc.i4.1
0x9ec1c  newarr   [mscorlib]System.Char
0x9ec21  dup
0x9ec22  ldc.i4.0
0x9ec23  ldc.i4.s 0x2F
0x9ec25  stelem.i2
0x9ec26  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x9ec2b  ldstr    aImgsIco16Delet// "/_imgs/ico_16_delete.gif"
0x9ec30  call     string [mscorlib]System.String::Concat(string, string)
0x9ec35  ldarg.0
0x9ec36  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ec3b  ldstr    aSystemcustomiz_305// "SystemCustomization.Visualizations.Butt"...
0x9ec40  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ec45  ldstr    aBtndeleteviews// "btnDeleteViews"
0x9ec4a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x9ec4f  pop
0x9ec50  ldarg.0
0x9ec51  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::menuBar
0x9ec56  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x9ec5b  ldarg.0
0x9ec5c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0x9ec61  ldarg.0
0x9ec62  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::_entityMD
0x9ec67  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x9ec6c  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.SolutionUtil::AreSubcomponentsAddedSeperately(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext, valuetype [mscorlib]System.Guid)
0x9ec71  brfalse  loc_9EDC3
0x9ec76  ldarg.0
0x9ec77  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::menuBar
0x9ec7c  ldarg.0
0x9ec7d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ec82  ldstr    aMenuitemLabelR_2// "MenuItem_Label_RemoveComponent"
0x9ec87  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ec8c  ldstr    aMscrmSolutionc_0// "Mscrm.SolutionComponentList.removeSolut"...
0x9ec91  ldc.i4   0x457
0x9ec96  stloc.1
0x9ec97  ldloca.s 1
0x9ec99  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9ec9e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9eca3  callvirt instance string [mscorlib]System.Object::ToString()
0x9eca8  ldstr    asc_14E862// ")"
0x9ecad  call     string [mscorlib]System.String::Concat(string, string, string)
0x9ecb2  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x9ecb7  ldc.i4.1
0x9ecb8  newarr   [mscorlib]System.Char
0x9ecbd  dup
0x9ecbe  ldc.i4.0
0x9ecbf  ldc.i4.s 0x2F
0x9ecc1  stelem.i2
0x9ecc2  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x9ecc7  ldstr    aImgsSolutionRe// "/_imgs/solution/removecomponent.gif"
0x9eccc  call     string [mscorlib]System.String::Concat(string, string)
0x9ecd1  ldarg.0
0x9ecd2  ldstr    aButtonsRemovec// "Buttons.RemoveComponent.Tooltip"
0x9ecd7  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::GetString(string name)
0x9ecdc  ldstr    aBtnremovecompo// "btnRemoveComponent"
0x9ece1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x9ece6  pop
0x9ece7  ldarg.0
0x9ece8  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::menuBar
0x9eced  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x9ecf2  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteCustomization()
0x9ecf7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9ecfc  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9ed01  brfalse  loc_9EDC3
0x9ed06  ldarg.0
0x9ed07  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::menuBar
0x9ed0c  ldarg.0
0x9ed0d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ed12  ldstr    aMenuitemLabelA_0// "MenuItem_Label_AddSubcomponents"
0x9ed17  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ed1c  ldc.i4.7
0x9ed1d  newarr   [mscorlib]System.Object
0x9ed22  dup
0x9ed23  ldc.i4.0
0x9ed24  ldstr    aMscrmSolutionc_2// "Mscrm.SolutionComponentList.manageSelec"...
0x9ed29  stelem.ref
0x9ed2a  dup
0x9ed2b  ldc.i4.1
0x9ed2c  ldc.i4   0x2649
0x9ed31  stloc.1
0x9ed32  ldloca.s 1
0x9ed34  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9ed39  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9ed3e  callvirt instance string [mscorlib]System.Object::ToString()
0x9ed43  stelem.ref
0x9ed44  dup
0x9ed45  ldc.i4.2
0x9ed46  ldstr    asc_15BF70// ",'"
0x9ed4b  stelem.ref
0x9ed4c  dup
0x9ed4d  ldc.i4.3
0x9ed4e  ldarg.0
0x9ed4f  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::_entityMD
0x9ed54  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x9ed59  box      [mscorlib]System.Guid
0x9ed5e  stelem.ref
0x9ed5f  dup
0x9ed60  ldc.i4.4
0x9ed61  ldstr    asc_14EC6A// "','"
0x9ed66  stelem.ref
0x9ed67  dup
0x9ed68  ldc.i4.5
0x9ed69  ldc.i4   0x457
0x9ed6e  stloc.1
0x9ed6f  ldloca.s 1
0x9ed71  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9ed76  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9ed7b  stelem.ref
0x9ed7c  dup
0x9ed7d  ldc.i4.6
0x9ed7e  ldstr    asc_1235BC// "')"
0x9ed83  stelem.ref
0x9ed84  call     string [mscorlib]System.String::Concat(object[])
0x9ed89  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x9ed8e  ldc.i4.1
0x9ed8f  newarr   [mscorlib]System.Char
0x9ed94  dup
0x9ed95  ldc.i4.0
0x9ed96  ldc.i4.s 0x2F
0x9ed98  stelem.i2
0x9ed99  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x9ed9e  ldstr    aImgsSolutionAd// "/_imgs/solution/addrequiredcomponents.g"...
0x9eda3  call     string [mscorlib]System.String::Concat(string, string)
0x9eda8  ldarg.0
0x9eda9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9edae  ldstr    aMenuitemLabelA_0// "MenuItem_Label_AddSubcomponents"
0x9edb3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9edb8  ldstr    aBtnaddsubcompo// "btnAddSubcomponents"
0x9edbd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x9edc2  pop
0x9edc3  ldarg.0
0x9edc4  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.VisualizationsPage::menuBar
0x9edc9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x9edce  ldloc.0
0x9edcf  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x9edd4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9edd9  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x9edde  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9ede3  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x9ede8  dup
0x9ede9  ldarg.0
0x9edea  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9edef  ldstr    aSystemcustomiz_306// "SystemCustomization.Visualizations.Menu"...
0x9edf4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9edf9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9edfe  ldstr    aDispatchaction_8// "dispatchAction(getSelectedVisualization"...
0x9ee03  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x9ee08  ldloc.0
0x9ee09  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x9ee0e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9ee13  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x9ee18  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9ee1d  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x9ee22  dup
0x9ee23  ldarg.0
0x9ee24  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ee29  ldstr    aMenuitemLabelS_2// "MenuItem_Label_ShowDependency"
0x9ee2e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ee33  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9ee38  ldstr    aDispatchaction_9// "dispatchAction(getSelectedVisualization"...
0x9ee3d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x9ee42  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadSavedQueryVisualizations()
0x9ee47  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9ee4c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9ee51  brfalse.s loc_9EE8D
0x9ee53  ldloc.0
0x9ee54  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x9ee59  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9ee5e  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x9ee63  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9ee68  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
  ... truncated ...
```
