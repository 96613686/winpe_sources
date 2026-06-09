# Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::ConfigurePage

- ea: `0x70`
- end: `0x156`
- name: `Microsoft.Crm.Sales.Dialogs.CloseOpportunityPage::ConfigurePage`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x70  ldarg.0
0x71  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::ConfigurePage()
0x76  ldarg.0
0x77  ldstr    aOpportunity// "opportunity"
0x7c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x81  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x86  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x8b  ldarg.0
0x8c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x91  ldstr    aLocidIncorrect// "LOCID_INCORRECT_ACTUAL_REVENUE"
0x96  ldarg.0
0x97  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9c  ldstr    aWebSfaOppsDlgC// "Web.SFA.opps.dlg_closeopp.aspx_37"
0xa1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa6  ldc.i4.0
0xa7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xac  ldarg.0
0xad  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb2  ldstr    aLocidCloseDate// "LOCID_CLOSE_DATE_NOT_SUPPLIED"
0xb7  ldarg.0
0xb8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xbd  ldstr    aWebSfaOppsDlgC_0// "Web.SFA.opps.dlg_closeopp.aspx_67"
0xc2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc7  ldc.i4.0
0xc8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xcd  ldarg.0
0xce  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd3  ldstr    aLocidActRevenu// "LOCID_ACT_REVENUE_NOT_SUPPLIED"
0xd8  ldarg.0
0xd9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xde  ldstr    aWebSfaOppsDlgC_1// "Web.SFA.opps.dlg_closeopp.aspx_74"
0xe3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe8  ldc.i4.0
0xe9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xee  ldarg.0
0xef  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf4  ldstr    aLocidFormRequi// "LOCID_FORM_REQUIRED_ALT"
0xf9  ldarg.0
0xfa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xff  ldstr    aFormsRequiredA// "Forms.Required.AltTag"
0x104  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x109  ldc.i4.0
0x10a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10f  ldarg.0
0x110  ldarg.0
0x111  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x116  ldstr    aCloseOppDlgTit// "Close_Opp_Dlg_Title"
0x11b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x120  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x125  ldarg.0
0x126  ldarg.0
0x127  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12c  ldstr    aCloseOppDlgDes// "Close_Opp_Dlg_Desc"
0x131  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x136  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x13b  ldarg.0
0x13c  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x141  ldc.i4.1
0x142  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x147  pop
0x148  ldarg.0
0x149  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x14e  ldc.i4.2
0x14f  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x154  pop
0x155  ret
```
