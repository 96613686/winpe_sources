# Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.FormsGridPage::ConfigureMenus

- ea: `0x9d520`
- end: `0x9dddb`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.FormsGridPage::ConfigureMenus`
- size: `2235`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x9d520`

## string_xrefs

- `0x9d75b`: `/_imgs/ico_16_delete.gif`
- `0x9d737`: `MenuItem_Label_Delete_SolutionCompontent`
- `0x9daf9`: `Mscrm.SolutionComponentList.removeSolutionSubcomponent(`
- `0x9db34`: `/_imgs/solution/removecomponent.gif`
- `0x9db84`: `MenuItem_Label_AddSubcomponents`
- `0x9dc20`: `MenuItem_Label_AddSubcomponents`
- `0x9db96`: `Mscrm.SolutionComponentList.manageSelectedEntitySubComponents(`
- `0x9dc10`: `/_imgs/solution/addrequiredcomponents.gif`
- `0x9dc2a`: `btnAddSubcomponents`
- `0x9d585`: `cancreateforms`
- `0x9d5ba`: `btnCreateForm`
- `0x9d5e1`: `SystemCustomization.FormsGridPage.Buttons.CreateForm.Tooltip`
- `0x9d5f8`: `Mscrm.UIElementsGrid.createNewForm();`
- `0x9d647`: `Mscrm.UIElementsGrid.createNewForm();`
- `0x9d638`: `SystemCustomization.FormsGridPage.Buttons.CreateMainForm`
- `0x9d672`: `SystemCustomization.FormsGridPage.Buttons.CreateQuickForm`
- `0x9d681`: `Mscrm.UIElementsGrid.createNewQuickForm();`
- `0x9d6ac`: `SystemCustomization.FormsGridPage.Buttons.CreateQuickCreateForm`
- `0x9d6bb`: `Mscrm.UIElementsGrid.createNewQuickCreateForm();`
- `0x9d6e5`: `SystemCustomization.FormsGridPage.Buttons.CreateCardForm`
- `0x9d6f4`: `Mscrm.UIElementsGrid.createNewCardForm();`
- `0x9d741`: `Mscrm.UIElementsGrid.deleteItem();`
- `0x9d76b`: `SystemCustomization.FormsGridPage.Buttons.Delete.Tooltip`
- `0x9d775`: `btnDeleteForm`
- `0x9d918`: `SystemCustomization.FormsGridPage.Buttons.OrderQuickCreateForms`
- `0x9daef`: `MenuItem_Label_RemoveComponent`
- `0x9db44`: `Ribbon.Formeditor.Button.RemoveComponent.Description`
- `0x9db4e`: `btnRemoveComponent`
- `0x9dceb`: `Mscrm.UIElementsGrid.editExistingFormFromGridCommand();`

## pseudocode

```c

```

## disassembly

```asm
0x9d520  ldarg.0
0x9d521  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.FormsGridPage::menuBar
0x9d526  ldnull
0x9d527  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_ShadowCssClass(string)
0x9d52c  ldarg.0
0x9d52d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.FormsGridPage::menuBar
0x9d532  ldstr    aMsCrmActionbar// "ms-crm-ActionBar"
0x9d537  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_CssClass(string)
0x9d53c  ldarg.0
0x9d53d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0x9d542  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::IsManaged()
0x9d547  brtrue.s loc_9D556
0x9d549  ldarg.0
0x9d54a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0x9d54f  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::get_IsParent()
0x9d554  brfalse.s loc_9D557
0x9d556  ret
0x9d557  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateCustomization()
0x9d55c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9d561  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9d566  brfalse  loc_9D6FE
0x9d56b  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateSystemForm()
0x9d570  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9d575  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9d57a  brfalse  loc_9D6FE
0x9d57f  ldarg.0
0x9d580  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.FormsGridPage::_entityMD
0x9d585  ldstr    aCancreateforms// "cancreateforms"
0x9d58a  ldarg.0
0x9d58b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.FormsGridPage::_entityMD
0x9d590  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanCreateForms()
0x9d595  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ManagedPropertyCheckUtil::IsPropertyDisabled(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, string, bool)
0x9d59a  brtrue   loc_9D6FE
0x9d59f  ldarg.0
0x9d5a0  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.FormsGridPage::menuBar
0x9d5a5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9d5aa  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::.ctor()
0x9d5af  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9d5b4  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup
0x9d5b9  dup
0x9d5ba  ldstr    aBtncreateform// "btnCreateForm"
0x9d5bf  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x9d5c4  dup
0x9d5c5  ldarg.0
0x9d5c6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d5cb  ldstr    aButtonLabelNew// "Button_Label_New"
0x9d5d0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d5d5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9d5da  dup
0x9d5db  ldarg.0
0x9d5dc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d5e1  ldstr    aSystemcustomiz_289// "SystemCustomization.FormsGridPage.Butto"...
0x9d5e6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d5eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x9d5f0  dup
0x9d5f1  ldc.i4.1
0x9d5f2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::set_DownArrow(bool)
0x9d5f7  dup
0x9d5f8  ldstr    aMscrmUielement// "Mscrm.UIElementsGrid.createNewForm();"
0x9d5fd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x9d602  dup
0x9d603  ldstr    aImgsIco161039G// "/_imgs/ico_16_1039.gif"
0x9d608  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9d60d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9d612  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x9d617  dup
0x9d618  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x9d61d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9d622  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x9d627  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9d62c  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x9d631  dup
0x9d632  ldarg.0
0x9d633  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d638  ldstr    aSystemcustomiz_290// "SystemCustomization.FormsGridPage.Butto"...
0x9d63d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d642  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9d647  ldstr    aMscrmUielement// "Mscrm.UIElementsGrid.createNewForm();"
0x9d64c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x9d651  dup
0x9d652  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x9d657  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9d65c  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x9d661  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9d666  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x9d66b  dup
0x9d66c  ldarg.0
0x9d66d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d672  ldstr    aSystemcustomiz_291// "SystemCustomization.FormsGridPage.Butto"...
0x9d677  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d67c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9d681  ldstr    aMscrmUielement_0// "Mscrm.UIElementsGrid.createNewQuickForm"...
0x9d686  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x9d68b  dup
0x9d68c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x9d691  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9d696  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x9d69b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9d6a0  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x9d6a5  dup
0x9d6a6  ldarg.0
0x9d6a7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d6ac  ldstr    aSystemcustomiz_292// "SystemCustomization.FormsGridPage.Butto"...
0x9d6b1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d6b6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9d6bb  ldstr    aMscrmUielement_1// "Mscrm.UIElementsGrid.createNewQuickCrea"...
0x9d6c0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x9d6c5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x9d6ca  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9d6cf  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x9d6d4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9d6d9  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x9d6de  dup
0x9d6df  ldarg.0
0x9d6e0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d6e5  ldstr    aSystemcustomiz_293// "SystemCustomization.FormsGridPage.Butto"...
0x9d6ea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d6ef  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9d6f4  ldstr    aMscrmUielement_2// "Mscrm.UIElementsGrid.createNewCardForm("...
0x9d6f9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x9d6fe  ldarg.0
0x9d6ff  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.FormsGridPage::menuBar
0x9d704  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x9d709  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_DeleteCustomization()
0x9d70e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9d713  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9d718  brfalse.s loc_9D780
0x9d71a  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_DeleteSystemForm()
0x9d71f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9d724  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9d729  brfalse.s loc_9D780
0x9d72b  ldarg.0
0x9d72c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.FormsGridPage::menuBar
0x9d731  ldarg.0
0x9d732  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d737  ldstr    aMenuitemLabelD_3// "MenuItem_Label_Delete_SolutionComponten"...
0x9d73c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d741  ldstr    aMscrmUielement_3// "Mscrm.UIElementsGrid.deleteItem();"
0x9d746  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x9d74b  ldc.i4.1
0x9d74c  newarr   [mscorlib]System.Char
0x9d751  dup
0x9d752  ldc.i4.0
0x9d753  ldc.i4.s 0x2F
0x9d755  stelem.i2
0x9d756  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x9d75b  ldstr    aImgsIco16Delet// "/_imgs/ico_16_delete.gif"
0x9d760  call     string [mscorlib]System.String::Concat(string, string)
0x9d765  ldarg.0
0x9d766  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d76b  ldstr    aSystemcustomiz_294// "SystemCustomization.FormsGridPage.Butto"...
0x9d770  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d775  ldstr    aBtndeleteform// "btnDeleteForm"
0x9d77a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x9d77f  pop
0x9d780  ldarg.0
0x9d781  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.FormsGridPage::menuBar
0x9d786  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x9d78b  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteCustomization()
0x9d790  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9d795  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9d79a  brfalse.s loc_9D802
0x9d79c  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteSystemForm()
0x9d7a1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9d7a6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9d7ab  brfalse.s loc_9D802
0x9d7ad  ldarg.0
0x9d7ae  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.FormsGridPage::menuBar
0x9d7b3  ldarg.0
0x9d7b4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d7b9  ldstr    aRibbonFormedit// "Ribbon.Formeditor.Button.AssignRoles"
0x9d7be  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d7c3  ldstr    aMscrmUielement_4// "Mscrm.UIElementsGrid.assignRoles();"
0x9d7c8  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x9d7cd  ldc.i4.1
0x9d7ce  newarr   [mscorlib]System.Char
0x9d7d3  dup
0x9d7d4  ldc.i4.0
0x9d7d5  ldc.i4.s 0x2F
0x9d7d7  stelem.i2
0x9d7d8  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x9d7dd  ldstr    aImgsRibbonAssi// "/_imgs/ribbon/assignroles_16.png"
0x9d7e2  call     string [mscorlib]System.String::Concat(string, string)
0x9d7e7  ldarg.0
0x9d7e8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d7ed  ldstr    aRibbonFormedit_0// "Ribbon.Formeditor.Button.AssignRoles.De"...
0x9d7f2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d7f7  ldstr    aBtnassignformr// "btnAssignFormRoles"
0x9d7fc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x9d801  pop
0x9d802  ldarg.0
0x9d803  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.FormsGridPage::menuBar
0x9d808  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x9d80d  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteCustomization()
0x9d812  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9d817  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9d81c  brfalse  loc_9D9E0
0x9d821  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteSystemForm()
0x9d826  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9d82b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9d830  brfalse  loc_9D9E0
0x9d835  ldarg.0
0x9d836  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.UIElements.FormsGridPage::menuBar
0x9d83b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9d840  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::.ctor()
0x9d845  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9d84a  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup
0x9d84f  dup
0x9d850  ldstr    aBtnformorder// "btnFormOrder"
0x9d855  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x9d85a  dup
0x9d85b  ldarg.0
0x9d85c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d861  ldstr    aSystemcustomiz_295// "SystemCustomization.FormsGridPage.Butto"...
0x9d866  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d86b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9d870  dup
0x9d871  ldarg.0
0x9d872  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d877  ldstr    aSystemcustomiz_296// "SystemCustomization.FormsGridPage.Butto"...
0x9d87c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d881  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x9d886  dup
0x9d887  ldc.i4.1
0x9d888  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::set_DownArrow(bool)
0x9d88d  dup
0x9d88e  ldstr    aMscrmUielement_5// "Mscrm.UIElementsGrid.formOrder();"
0x9d893  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x9d898  dup
0x9d899  ldstr    aImgsIco16Formo// "/_imgs/ico_16_formorder.png"
0x9d89e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9d8a3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9d8a8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x9d8ad  dup
0x9d8ae  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x9d8b3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9d8b8  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x9d8bd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9d8c2  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x9d8c7  dup
0x9d8c8  ldarg.0
0x9d8c9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d8ce  ldstr    aSystemcustomiz_297// "SystemCustomization.FormsGridPage.Butto"...
0x9d8d3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d8d8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9d8dd  ldstr    aMscrmUielement_6// "Mscrm.UIElementsGrid.formOrder('"
0x9d8e2  ldc.i4.2
0x9d8e3  box      [mscorlib]System.Int32
0x9d8e8  ldstr    asc_142D92// "');"
0x9d8ed  call     string [mscorlib]System.String::Concat(object, object, object)
0x9d8f2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x9d8f7  dup
0x9d8f8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x9d8fd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9d902  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x9d907  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9d90c  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x9d911  dup
0x9d912  ldarg.0
0x9d913  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d918  ldstr    aSystemcustomiz_298// "SystemCustomization.FormsGridPage.Butto"...
0x9d91d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d922  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9d927  ldstr    aMscrmUielement_6// "Mscrm.UIElementsGrid.formOrder('"
0x9d92c  ldc.i4.7
0x9d92d  box      [mscorlib]System.Int32
0x9d932  ldstr    asc_142D92// "');"
0x9d937  call     string [mscorlib]System.String::Concat(object, object, object)
0x9d93c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x9d941  dup
0x9d942  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x9d947  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9d94c  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x9d951  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9d956  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x9d95b  dup
0x9d95c  ldarg.0
0x9d95d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d962  ldstr    aSystemcustomiz_299// "SystemCustomization.FormsGridPage.Butto"...
0x9d967  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d96c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9d971  ldstr    aMscrmUielement_6// "Mscrm.UIElementsGrid.formOrder('"
0x9d976  ldc.i4.6
0x9d977  box      [mscorlib]System.Int32
0x9d97c  ldstr    asc_142D92// "');"
0x9d981  call     string [mscorlib]System.String::Concat(object, object, object)
0x9d986  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x9d98b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x9d990  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x9d995  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x9d99a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x9d99f  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x9d9a4  dup
0x9d9a5  ldarg.0
0x9d9a6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d9ab  ldstr    aSystemcustomiz_300// "SystemCustomization.FormsGridPage.Butto"...
0x9d9b0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d9b5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9d9ba  ldstr    aMscrmUielement_6// "Mscrm.UIElementsGrid.formOrder('"
0x9d9bf  ldc.i4.s 0xB
  ... truncated ...
```
