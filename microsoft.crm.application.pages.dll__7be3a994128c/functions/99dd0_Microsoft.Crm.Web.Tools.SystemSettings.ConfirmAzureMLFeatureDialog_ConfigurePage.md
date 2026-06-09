# Microsoft.Crm.Web.Tools.SystemSettings.ConfirmAzureMLFeatureDialog::ConfigurePage

- ea: `0x99dd0`
- end: `0x99f06`
- name: `Microsoft.Crm.Web.Tools.SystemSettings.ConfirmAzureMLFeatureDialog::ConfigurePage`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x99dd0`

## string_xrefs

- `0x99ddc`: `/_common/styles/dialogs.css.aspx`
- `0x99ebc`: `http://go.microsoft.com/fwlink/p/?LinkID=746137`
- `0x99e20`: `rdProductRecommendationsPreview`
- `0x99e41`: `SystemCustomization.SystemSettingsDialog.EnableProductRecommendations.ConfirmDialog.Title`
- `0x99e55`: `SystemCustomization.SystemSettingsDialog.EnableProductRecommendations.ConfirmDialog.Description`
- `0x99eb4`: `' class='default-link' target='_blank' href='`

## pseudocode

```c

```

## disassembly

```asm
0x99dd0  ldarg.0
0x99dd1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x99dd6  ldarg.0
0x99dd7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x99ddc  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x99de1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x99de6  ldarg.0
0x99de7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x99dec  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x99df1  ldnull
0x99df2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x99df7  ldarg.0
0x99df8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x99dfd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x99e02  ldstr    aRadioid// "radioId"
0x99e07  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x99e0c  stloc.0
0x99e0d  ldsfld   string [mscorlib]System.String::Empty
0x99e12  stloc.1
0x99e13  ldarg.0
0x99e14  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x99e19  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x99e1e  stloc.2
0x99e1f  ldloc.0
0x99e20  ldstr    aRdproductrecom// "rdProductRecommendationsPreview"
0x99e25  call     bool [mscorlib]System.String::op_Equality(string, string)
0x99e2a  brtrue.s loc_99E3B
0x99e2c  ldloc.0
0x99e2d  ldstr    aRdtextanalytic// "rdTextAnalyticsPreview"
0x99e32  call     bool [mscorlib]System.String::op_Equality(string, string)
0x99e37  brtrue.s loc_99E62
0x99e39  br.s     loc_99E87
0x99e3b  ldloc.2
0x99e3c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x99e41  ldstr    aSystemcustomiz_242// "SystemCustomization.SystemSettingsDialo"...
0x99e46  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99e4b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x99e50  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x99e55  ldstr    aSystemcustomiz_243// "SystemCustomization.SystemSettingsDialo"...
0x99e5a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99e5f  stloc.1
0x99e60  br.s     loc_99E87
0x99e62  ldloc.2
0x99e63  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x99e68  ldstr    aSystemcustomiz_244// "SystemCustomization.SystemSettingsDialo"...
0x99e6d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99e72  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x99e77  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x99e7c  ldstr    aSystemcustomiz_245// "SystemCustomization.SystemSettingsDialo"...
0x99e81  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99e86  stloc.1
0x99e87  ldarg.0
0x99e88  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x99e8d  ldloc.1
0x99e8e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0x99e93  ldc.i4.2
0x99e94  newarr   [mscorlib]System.Object
0x99e99  dup
0x99e9a  ldc.i4.0
0x99e9b  ldc.i4.5
0x99e9c  newarr   [mscorlib]System.String
0x99ea1  dup
0x99ea2  ldc.i4.0
0x99ea3  ldstr    aAId// "<a id='"
0x99ea8  stelem.ref
0x99ea9  dup
0x99eaa  ldc.i4.1
0x99eab  ldloc.0
0x99eac  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x99eb1  stelem.ref
0x99eb2  dup
0x99eb3  ldc.i4.2
0x99eb4  ldstr    aClassDefaultLi_1// "' class='default-link' target='_blank' "...
0x99eb9  stelem.ref
0x99eba  dup
0x99ebb  ldc.i4.3
0x99ebc  ldstr    aHttpGoMicrosof_6// "http://go.microsoft.com/fwlink/p/?LinkI"...
0x99ec1  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendUserUILanguageClcid(string)
0x99ec6  stelem.ref
0x99ec7  dup
0x99ec8  ldc.i4.4
0x99ec9  ldstr    asc_144456// "'>"
0x99ece  stelem.ref
0x99ecf  call     string [mscorlib]System.String::Concat(string[])
0x99ed4  stelem.ref
0x99ed5  dup
0x99ed6  ldc.i4.1
0x99ed7  ldstr    aA// "</a>"
0x99edc  stelem.ref
0x99edd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x99ee2  stfld    string Microsoft.Crm.Web.Tools.SystemSettings.ConfirmAzureMLFeatureDialog::dialogBody
0x99ee7  ldloc.2
0x99ee8  ldloc.2
0x99ee9  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::get_DialogTitle()
0x99eee  ldarg.0
0x99eef  ldfld    string Microsoft.Crm.Web.Tools.SystemSettings.ConfirmAzureMLFeatureDialog::dialogBody
0x99ef4  call     string [mscorlib]System.String::Concat(string, string)
0x99ef9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_HeaderTextForNarration(string)
0x99efe  ldloc.2
0x99eff  ldc.i4.3
0x99f00  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x99f05  ret
```
