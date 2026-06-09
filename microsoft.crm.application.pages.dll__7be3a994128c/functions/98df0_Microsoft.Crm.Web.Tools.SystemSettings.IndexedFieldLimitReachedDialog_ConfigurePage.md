# Microsoft.Crm.Web.Tools.SystemSettings.IndexedFieldLimitReachedDialog::ConfigurePage

- ea: `0x98df0`
- end: `0x98e8e`
- name: `Microsoft.Crm.Web.Tools.SystemSettings.IndexedFieldLimitReachedDialog::ConfigurePage`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x98dfc`: `/_common/styles/dialogs.css.aspx`
- `0x98e29`: `SystemCustomization.SystemSettingsDialog.RelevanceSearchConfiguration.IndexedFieldLimitReached.Title`
- `0x98e43`: `SystemCustomization.SystemSettingsDialog.RelevanceSearchConfiguration.IndexedFieldLimitReached.Description`
- `0x98e5a`: `<a id='IndexedFieldLimitReachedLearnMore' class='default-link' target='_blank' href='`
- `0x98e5f`: `http://go.microsoft.com/fwlink/p/?LinkID=623061`

## pseudocode

```c

```

## disassembly

```asm
0x98df0  ldarg.0
0x98df1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x98df6  ldarg.0
0x98df7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x98dfc  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x98e01  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x98e06  ldarg.0
0x98e07  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x98e0c  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x98e11  ldnull
0x98e12  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x98e17  ldarg.0
0x98e18  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x98e1d  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x98e22  stloc.0
0x98e23  ldloc.0
0x98e24  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x98e29  ldstr    aSystemcustomiz_240// "SystemCustomization.SystemSettingsDialo"...
0x98e2e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98e33  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x98e38  ldarg.0
0x98e39  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x98e3e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x98e43  ldstr    aSystemcustomiz_241// "SystemCustomization.SystemSettingsDialo"...
0x98e48  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98e4d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0x98e52  ldc.i4.2
0x98e53  newarr   [mscorlib]System.Object
0x98e58  dup
0x98e59  ldc.i4.0
0x98e5a  ldstr    aAIdIndexedfiel// "<a id='IndexedFieldLimitReachedLearnMor"...
0x98e5f  ldstr    aHttpGoMicrosof_13// "http://go.microsoft.com/fwlink/p/?LinkI"...
0x98e64  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendUserUILanguageClcid(string)
0x98e69  ldstr    asc_144456// "'>"
0x98e6e  call     string [mscorlib]System.String::Concat(string, string, string)
0x98e73  stelem.ref
0x98e74  dup
0x98e75  ldc.i4.1
0x98e76  ldstr    aA// "</a>"
0x98e7b  stelem.ref
0x98e7c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x98e81  stfld    string Microsoft.Crm.Web.Tools.SystemSettings.IndexedFieldLimitReachedDialog::dialogBody
0x98e86  ldloc.0
0x98e87  ldc.i4.1
0x98e88  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x98e8d  ret
```
