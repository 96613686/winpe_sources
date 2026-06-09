# Microsoft.Crm.Service.Web.Tools.ServiceManagement.ServiceManagementPage::ConfigurePage

- ea: `0x7cc0`
- end: `0x7d09`
- name: `Microsoft.Crm.Service.Web.Tools.ServiceManagement.ServiceManagementPage::ConfigurePage`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x7cc1`: `servicemanagement.aspx`
- `0x7ccc`: `servicemanagement`
- `0x7cd7`: `nav_servicemanagement`

## pseudocode

```c

```

## disassembly

```asm
0x7cc0  ldarg.0
0x7cc1  ldstr    aServicemanagem// "servicemanagement.aspx"
0x7cc6  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.AppNavPage::set_Homepage(string)
0x7ccb  ldarg.0
0x7ccc  ldstr    aServicemanagem_0// "servicemanagement"
0x7cd1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.AppNavPage::set_Area(string)
0x7cd6  ldarg.0
0x7cd7  ldstr    aNavServicemana// "nav_servicemanagement"
0x7cdc  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.AppNavPage::set_Nav(string)
0x7ce1  ldarg.0
0x7ce2  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.AppNavPage::ConfigurePage()
0x7ce7  ldarg.0
0x7ce8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7ced  ldstr    aLocidMicrosoft// "LOCID_MICROSOFT_CRM"
0x7cf2  ldarg.0
0x7cf3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7cf8  ldstr    aMicrosoftCrm// "Microsoft_CRM"
0x7cfd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d02  ldc.i4.0
0x7d03  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d08  ret
```
