# Microsoft.Crm.Marketing.Web.MA.CampaignActivity.Dialogs.ConfirmPropagation::ConfigureForm

- ea: `0xc70`
- end: `0xdf0`
- name: `Microsoft.Crm.Marketing.Web.MA.CampaignActivity.Dialogs.ConfirmPropagation::ConfigureForm`
- size: `384`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xc70`
- `0xe00`

## pseudocode

```c

```

## disassembly

```asm
0xc70  ldarg.0
0xc71  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0xc76  ldarg.0
0xc77  ldarg.0
0xc78  ldstr    aConfirmPropaga// "Confirm_Propagation_Dlg_Header"
0xc7d  ldarg.0
0xc7e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xc83  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xc88  ldstr    aEntitytypecode// "EntityTypeCode"
0xc8d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc92  call     instance string Microsoft.Crm.Marketing.Web.MA.CampaignActivity.Dialogs.ConfirmPropagation::GetResourceStringWithoutEncoding(string resourceId, string entityCode)
0xc97  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0xc9c  ldarg.0
0xc9d  ldarg.0
0xc9e  ldstr    aConfirmPropaga_0// "Confirm_Propagation_Dlg_Desc"
0xca3  ldarg.0
0xca4  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xca9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xcae  ldstr    aEntitytypecode// "EntityTypeCode"
0xcb3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xcb8  call     instance string Microsoft.Crm.Marketing.Web.MA.CampaignActivity.Dialogs.ConfirmPropagation::GetResourceStringWithoutEncoding(string resourceId, string entityCode)
0xcbd  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0xcc2  ldarg.0
0xcc3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xcc8  ldarg.0
0xcc9  call     instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_DialogTitle()
0xcce  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0xcd3  ldarg.0
0xcd4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xcd9  ldstr    aLocidMcQueueMa// "LOCID_MC_QUEUE_MANDATORY"
0xcde  ldarg.0
0xcdf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xce4  ldstr    aMcAlertChooseq// "MC_Alert_ChooseQueue"
0xce9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcee  ldc.i4.0
0xcef  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xcf4  ldarg.0
0xcf5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xcfa  ldstr    aLocidMcOwnerMa// "LOCID_MC_OWNER_MANDATORY"
0xcff  ldarg.0
0xd00  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd05  ldstr    aMcAlertChooseo// "MC_Alert_ChooseOwnerOption"
0xd0a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd0f  ldc.i4.0
0xd10  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd15  ldarg.0
0xd16  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xd1b  ldc.i4.1
0xd1c  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0xd21  stloc.0
0xd22  ldarg.0
0xd23  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xd28  ldloc.0
0xd29  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::get_Item(int32)
0xd2e  ldstr    aConfirmPropaga_1// "Confirm_Propagation_Dlg_Distribute"
0xd33  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_ResourceId(string)
0xd38  ldarg.0
0xd39  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xd3e  ldc.i4.2
0xd3f  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0xd44  pop
0xd45  ldarg.0
0xd46  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xd4b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xd50  ldstr    aEntitytypecode// "EntityTypeCode"
0xd55  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xd5a  ldc.i4.7
0xd5b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd60  call     int16 [mscorlib]System.Int16::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0xd65  ldc.i4   0x106A
0xd6a  bne.un.s loc_D84
0xd6c  ldarg.0
0xd6d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.Crm.Marketing.Web.MA.CampaignActivity.Dialogs.ConfirmPropagation::SendEmail
0xd72  ldc.i4.0
0xd73  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlControl::set_Disabled(bool)
0xd78  ldarg.0
0xd79  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.Crm.Marketing.Web.MA.CampaignActivity.Dialogs.ConfirmPropagation::SendEmail
0xd7e  ldc.i4.1
0xd7f  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox::set_Checked(bool)
0xd84  ldarg.0
0xd85  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Web.MA.CampaignActivity.Dialogs.ConfirmPropagation::ActivityLookup
0xd8a  ldstr    aSingle// "single"
0xd8f  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupStyle(string)
0xd94  ldarg.0
0xd95  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Web.MA.CampaignActivity.Dialogs.ConfirmPropagation::ActivityLookup
0xd9a  ldc.i4.2
0xd9b  newarr   [mscorlib]System.Int32
0xda0  dup
0xda1  ldc.i4.0
0xda2  ldc.i4.8
0xda3  stelem.i4
0xda4  dup
0xda5  ldc.i4.1
0xda6  ldc.i4.s 9
0xda8  stelem.i4
0xda9  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0xdae  ldarg.0
0xdaf  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Web.MA.CampaignActivity.Dialogs.ConfirmPropagation::ActivityLookup
0xdb4  ldc.i4.1
0xdb5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0xdba  ldarg.0
0xdbb  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Web.MA.CampaignActivity.Dialogs.ConfirmPropagation::QueueLookup
0xdc0  ldstr    aSingle// "single"
0xdc5  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupStyle(string)
0xdca  ldarg.0
0xdcb  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Web.MA.CampaignActivity.Dialogs.ConfirmPropagation::QueueLookup
0xdd0  ldc.i4.1
0xdd1  newarr   [mscorlib]System.Int32
0xdd6  dup
0xdd7  ldc.i4.0
0xdd8  ldc.i4   0x7E4
0xddd  stelem.i4
0xdde  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0xde3  ldarg.0
0xde4  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Marketing.Web.MA.CampaignActivity.Dialogs.ConfirmPropagation::QueueLookup
0xde9  ldc.i4.1
0xdea  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0xdef  ret
```
