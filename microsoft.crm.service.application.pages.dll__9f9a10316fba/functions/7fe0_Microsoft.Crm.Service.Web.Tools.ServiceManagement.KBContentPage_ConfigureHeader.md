# Microsoft.Crm.Service.Web.Tools.ServiceManagement.KBContentPage::ConfigureHeader

- ea: `0x7fe0`
- end: `0x8108`
- name: `Microsoft.Crm.Service.Web.Tools.ServiceManagement.KBContentPage::ConfigureHeader`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7fe0`
- `0x8130`

## string_xrefs

- `0x803b`: `/_static/_common/scripts/Wall.Interfaces.js`
- `0x804b`: `/_static/_common/scripts/Wall.Control.js`
- `0x801b`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0x802b`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0x805b`: `/_common/styles/global.css.aspx`
- `0x80ee`: `INVALID_JSON`
- `0x80f8`: `SearchWidget.Invalid.JSON`

## pseudocode

```c

```

## disassembly

```asm
0x7fe0  ldarg.0
0x7fe1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::ConfigureHeader()
0x7fe6  ldarg.0
0x7fe7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7fec  ldc.i4.1
0x7fed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x7ff2  ldarg.0
0x7ff3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7ff8  ldc.i4.1
0x7ff9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQueryTemplate(bool)
0x7ffe  ldarg.0
0x7fff  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8004  ldc.i4.1
0x8005  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJSRender(bool)
0x800a  ldarg.0
0x800b  ldsfld   string [mscorlib]System.String::Empty
0x8010  stfld    string Microsoft.Crm.Service.Web.Tools.ServiceManagement.KBContentPage::articleRow
0x8015  ldarg.0
0x8016  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x801b  ldstr    aStaticCommonSc_6// "/_static/_common/scripts/jquery_ui_1.8."...
0x8020  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8025  ldarg.0
0x8026  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x802b  ldstr    aStaticCommonSc_7// "/_static/_common/scripts/CrmInternalUti"...
0x8030  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8035  ldarg.0
0x8036  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x803b  ldstr    aStaticCommonSc_0// "/_static/_common/scripts/Wall.Interface"...
0x8040  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8045  ldarg.0
0x8046  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x804b  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/Wall.Control.j"...
0x8050  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8055  ldarg.0
0x8056  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x805b  ldstr    aCommonStylesGl// "/_common/styles/global.css.aspx"
0x8060  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x8065  ldarg.0
0x8066  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x806b  ldstr    aSearchwidgetSe_3// "/SearchWidget/SearchWidget.css.aspx"
0x8070  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x8075  ldarg.0
0x8076  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x807b  ldstr    aStaticControls_4// "/_static/_controls/SearchWidget/SearchW"...
0x8080  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8085  ldarg.0
0x8086  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x808b  ldstr    aSearchwidgetwa// "searchWidgetWallStrings"
0x8090  ldarg.0
0x8091  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Service.Web.Tools.ServiceManagement.KBContentPage::GenerateClientStrings()
0x8096  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>)
0x809b  ldarg.0
0x809c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x80a1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x80a6  ldstr    aFormdata// "formdata"
0x80ab  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x80b0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x80b5  brtrue.s loc_80D2
0x80b7  ldarg.0
0x80b8  ldarg.0
0x80b9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x80be  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x80c3  ldstr    aFormdata// "formdata"
0x80c8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x80cd  stfld    string Microsoft.Crm.Service.Web.Tools.ServiceManagement.KBContentPage::articleRow
0x80d2  ldarg.0
0x80d3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x80d8  ldstr    aArticlerow// "articleRow"
0x80dd  ldarg.0
0x80de  ldfld    string Microsoft.Crm.Service.Web.Tools.ServiceManagement.KBContentPage::articleRow
0x80e3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x80e8  ldarg.0
0x80e9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x80ee  ldstr    aInvalidJson// "INVALID_JSON"
0x80f3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x80f8  ldstr    aSearchwidgetIn// "SearchWidget.Invalid.JSON"
0x80fd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8102  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8107  ret
```
