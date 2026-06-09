# Microsoft.Crm.Common.Application.Web.Pages.MobileErrorHandlerPage::ConfigureHeader

- ea: `0x132f0`
- end: `0x13386`
- name: `Microsoft.Crm.Common.Application.Web.Pages.MobileErrorHandlerPage::ConfigureHeader`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## string_xrefs

- `0x1331f`: `web._common.error.errorHandler.aspx_title`
- `0x1337b`: `/_common/styles/mobile/global.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x132f0  ldarg.0
0x132f1  ldfld    class [Microsoft.Crm.Mobile.Application.Components]Microsoft.Crm.Mobile.Application.Controls.MobileHeader Microsoft.Crm.Common.Application.Web.Pages.MobileErrorHandlerPage::MobileHeader
0x132f6  ldarg.0
0x132f7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x132fc  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.MobileUtility::AddSignoutJavascript(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager)
0x13301  ldarg.0
0x13302  ldfld    class [Microsoft.Crm.Mobile.Application.Components]Microsoft.Crm.Mobile.Application.Controls.MobileHeader Microsoft.Crm.Common.Application.Web.Pages.MobileErrorHandlerPage::MobileHeader
0x13307  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1330c  ldstr    a01_0// "{0} : {1}"
0x13311  ldc.i4.2
0x13312  newarr   [mscorlib]System.Object
0x13317  dup
0x13318  ldc.i4.0
0x13319  ldarg.0
0x1331a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1331f  ldstr    aWebCommonError_4// "web._common.error.errorHandler.aspx_tit"...
0x13324  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x13329  ldc.i4.1
0x1332a  newarr   [mscorlib]System.Object
0x1332f  dup
0x13330  ldc.i4.0
0x13331  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x13336  stelem.ref
0x13337  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x1333c  stelem.ref
0x1333d  dup
0x1333e  ldc.i4.1
0x1333f  ldarg.0
0x13340  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::ErrorTitle
0x13345  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::get_InnerText()
0x1334a  stelem.ref
0x1334b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13350  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x13355  ldarg.0
0x13356  ldfld    class [Microsoft.Crm.Mobile.Application.Components]Microsoft.Crm.Mobile.Application.Controls.MobileHeader Microsoft.Crm.Common.Application.Web.Pages.MobileErrorHandlerPage::MobileHeader
0x1335b  ldstr    aStaticMobileSt// "/_static/mobile/styles/global.css"
0x13360  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x13365  ldarg.0
0x13366  ldfld    class [Microsoft.Crm.Mobile.Application.Components]Microsoft.Crm.Mobile.Application.Controls.MobileHeader Microsoft.Crm.Common.Application.Web.Pages.MobileErrorHandlerPage::MobileHeader
0x1336b  ldstr    aStaticMobileSt_0// "/_static/mobile/styles/err.css"
0x13370  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x13375  ldarg.0
0x13376  ldfld    class [Microsoft.Crm.Mobile.Application.Components]Microsoft.Crm.Mobile.Application.Controls.MobileHeader Microsoft.Crm.Common.Application.Web.Pages.MobileErrorHandlerPage::MobileHeader
0x1337b  ldstr    aCommonStylesMo// "/_common/styles/mobile/global.css.aspx"
0x13380  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x13385  ret
```
