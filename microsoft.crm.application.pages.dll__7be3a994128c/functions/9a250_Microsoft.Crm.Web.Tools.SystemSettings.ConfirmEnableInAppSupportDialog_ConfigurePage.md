# Microsoft.Crm.Web.Tools.SystemSettings.ConfirmEnableInAppSupportDialog::ConfigurePage

- ea: `0x9a250`
- end: `0x9a329`
- name: `Microsoft.Crm.Web.Tools.SystemSettings.ConfirmEnableInAppSupportDialog::ConfigurePage`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x9a25c`: `/_common/styles/dialogs.css.aspx`
- `0x9a2bf`: `http://go.microsoft.com/fwlink/?LinkID=528361`
- `0x9a2ba`: `<a id='InAppSupportFullPrivacyDisclaimer' class='default-link' target='_blank' href='`
- `0x9a2de`: `<a id='InAppSupportLearnMore' class='default-link' target='_blank' href='`
- `0x9a2e3`: `http://go.microsoft.com/fwlink/p/?LinkID=852333`

## pseudocode

```c

```

## disassembly

```asm
0x9a250  ldarg.0
0x9a251  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x9a256  ldarg.0
0x9a257  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9a25c  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x9a261  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9a266  ldarg.0
0x9a267  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9a26c  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x9a271  ldnull
0x9a272  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x9a277  ldarg.0
0x9a278  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9a27d  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x9a282  stloc.0
0x9a283  ldloc.0
0x9a284  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9a289  ldstr    aSystemcustomiz_252// "SystemCustomization.SystemSettingsDialo"...
0x9a28e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a293  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x9a298  ldarg.0
0x9a299  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9a29e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9a2a3  ldstr    aSystemcustomiz_253// "SystemCustomization.SystemSettingsDialo"...
0x9a2a8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a2ad  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0x9a2b2  ldc.i4.4
0x9a2b3  newarr   [mscorlib]System.Object
0x9a2b8  dup
0x9a2b9  ldc.i4.0
0x9a2ba  ldstr    aAIdInappsuppor// "<a id='InAppSupportFullPrivacyDisclaime"...
0x9a2bf  ldstr    aHttpGoMicrosof_16// "http://go.microsoft.com/fwlink/?LinkID="...
0x9a2c4  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendUserUILanguageClcid(string)
0x9a2c9  ldstr    asc_144456// "'>"
0x9a2ce  call     string [mscorlib]System.String::Concat(string, string, string)
0x9a2d3  stelem.ref
0x9a2d4  dup
0x9a2d5  ldc.i4.1
0x9a2d6  ldstr    aA// "</a>"
0x9a2db  stelem.ref
0x9a2dc  dup
0x9a2dd  ldc.i4.2
0x9a2de  ldstr    aAIdInappsuppor_0// "<a id='InAppSupportLearnMore' class='de"...
0x9a2e3  ldstr    aHttpGoMicrosof_18// "http://go.microsoft.com/fwlink/p/?LinkI"...
0x9a2e8  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendUserUILanguageClcid(string)
0x9a2ed  ldstr    asc_144456// "'>"
0x9a2f2  call     string [mscorlib]System.String::Concat(string, string, string)
0x9a2f7  stelem.ref
0x9a2f8  dup
0x9a2f9  ldc.i4.3
0x9a2fa  ldstr    aA// "</a>"
0x9a2ff  stelem.ref
0x9a300  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9a305  stfld    string Microsoft.Crm.Web.Tools.SystemSettings.ConfirmEnableInAppSupportDialog::dialogBody
0x9a30a  ldloc.0
0x9a30b  ldloc.0
0x9a30c  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::get_DialogTitle()
0x9a311  ldarg.0
0x9a312  ldfld    string Microsoft.Crm.Web.Tools.SystemSettings.ConfirmEnableInAppSupportDialog::dialogBody
0x9a317  call     string [mscorlib]System.String::Concat(string, string)
0x9a31c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_HeaderTextForNarration(string)
0x9a321  ldloc.0
0x9a322  ldc.i4.3
0x9a323  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x9a328  ret
```
