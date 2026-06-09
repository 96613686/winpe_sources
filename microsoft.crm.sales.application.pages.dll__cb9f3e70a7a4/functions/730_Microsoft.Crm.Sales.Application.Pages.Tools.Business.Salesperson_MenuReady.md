# Microsoft.Crm.Sales.Application.Pages.Tools.Business.Salesperson::MenuReady

- ea: `0x730`
- end: `0x76e`
- name: `Microsoft.Crm.Sales.Application.Pages.Tools.Business.Salesperson::MenuReady`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x730`

## pseudocode

```c

```

## disassembly

```asm
0x730  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteUser()
0x735  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x73a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x73f  brfalse.s loc_76D
0x741  ldarg.2
0x742  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_Menu()
0x747  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x74c  ldarg.2
0x74d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_Menu()
0x752  ldarg.0
0x753  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x758  ldstr    aMenuitemLabelA// "MenuItem_Label_AssignTerritory"
0x75d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x762  ldstr    aModifymembersh// "ModifyMembership('crmGrid', 'crmGrid', "...
0x767  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x76c  pop
0x76d  ret
```
