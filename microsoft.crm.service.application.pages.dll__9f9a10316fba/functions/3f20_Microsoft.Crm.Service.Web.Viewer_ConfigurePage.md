# Microsoft.Crm.Service.Web.Viewer::ConfigurePage

- ea: `0x3f20`
- end: `0x3ff4`
- name: `Microsoft.Crm.Service.Web.Viewer::ConfigurePage`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x3f20`

## string_xrefs

- `0x3f6c`: `/_static/_common/scripts/print.js`

## pseudocode

```c

```

## disassembly

```asm
0x3f20  ldarg.0
0x3f21  ldarg.0
0x3f22  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x3f27  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3f2c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsIosDevice(class [System.Web]System.Web.HttpRequest)
0x3f31  stfld    bool Microsoft.Crm.Service.Web.Viewer::isIOS
0x3f36  ldarg.0
0x3f37  ldarg.0
0x3f38  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3f3d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3f42  ldstr    aId// "id"
0x3f47  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3f4c  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetGuid(string)
0x3f51  stfld    string Microsoft.Crm.Service.Web.Viewer::_contentId
0x3f56  ldarg.0
0x3f57  ldfld    string Microsoft.Crm.Service.Web.Viewer::_contentId
0x3f5c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3f61  brtrue   loc_3FF3
0x3f66  ldarg.0
0x3f67  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3f6c  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/print.js"
0x3f71  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x3f76  ldarg.0
0x3f77  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3f7c  ldstr    aGuidcontentid// "_guidContentId"
0x3f81  ldarg.0
0x3f82  ldfld    string Microsoft.Crm.Service.Web.Viewer::_contentId
0x3f87  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x3f8c  ldarg.0
0x3f8d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3f92  ldstr    aLocidKbviewerS// "LOCID_KBVIEWER_SHOW"
0x3f97  ldarg.0
0x3f98  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3f9d  ldstr    aWebCsArticlesV// "Web.CS.articles.Viewer.default.aspx.Sho"...
0x3fa2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3fa7  ldc.i4.0
0x3fa8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3fad  ldarg.0
0x3fae  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3fb3  ldstr    aLocidKbviewerH// "LOCID_KBVIEWER_HIDE"
0x3fb8  ldarg.0
0x3fb9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3fbe  ldstr    aWebCsArticlesV_0// "Web.CS.articles.Viewer.default.aspx.Hid"...
0x3fc3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3fc8  ldc.i4.0
0x3fc9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3fce  ldarg.0
0x3fcf  ldfld    class [System.Web]System.Web.UI.LiteralControl Microsoft.Crm.Service.Web.Viewer::printMain
0x3fd4  ldstr    aIframeIdPrintm// "<iframe id=\"printMain\" name=\"printMa"...
0x3fd9  ldarg.0
0x3fda  ldfld    string Microsoft.Crm.Service.Web.Viewer::_contentId
0x3fdf  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x3fe4  ldstr    aIframe// "\"></iframe>"
0x3fe9  call     string [mscorlib]System.String::Concat(string, string, string)
0x3fee  callvirt instance void [System.Web]System.Web.UI.LiteralControl::set_Text(string)
0x3ff3  ret
```
