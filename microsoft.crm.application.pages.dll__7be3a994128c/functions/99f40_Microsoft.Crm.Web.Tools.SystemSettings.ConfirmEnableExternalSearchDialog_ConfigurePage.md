# Microsoft.Crm.Web.Tools.SystemSettings.ConfirmEnableExternalSearchDialog::ConfigurePage

- ea: `0x99f40`
- end: `0x9a061`
- name: `Microsoft.Crm.Web.Tools.SystemSettings.ConfirmEnableExternalSearchDialog::ConfigurePage`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x99f40`

## string_xrefs

- `0x99f4c`: `/_common/styles/dialogs.css.aspx`
- `0x99ff2`: `<a id='ExternalSearchFullPrivacyDisclaimer' class='default-link' target='_blank' href='`
- `0x99ff7`: `http://go.microsoft.com/fwlink/p/?LinkID=623063`
- `0x9a016`: `<a id='ExternalSearchLearnMore' class='default-link' target='_blank' href='`
- `0x9a01b`: `http://go.microsoft.com/fwlink/p/?LinkID=623062`

## pseudocode

```c

```

## disassembly

```asm
0x99f40  ldarg.0
0x99f41  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x99f46  ldarg.0
0x99f47  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x99f4c  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x99f51  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x99f56  ldarg.0
0x99f57  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x99f5c  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x99f61  ldnull
0x99f62  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x99f67  ldarg.0
0x99f68  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x99f6d  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x99f72  stloc.0
0x99f73  ldarg.0
0x99f74  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x99f79  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x99f7e  ldstr    aIsenabling// "isEnabling"
0x99f83  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x99f88  ldstr    aTrue_0// "true"
0x99f8d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x99f92  stloc.1
0x99f93  ldloc.0
0x99f94  ldloc.1
0x99f95  brtrue.s loc_99FA8
0x99f97  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x99f9c  ldstr    aSystemcustomiz_246// "SystemCustomization.SystemSettingsDialo"...
0x99fa1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99fa6  br.s     loc_99FB7
0x99fa8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x99fad  ldstr    aSystemcustomiz_247// "SystemCustomization.SystemSettingsDialo"...
0x99fb2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99fb7  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x99fbc  ldarg.0
0x99fbd  ldloc.1
0x99fbe  brtrue.s loc_99FD1
0x99fc0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x99fc5  ldstr    aSystemcustomiz_248// "SystemCustomization.SystemSettingsDialo"...
0x99fca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99fcf  br.s     loc_9A03D
0x99fd1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x99fd6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x99fdb  ldstr    aSystemcustomiz_249// "SystemCustomization.SystemSettingsDialo"...
0x99fe0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99fe5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0x99fea  ldc.i4.4
0x99feb  newarr   [mscorlib]System.Object
0x99ff0  dup
0x99ff1  ldc.i4.0
0x99ff2  ldstr    aAIdExternalsea_0// "<a id='ExternalSearchFullPrivacyDisclai"...
0x99ff7  ldstr    aHttpGoMicrosof_14// "http://go.microsoft.com/fwlink/p/?LinkI"...
0x99ffc  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendUserUILanguageClcid(string)
0x9a001  ldstr    asc_144456// "'>"
0x9a006  call     string [mscorlib]System.String::Concat(string, string, string)
0x9a00b  stelem.ref
0x9a00c  dup
0x9a00d  ldc.i4.1
0x9a00e  ldstr    aA// "</a>"
0x9a013  stelem.ref
0x9a014  dup
0x9a015  ldc.i4.2
0x9a016  ldstr    aAIdExternalsea_1// "<a id='ExternalSearchLearnMore' class='"...
0x9a01b  ldstr    aHttpGoMicrosof_15// "http://go.microsoft.com/fwlink/p/?LinkI"...
0x9a020  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendUserUILanguageClcid(string)
0x9a025  ldstr    asc_144456// "'>"
0x9a02a  call     string [mscorlib]System.String::Concat(string, string, string)
0x9a02f  stelem.ref
0x9a030  dup
0x9a031  ldc.i4.3
0x9a032  ldstr    aA// "</a>"
0x9a037  stelem.ref
0x9a038  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9a03d  stfld    string Microsoft.Crm.Web.Tools.SystemSettings.ConfirmEnableExternalSearchDialog::dialogBody
0x9a042  ldloc.0
0x9a043  ldloc.0
0x9a044  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::get_DialogTitle()
0x9a049  ldarg.0
0x9a04a  ldfld    string Microsoft.Crm.Web.Tools.SystemSettings.ConfirmEnableExternalSearchDialog::dialogBody
0x9a04f  call     string [mscorlib]System.String::Concat(string, string)
0x9a054  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_HeaderTextForNarration(string)
0x9a059  ldloc.0
0x9a05a  ldc.i4.3
0x9a05b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x9a060  ret
```
