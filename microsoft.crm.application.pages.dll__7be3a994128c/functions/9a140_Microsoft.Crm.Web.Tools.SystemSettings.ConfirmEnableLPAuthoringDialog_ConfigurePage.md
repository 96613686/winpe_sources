# Microsoft.Crm.Web.Tools.SystemSettings.ConfirmEnableLPAuthoringDialog::ConfigurePage

- ea: `0x9a140`
- end: `0x9a219`
- name: `Microsoft.Crm.Web.Tools.SystemSettings.ConfirmEnableLPAuthoringDialog::ConfigurePage`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x9a14c`: `/_common/styles/dialogs.css.aspx`
- `0x9a179`: `SystemCustomization.SystemSettingsDialog.EnableLearningPathAuthoring.ConfirmDialog.Title`
- `0x9a193`: `SystemCustomization.SystemSettingsDialog.EnableLearningPathAuthoring.ConfirmDialog.Description`
- `0x9a1aa`: `<a id='LPAuthoringFullPrivacyDisclaimer' class='default-link' target='_blank' href='`
- `0x9a1af`: `http://go.microsoft.com/fwlink/?LinkID=528361`
- `0x9a1ce`: `<a id='LPAuthoringLearnMore' class='default-link' target='_blank' href='`
- `0x9a1d3`: `http://go.microsoft.com/fwlink/p/?LinkID=849248`

## pseudocode

```c

```

## disassembly

```asm
0x9a140  ldarg.0
0x9a141  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x9a146  ldarg.0
0x9a147  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9a14c  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x9a151  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9a156  ldarg.0
0x9a157  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9a15c  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x9a161  ldnull
0x9a162  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x9a167  ldarg.0
0x9a168  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9a16d  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x9a172  stloc.0
0x9a173  ldloc.0
0x9a174  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9a179  ldstr    aSystemcustomiz_250// "SystemCustomization.SystemSettingsDialo"...
0x9a17e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a183  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x9a188  ldarg.0
0x9a189  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9a18e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9a193  ldstr    aSystemcustomiz_251// "SystemCustomization.SystemSettingsDialo"...
0x9a198  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a19d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0x9a1a2  ldc.i4.4
0x9a1a3  newarr   [mscorlib]System.Object
0x9a1a8  dup
0x9a1a9  ldc.i4.0
0x9a1aa  ldstr    aAIdLpauthoring// "<a id='LPAuthoringFullPrivacyDisclaimer"...
0x9a1af  ldstr    aHttpGoMicrosof_16// "http://go.microsoft.com/fwlink/?LinkID="...
0x9a1b4  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendUserUILanguageClcid(string)
0x9a1b9  ldstr    asc_144456// "'>"
0x9a1be  call     string [mscorlib]System.String::Concat(string, string, string)
0x9a1c3  stelem.ref
0x9a1c4  dup
0x9a1c5  ldc.i4.1
0x9a1c6  ldstr    aA// "</a>"
0x9a1cb  stelem.ref
0x9a1cc  dup
0x9a1cd  ldc.i4.2
0x9a1ce  ldstr    aAIdLpauthoring_0// "<a id='LPAuthoringLearnMore' class='def"...
0x9a1d3  ldstr    aHttpGoMicrosof_17// "http://go.microsoft.com/fwlink/p/?LinkI"...
0x9a1d8  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendUserUILanguageClcid(string)
0x9a1dd  ldstr    asc_144456// "'>"
0x9a1e2  call     string [mscorlib]System.String::Concat(string, string, string)
0x9a1e7  stelem.ref
0x9a1e8  dup
0x9a1e9  ldc.i4.3
0x9a1ea  ldstr    aA// "</a>"
0x9a1ef  stelem.ref
0x9a1f0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9a1f5  stfld    string Microsoft.Crm.Web.Tools.SystemSettings.ConfirmEnableLPAuthoringDialog::dialogBody
0x9a1fa  ldloc.0
0x9a1fb  ldloc.0
0x9a1fc  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::get_DialogTitle()
0x9a201  ldarg.0
0x9a202  ldfld    string Microsoft.Crm.Web.Tools.SystemSettings.ConfirmEnableLPAuthoringDialog::dialogBody
0x9a207  call     string [mscorlib]System.String::Concat(string, string)
0x9a20c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_HeaderTextForNarration(string)
0x9a211  ldloc.0
0x9a212  ldc.i4.3
0x9a213  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x9a218  ret
```
