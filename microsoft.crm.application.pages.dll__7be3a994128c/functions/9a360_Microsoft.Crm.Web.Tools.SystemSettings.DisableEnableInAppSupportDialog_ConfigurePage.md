# Microsoft.Crm.Web.Tools.SystemSettings.DisableEnableInAppSupportDialog::ConfigurePage

- ea: `0x9a360`
- end: `0x9a439`
- name: `Microsoft.Crm.Web.Tools.SystemSettings.DisableEnableInAppSupportDialog::ConfigurePage`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x9a36c`: `/_common/styles/dialogs.css.aspx`
- `0x9a3cf`: `http://go.microsoft.com/fwlink/?LinkID=528361`
- `0x9a3ca`: `<a id='InAppSupportFullPrivacyDisclaimer' class='default-link' target='_blank' href='`
- `0x9a3ee`: `<a id='InAppSupportLearnMore' class='default-link' target='_blank' href='`
- `0x9a3f3`: `http://go.microsoft.com/fwlink/p/?LinkID=852333`

## pseudocode

```c

```

## disassembly

```asm
0x9a360  ldarg.0
0x9a361  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x9a366  ldarg.0
0x9a367  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9a36c  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x9a371  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9a376  ldarg.0
0x9a377  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9a37c  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x9a381  ldnull
0x9a382  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x9a387  ldarg.0
0x9a388  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9a38d  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x9a392  stloc.0
0x9a393  ldloc.0
0x9a394  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9a399  ldstr    aSystemcustomiz_254// "SystemCustomization.SystemSettingsDialo"...
0x9a39e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a3a3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x9a3a8  ldarg.0
0x9a3a9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9a3ae  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9a3b3  ldstr    aSystemcustomiz_255// "SystemCustomization.SystemSettingsDialo"...
0x9a3b8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a3bd  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0x9a3c2  ldc.i4.4
0x9a3c3  newarr   [mscorlib]System.Object
0x9a3c8  dup
0x9a3c9  ldc.i4.0
0x9a3ca  ldstr    aAIdInappsuppor// "<a id='InAppSupportFullPrivacyDisclaime"...
0x9a3cf  ldstr    aHttpGoMicrosof_16// "http://go.microsoft.com/fwlink/?LinkID="...
0x9a3d4  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendUserUILanguageClcid(string)
0x9a3d9  ldstr    asc_144456// "'>"
0x9a3de  call     string [mscorlib]System.String::Concat(string, string, string)
0x9a3e3  stelem.ref
0x9a3e4  dup
0x9a3e5  ldc.i4.1
0x9a3e6  ldstr    aA// "</a>"
0x9a3eb  stelem.ref
0x9a3ec  dup
0x9a3ed  ldc.i4.2
0x9a3ee  ldstr    aAIdInappsuppor_0// "<a id='InAppSupportLearnMore' class='de"...
0x9a3f3  ldstr    aHttpGoMicrosof_18// "http://go.microsoft.com/fwlink/p/?LinkI"...
0x9a3f8  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendUserUILanguageClcid(string)
0x9a3fd  ldstr    asc_144456// "'>"
0x9a402  call     string [mscorlib]System.String::Concat(string, string, string)
0x9a407  stelem.ref
0x9a408  dup
0x9a409  ldc.i4.3
0x9a40a  ldstr    aA// "</a>"
0x9a40f  stelem.ref
0x9a410  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9a415  stfld    string Microsoft.Crm.Web.Tools.SystemSettings.DisableEnableInAppSupportDialog::dialogBody
0x9a41a  ldloc.0
0x9a41b  ldloc.0
0x9a41c  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::get_DialogTitle()
0x9a421  ldarg.0
0x9a422  ldfld    string Microsoft.Crm.Web.Tools.SystemSettings.DisableEnableInAppSupportDialog::dialogBody
0x9a427  call     string [mscorlib]System.String::Concat(string, string)
0x9a42c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_HeaderTextForNarration(string)
0x9a431  ldloc.0
0x9a432  ldc.i4.3
0x9a433  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x9a438  ret
```
