# Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.Mappings.MappingListPage::ConfigureMenus

- ea: `0xa32e0`
- end: `0xa3495`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.Mappings.MappingListPage::ConfigureMenus`
- size: `437`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0xa32e0`
- `0xa3520`

## string_xrefs

- `0xa33ca`: `/_imgs/ico_16_delete.gif`
- `0xa33d5`: `Buttons.Delete.Tooltip`
- `0xa3349`: `createMappingAction();`
- `0xa336e`: `Buttons.Create.Tooltip`
- `0xa3378`: `btnCreateEntityMap`
- `0xa33a6`: `Buttons.Delete.Title`
- `0xa33b0`: `dispatchAction(getSelected('gridMappings'), _oConst.sDeleteAction);`
- `0xa33df`: `btnDeleteEntityMap`

## pseudocode

```c

```

## disassembly

```asm
0xa32e0  ldarg.0
0xa32e1  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.Mappings.MappingListPage::menuBar
0xa32e6  ldnull
0xa32e7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_ShadowCssClass(string)
0xa32ec  ldarg.0
0xa32ed  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.Mappings.MappingListPage::menuBar
0xa32f2  ldstr    aMsCrmActionbar// "ms-crm-ActionBar"
0xa32f7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_CssClass(string)
0xa32fc  ldarg.0
0xa32fd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0xa3302  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::IsManaged()
0xa3307  brtrue.s loc_A3316
0xa3309  ldarg.0
0xa330a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0xa330f  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::get_IsParent()
0xa3314  brfalse.s loc_A3322
0xa3316  ldarg.0
0xa3317  ldstr    a1// "1"
0xa331c  stfld    string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.Mappings.MappingListPage::disableDoubleClick
0xa3321  ret
0xa3322  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteRelationship()
0xa3327  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa332c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa3331  brfalse.s loc_A3383
0xa3333  ldarg.0
0xa3334  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.Mappings.MappingListPage::menuBar
0xa3339  ldarg.0
0xa333a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa333f  ldstr    aButtonLabelNew// "Button_Label_New"
0xa3344  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa3349  ldstr    aCreatemappinga// "createMappingAction();"
0xa334e  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xa3353  ldc.i4.1
0xa3354  newarr   [mscorlib]System.Char
0xa3359  dup
0xa335a  ldc.i4.0
0xa335b  ldc.i4.s 0x2F
0xa335d  stelem.i2
0xa335e  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xa3363  ldstr    aImgsIco16Custo// "/_imgs/ico_16_customattributemap.gif"
0xa3368  call     string [mscorlib]System.String::Concat(string, string)
0xa336d  ldarg.0
0xa336e  ldstr    aButtonsCreateT// "Buttons.Create.Tooltip"
0xa3373  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.Mappings.MappingListPage::GetString(string name)
0xa3378  ldstr    aBtncreateentit// "btnCreateEntityMap"
0xa337d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xa3382  pop
0xa3383  ldarg.0
0xa3384  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.Mappings.MappingListPage::menuBar
0xa3389  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xa338e  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteRelationship()
0xa3393  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa3398  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa339d  brfalse.s loc_A33EA
0xa339f  ldarg.0
0xa33a0  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.Mappings.MappingListPage::menuBar
0xa33a5  ldarg.0
0xa33a6  ldstr    aButtonsDeleteT_0// "Buttons.Delete.Title"
0xa33ab  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.Mappings.MappingListPage::GetString(string name)
0xa33b0  ldstr    aDispatchaction_15// "dispatchAction(getSelected('gridMapping"...
0xa33b5  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xa33ba  ldc.i4.1
0xa33bb  newarr   [mscorlib]System.Char
0xa33c0  dup
0xa33c1  ldc.i4.0
0xa33c2  ldc.i4.s 0x2F
0xa33c4  stelem.i2
0xa33c5  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xa33ca  ldstr    aImgsIco16Delet// "/_imgs/ico_16_delete.gif"
0xa33cf  call     string [mscorlib]System.String::Concat(string, string)
0xa33d4  ldarg.0
0xa33d5  ldstr    aButtonsDeleteT// "Buttons.Delete.Tooltip"
0xa33da  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.Mappings.MappingListPage::GetString(string name)
0xa33df  ldstr    aBtndeleteentit// "btnDeleteEntityMap"
0xa33e4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xa33e9  pop
0xa33ea  ldarg.0
0xa33eb  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.Mappings.MappingListPage::menuBar
0xa33f0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xa33f5  ldarg.0
0xa33f6  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.Mappings.MappingListPage::menuBar
0xa33fb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0xa3400  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::.ctor()
0xa3405  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0xa340a  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup
0xa340f  stloc.0
0xa3410  ldloc.0
0xa3411  ldstr    aMoreactions// "MoreActions"
0xa3416  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xa341b  ldloc.0
0xa341c  ldarg.0
0xa341d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa3422  ldstr    aMenuLabelMorea// "Menu_Label_MoreActions"
0xa3427  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa342c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0xa3431  ldloc.0
0xa3432  ldarg.0
0xa3433  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa3438  ldstr    aMenuLabelMorea// "Menu_Label_MoreActions"
0xa343d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa3442  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0xa3447  ldloc.0
0xa3448  ldc.i4.1
0xa3449  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::set_DownArrow(bool)
0xa344e  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteRelationship()
0xa3453  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa3458  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa345d  brfalse.s loc_A3494
0xa345f  ldloc.0
0xa3460  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0xa3465  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0xa346a  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0xa346f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0xa3474  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0xa3479  dup
0xa347a  ldarg.0
0xa347b  ldstr    aActionsAutomap// "Actions.AutoMap.Title"
0xa3480  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Relationships.Mappings.MappingListPage::GetString(string name)
0xa3485  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0xa348a  ldstr    aAutomapaction// "autoMapAction();"
0xa348f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0xa3494  ret
```
