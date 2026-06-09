# Microsoft.Crm.Web.Tools.Admin.SystemAddOnPage::HandleNoUpdateMode

- ea: `0x8b920`
- end: `0x8b984`
- name: `Microsoft.Crm.Web.Tools.Admin.SystemAddOnPage::HandleNoUpdateMode`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x8b800`

## string_xrefs

- `0x8b927`: `AddOnWizard.NoUpdateMode.Warning`
- `0x8b958`: `Wizard_Button_Tooltip_AddLicense_NoUpdateMode`
- `0x8b963`: `Wizard_Button_Tooltip_AddStorage_NoUpdateMode`
- `0x8b96e`: `Wizard_Button_Tooltip_RemoveStorage_NoUpdateMode`
- `0x8b979`: `Wizard_Button_Tooltip_ViewOffers_NoUpdateMode`

## pseudocode

```c

```

## disassembly

```asm
0x8b920  ldarg.0
0x8b921  ldarg.0
0x8b922  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8b927  ldstr    aAddonwizardNou// "AddOnWizard.NoUpdateMode.Warning"
0x8b92c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8b931  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x8b936  stfld    string Microsoft.Crm.Web.Tools.Admin.SystemAddOnPage::warningMessageHtml
0x8b93b  ldarg.0
0x8b93c  ldc.i4.1
0x8b93d  stfld    bool Microsoft.Crm.Web.Tools.Admin.SystemAddOnPage::addLicenseButtonDisabled
0x8b942  ldarg.0
0x8b943  ldc.i4.1
0x8b944  stfld    bool Microsoft.Crm.Web.Tools.Admin.SystemAddOnPage::addStorageButtonDisabled
0x8b949  ldarg.0
0x8b94a  ldc.i4.1
0x8b94b  stfld    bool Microsoft.Crm.Web.Tools.Admin.SystemAddOnPage::removeStorageButtonDisabled
0x8b950  ldarg.0
0x8b951  ldc.i4.1
0x8b952  stfld    bool Microsoft.Crm.Web.Tools.Admin.SystemAddOnPage::viewOffersButtonDisabled
0x8b957  ldarg.0
0x8b958  ldstr    aWizardButtonTo_3// "Wizard_Button_Tooltip_AddLicense_NoUpda"...
0x8b95d  stfld    string Microsoft.Crm.Web.Tools.Admin.SystemAddOnPage::addLicenseButtonTooltip
0x8b962  ldarg.0
0x8b963  ldstr    aWizardButtonTo_4// "Wizard_Button_Tooltip_AddStorage_NoUpda"...
0x8b968  stfld    string Microsoft.Crm.Web.Tools.Admin.SystemAddOnPage::addStorageButtonTooltip
0x8b96d  ldarg.0
0x8b96e  ldstr    aWizardButtonTo_5// "Wizard_Button_Tooltip_RemoveStorage_NoU"...
0x8b973  stfld    string Microsoft.Crm.Web.Tools.Admin.SystemAddOnPage::removeStorageButtonTooltip
0x8b978  ldarg.0
0x8b979  ldstr    aWizardButtonTo_6// "Wizard_Button_Tooltip_ViewOffers_NoUpda"...
0x8b97e  stfld    string Microsoft.Crm.Web.Tools.Admin.SystemAddOnPage::viewOffersButtonTooltip
0x8b983  ret
```
