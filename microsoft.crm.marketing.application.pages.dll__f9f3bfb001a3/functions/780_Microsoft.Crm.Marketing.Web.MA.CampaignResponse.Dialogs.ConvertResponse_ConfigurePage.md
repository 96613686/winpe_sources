# Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::ConfigurePage

- ea: `0x780`
- end: `0x7c9`
- name: `Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ConvertResponse::ConfigurePage`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x780  ldarg.0
0x781  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::ConfigurePage()
0x786  ldarg.0
0x787  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x78c  ldstr    aLocidCustomerM// "LOCID_CUSTOMER_MUST_BE_SUPPLIED"
0x791  ldarg.0
0x792  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x797  ldstr    aAlertCustomerM// "Alert_Customer_Must_Be_Supplied"
0x79c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7a1  ldc.i4.0
0x7a2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7a7  ldarg.0
0x7a8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7ad  ldstr    aLocidLeadMustB// "LOCID_LEAD_MUST_BE_SUPPLIED"
0x7b2  ldarg.0
0x7b3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7b8  ldstr    aAlertLeadMustB// "Alert_Lead_Must_Be_Supplied"
0x7bd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7c2  ldc.i4.0
0x7c3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7c8  ret
```
