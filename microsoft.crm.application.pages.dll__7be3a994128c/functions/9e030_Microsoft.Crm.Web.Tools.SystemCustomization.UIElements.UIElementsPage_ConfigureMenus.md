# Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::ConfigureMenus

- ea: `0x9e030`
- end: `0x9e526`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::ConfigureMenus`
- size: `1270`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x9e030`
- `0x9e820`
- `0x9e840`

## string_xrefs

- `0x9e17b`: `/_imgs/ico_16_delete.gif`
- `0x9e1d7`: `Mscrm.SolutionComponentList.removeSolutionSubcomponent(`
- `0x9e212`: `/_imgs/solution/removecomponent.gif`
- `0x9e25d`: `MenuItem_Label_AddSubcomponents`
- `0x9e2f9`: `MenuItem_Label_AddSubcomponents`
- `0x9e26f`: `Mscrm.SolutionComponentList.manageSelectedEntitySubComponents(`
- `0x9e2e9`: `/_imgs/solution/addrequiredcomponents.gif`
- `0x9e303`: `btnAddSubcomponents`
- `0x9e0d3`: `cancreateviews`
- `0x9e1cd`: `MenuItem_Label_RemoveComponent`
- `0x9e227`: `btnRemoveComponent`
- `0x9e100`: `createView();`
- `0x9e125`: `Buttons.CreateView.Tooltip`
- `0x9e12f`: `btnCreateView`
- `0x9e161`: `dispatchAction(getSelectedUIElementOid(), _oConst.sDeleteAction);`
- `0x9e186`: `Buttons.Delete.Tooltip`
- `0x9e190`: `btnDeleteViews`
- `0x9e21d`: `Buttons.RemoveComponent.Tooltip`

## pseudocode

```c

```

## disassembly

```asm
0x9e030  ldarg.0
0x9e031  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::menuBar
0x9e036  ldnull
0x9e037  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_ShadowCssClass(string)
0x9e03c  ldarg.0
0x9e03d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::menuBar
0x9e042  ldstr    aMsCrmActionbar// "ms-crm-ActionBar"
0x9e047  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_CssClass(string)
0x9e04c  ldarg.0
0x9e04d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0x9e052  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::IsManaged()
0x9e057  brtrue.s loc_9E066
0x9e059  ldarg.0
0x9e05a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0x9e05f  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::get_IsParent()
0x9e064  brfalse.s loc_9E072
0x9e066  ldarg.0
0x9e067  ldstr    a1// "1"
0x9e06c  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::disableDoubleClick
0x9e071  ret
0x9e072  ldarg.0
0x9e073  ldarg.0
0x9e074  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::_entityMD
0x9e079  call     instance bool Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::IsChildEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMD)
0x9e07e  brfalse.s loc_9E0A7
0x9e080  ldarg.0
0x9e081  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::_entityMD
0x9e086  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x9e08b  ldc.i4   0x7ED
0x9e090  beq.s    loc_9E0A7
0x9e092  ldarg.0
0x9e093  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::_entityMD
0x9e098  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x9e09d  ldc.i4   0x401
0x9e0a2  bne.un   loc_9E525
0x9e0a7  ldarg.0
0x9e0a8  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::_entityMD
0x9e0ad  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x9e0b2  ldc.i4   0x7DB
0x9e0b7  beq      loc_9E1A6
0x9e0bc  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateQuery()
0x9e0c1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9e0c6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9e0cb  brfalse.s loc_9E13A
0x9e0cd  ldarg.0
0x9e0ce  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::_entityMD
0x9e0d3  ldstr    aCancreateviews// "cancreateviews"
0x9e0d8  ldarg.0
0x9e0d9  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::_entityMD
0x9e0de  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanCreateViews()
0x9e0e3  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ManagedPropertyCheckUtil::IsPropertyDisabled(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, string, bool)
0x9e0e8  brtrue.s loc_9E13A
0x9e0ea  ldarg.0
0x9e0eb  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::menuBar
0x9e0f0  ldarg.0
0x9e0f1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9e0f6  ldstr    aButtonLabelNew// "Button_Label_New"
0x9e0fb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9e100  ldstr    aCreateview// "createView();"
0x9e105  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x9e10a  ldc.i4.1
0x9e10b  newarr   [mscorlib]System.Char
0x9e110  dup
0x9e111  ldc.i4.0
0x9e112  ldc.i4.s 0x2F
0x9e114  stelem.i2
0x9e115  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x9e11a  ldstr    aImgsIco161039G// "/_imgs/ico_16_1039.gif"
0x9e11f  call     string [mscorlib]System.String::Concat(string, string)
0x9e124  ldarg.0
0x9e125  ldstr    aButtonsCreatev// "Buttons.CreateView.Tooltip"
0x9e12a  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::GetString(string name)
0x9e12f  ldstr    aBtncreateview// "btnCreateView"
0x9e134  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x9e139  pop
0x9e13a  ldarg.0
0x9e13b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::menuBar
0x9e140  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x9e145  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_DeleteQuery()
0x9e14a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9e14f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9e154  brfalse.s loc_9E19B
0x9e156  ldarg.0
0x9e157  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::menuBar
0x9e15c  ldsfld   string [mscorlib]System.String::Empty
0x9e161  ldstr    aDispatchaction// "dispatchAction(getSelectedUIElementOid("...
0x9e166  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x9e16b  ldc.i4.1
0x9e16c  newarr   [mscorlib]System.Char
0x9e171  dup
0x9e172  ldc.i4.0
0x9e173  ldc.i4.s 0x2F
0x9e175  stelem.i2
0x9e176  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x9e17b  ldstr    aImgsIco16Delet// "/_imgs/ico_16_delete.gif"
0x9e180  call     string [mscorlib]System.String::Concat(string, string)
0x9e185  ldarg.0
0x9e186  ldstr    aButtonsDeleteT// "Buttons.Delete.Tooltip"
0x9e18b  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::GetString(string name)
0x9e190  ldstr    aBtndeleteviews// "btnDeleteViews"
0x9e195  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x9e19a  pop
0x9e19b  ldarg.0
0x9e19c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::menuBar
0x9e1a1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x9e1a6  ldarg.0
0x9e1a7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0x9e1ac  ldarg.0
0x9e1ad  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::_entityMD
0x9e1b2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x9e1b7  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.SolutionUtil::AreSubcomponentsAddedSeperately(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext, valuetype [mscorlib]System.Guid)
0x9e1bc  brfalse  loc_9E319
0x9e1c1  ldarg.0
0x9e1c2  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::menuBar
0x9e1c7  ldarg.0
0x9e1c8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9e1cd  ldstr    aMenuitemLabelR_2// "MenuItem_Label_RemoveComponent"
0x9e1d2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9e1d7  ldstr    aMscrmSolutionc_0// "Mscrm.SolutionComponentList.removeSolut"...
0x9e1dc  ldc.i4   0x40F
0x9e1e1  stloc.1
0x9e1e2  ldloca.s 1
0x9e1e4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9e1e9  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9e1ee  callvirt instance string [mscorlib]System.Object::ToString()
0x9e1f3  ldstr    asc_14E862// ")"
0x9e1f8  call     string [mscorlib]System.String::Concat(string, string, string)
0x9e1fd  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x9e202  ldc.i4.1
0x9e203  newarr   [mscorlib]System.Char
0x9e208  dup
0x9e209  ldc.i4.0
0x9e20a  ldc.i4.s 0x2F
0x9e20c  stelem.i2
0x9e20d  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x9e212  ldstr    aImgsSolutionRe// "/_imgs/solution/removecomponent.gif"
0x9e217  call     string [mscorlib]System.String::Concat(string, string)
0x9e21c  ldarg.0
0x9e21d  ldstr    aButtonsRemovec// "Buttons.RemoveComponent.Tooltip"
0x9e222  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::GetString(string name)
0x9e227  ldstr    aBtnremovecompo// "btnRemoveComponent"
0x9e22c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x9e231  pop
0x9e232  ldarg.0
0x9e233  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::menuBar
0x9e238  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x9e23d  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteCustomization()
0x9e242  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9e247  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9e24c  brfalse  loc_9E30E
0x9e251  ldarg.0
0x9e252  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::menuBar
0x9e257  ldarg.0
0x9e258  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9e25d  ldstr    aMenuitemLabelA_0// "MenuItem_Label_AddSubcomponents"
0x9e262  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9e267  ldc.i4.7
0x9e268  newarr   [mscorlib]System.Object
0x9e26d  dup
0x9e26e  ldc.i4.0
0x9e26f  ldstr    aMscrmSolutionc_2// "Mscrm.SolutionComponentList.manageSelec"...
0x9e274  stelem.ref
0x9e275  dup
0x9e276  ldc.i4.1
0x9e277  ldc.i4   0x2649
0x9e27c  stloc.1
0x9e27d  ldloca.s 1
0x9e27f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9e284  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9e289  callvirt instance string [mscorlib]System.Object::ToString()
0x9e28e  stelem.ref
0x9e28f  dup
0x9e290  ldc.i4.2
0x9e291  ldstr    asc_15BF70// ",'"
0x9e296  stelem.ref
0x9e297  dup
0x9e298  ldc.i4.3
0x9e299  ldarg.0
0x9e29a  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::_entityMD
0x9e29f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x9e2a4  box      [mscorlib]System.Guid
0x9e2a9  stelem.ref
0x9e2aa  dup
0x9e2ab  ldc.i4.4
0x9e2ac  ldstr    asc_14EC6A// "','"
0x9e2b1  stelem.ref
0x9e2b2  dup
0x9e2b3  ldc.i4.5
0x9e2b4  ldc.i4   0x40F
0x9e2b9  stloc.1
0x9e2ba  ldloca.s 1
0x9e2bc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9e2c1  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9e2c6  stelem.ref
0x9e2c7  dup
0x9e2c8  ldc.i4.6
0x9e2c9  ldstr    asc_1235BC// "')"
0x9e2ce  stelem.ref
0x9e2cf  call     string [mscorlib]System.String::Concat(object[])
0x9e2d4  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x9e2d9  ldc.i4.1
0x9e2da  newarr   [mscorlib]System.Char
0x9e2df  dup
0x9e2e0  ldc.i4.0
0x9e2e1  ldc.i4.s 0x2F
0x9e2e3  stelem.i2
0x9e2e4  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x9e2e9  ldstr    aImgsSolutionAd// "/_imgs/solution/addrequiredcomponents.g"...
0x9e2ee  call     string [mscorlib]System.String::Concat(string, string)
0x9e2f3  ldarg.0
0x9e2f4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9e2f9  ldstr    aMenuitemLabelA_0// "MenuItem_Label_AddSubcomponents"
0x9e2fe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9e303  ldstr    aBtnaddsubcompo// "btnAddSubcomponents"
0x9e308  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x9e30d  pop
0x9e30e  ldarg.0
0x9e30f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::menuBar
0x9e314  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x9e319  ldarg.0
0x9e31a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::menuBar
0x9e31f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9e324  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::.ctor()
0x9e329  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9e32e  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup
0x9e333  stloc.0
0x9e334  ldloc.0
0x9e335  ldstr    aMoreactions// "MoreActions"
0x9e33a  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x9e33f  ldloc.0
0x9e340  ldarg.0
0x9e341  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9e346  ldstr    aMenuLabelMorea// "Menu_Label_MoreActions"
0x9e34b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9e350  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9e355  ldloc.0
0x9e356  ldarg.0
0x9e357  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9e35c  ldstr    aMenuLabelMorea// "Menu_Label_MoreActions"
0x9e361  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9e366  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x9e36b  ldloc.0
0x9e36c  ldc.i4.1
0x9e36d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::set_DownArrow(bool)
0x9e372  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteCustomization()
0x9e377  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9e37c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9e381  brfalse.s loc_9E3CE
0x9e383  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteQuery()
0x9e388  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9e38d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9e392  brfalse.s loc_9E3CE
0x9e394  ldloc.0
0x9e395  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x9e39a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9e39f  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x9e3a4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9e3a9  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x9e3ae  dup
0x9e3af  ldarg.0
0x9e3b0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9e3b5  ldstr    aMenuitemLabelB// "MenuItem_Label_BulkEdit"
0x9e3ba  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9e3bf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9e3c4  ldstr    aDispatchaction_0// "dispatchAction(getSelectedUIElementOid("...
0x9e3c9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x9e3ce  ldarg.0
0x9e3cf  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.UIElementsPage::_entityMD
0x9e3d4  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x9e3d9  ldc.i4   0x7DB
0x9e3de  beq      loc_9E4A0
0x9e3e3  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteQuery()
0x9e3e8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9e3ed  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9e3f2  brfalse  loc_9E4A0
0x9e3f7  ldloc.0
0x9e3f8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x9e3fd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9e402  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x9e407  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9e40c  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x9e411  dup
0x9e412  ldarg.0
0x9e413  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9e418  ldstr    aMenuLabelActiv// "Menu_Label_Activate"
0x9e41d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9e422  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9e427  ldstr    aDispatchaction_1// "dispatchAction(getSelectedUIElementOid("...
0x9e42c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x9e431  ldloc.0
0x9e432  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x9e437  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9e43c  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x9e441  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9e446  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x9e44b  dup
0x9e44c  ldarg.0
0x9e44d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9e452  ldstr    aMenuLabelDeact// "Menu_Label_Deactivate"
0x9e457  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
  ... truncated ...
```
