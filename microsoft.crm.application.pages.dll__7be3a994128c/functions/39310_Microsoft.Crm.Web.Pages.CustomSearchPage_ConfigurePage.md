# Microsoft.Crm.Web.Pages.CustomSearchPage::ConfigurePage

- ea: `0x39310`
- end: `0x39557`
- name: `Microsoft.Crm.Web.Pages.CustomSearchPage::ConfigurePage`
- size: `583`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x39310`

## string_xrefs

- `0x39316`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0x39336`: `/_static/_common/scripts/InlineEditCommon.js`
- `0x39356`: `/_static/_controls/GlobalQuickCreate/GlobalQuickCreateBehavior.js`
- `0x39376`: `/_static/_common/scripts/MultiEntityQuickFind.js`
- `0x39396`: `/_common/styles/multientityquickfind.css`
- `0x394b6`: `IsReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x39310  ldarg.0
0x39311  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39316  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/jquery_ui_1.8."...
0x3931b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39320  ldarg.0
0x39321  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39326  ldstr    aStaticControls_7// "/_static/_controls/FlyoutDialog/FlyoutD"...
0x3932b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39330  ldarg.0
0x39331  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39336  ldstr    aStaticCommonSc_15// "/_static/_common/scripts/InlineEditComm"...
0x3933b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39340  ldarg.0
0x39341  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39346  ldstr    aStaticControls_8// "/_static/_controls/inlineedit/InlineEdi"...
0x3934b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39350  ldarg.0
0x39351  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39356  ldstr    aStaticControls_9// "/_static/_controls/GlobalQuickCreate/Gl"...
0x3935b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39360  ldarg.0
0x39361  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39366  ldstr    aStaticControls_10// "/_static/_controls/NavBar/NavBar.js"
0x3936b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39370  ldarg.0
0x39371  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39376  ldstr    aStaticCommonSc_16// "/_static/_common/scripts/MultiEntityQui"...
0x3937b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39380  ldarg.0
0x39381  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39386  ldstr    aControlsRefres// "/_controls/refreshform/flyoutdialog.css"...
0x3938b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x39390  ldarg.0
0x39391  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39396  ldstr    aCommonStylesMu// "/_common/styles/multientityquickfind.cs"...
0x3939b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x393a0  ldarg.0
0x393a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x393a6  ldstr    aMultientityqui_0// "/MultiEntityQuickfind/multiEntityQuickF"...
0x393ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x393b0  ldarg.0
0x393b1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x393b6  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.ElasticSearchIndexUtility::IsElasticSearchEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x393bb  stfld    bool Microsoft.Crm.Web.Pages.CustomSearchPage::IsExternalSearchEnabled
0x393c0  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.SearchUtility::GetSearchInfo()
0x393c5  stloc.0
0x393c6  ldarg.0
0x393c7  ldloc.0
0x393c8  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations::get_SearchProviderName()
0x393cd  stfld    string Microsoft.Crm.Web.Pages.CustomSearchPage::SearchProviderName
0x393d2  ldarg.0
0x393d3  ldloc.0
0x393d4  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations::get_IsSearchBoxVisible()
0x393d9  stfld    bool Microsoft.Crm.Web.Pages.CustomSearchPage::IsSearchBoxVisible
0x393de  ldarg.0
0x393df  ldloc.0
0x393e0  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations::get_SearchProviderResultsPage()
0x393e5  stfld    string Microsoft.Crm.Web.Pages.CustomSearchPage::CustomSearchIFrameUrlRaw
0x393ea  ldc.i4.5
0x393eb  newarr   [mscorlib]System.Object
0x393f0  dup
0x393f1  ldc.i4.0
0x393f2  ldarg.0
0x393f3  ldfld    string Microsoft.Crm.Web.Pages.CustomSearchPage::CustomSearchIFrameUrlRaw
0x393f8  stelem.ref
0x393f9  dup
0x393fa  ldc.i4.1
0x393fb  ldstr    aData_0// " ?data="
0x39400  stelem.ref
0x39401  dup
0x39402  ldc.i4.2
0x39403  ldarg.0
0x39404  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x39409  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3940e  ldstr    aText_0// "text"
0x39413  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x39418  callvirt instance string [mscorlib]System.Object::ToString()
0x3941d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x39422  stelem.ref
0x39423  dup
0x39424  ldc.i4.3
0x39425  ldstr    aUserlcid// "&userlcid="
0x3942a  stelem.ref
0x3942b  dup
0x3942c  ldc.i4.4
0x3942d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x39432  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserCulture()
0x39437  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x3943c  box      [mscorlib]System.Int32
0x39441  stelem.ref
0x39442  call     string [mscorlib]System.String::Concat(object[])
0x39447  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string)
0x3944c  stloc.1
0x3944d  ldarg.0
0x3944e  ldloc.1
0x3944f  callvirt instance string [mscorlib]System.Object::ToString()
0x39454  stfld    string Microsoft.Crm.Web.Pages.CustomSearchPage::CustomSearchIFrameUrl
0x39459  ldarg.0
0x3945a  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Web.Pages.CustomSearchPage::useRelevanceSearch
0x3945f  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x39464  ldstr    aTitle// "title"
0x39469  ldarg.0
0x3946a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3946f  ldstr    aExternalsearch_0// "ExternalSearch_Use_Relevance_Search"
0x39474  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x39479  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x3947e  ldarg.0
0x3947f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x39484  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x39489  ldstr    aText_0// "text"
0x3948e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x39493  brtrue.s loc_394AC
0x39495  ldarg.0
0x39496  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3949b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x394a0  ldstr    aOption// "option"
0x394a5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x394aa  brfalse.s loc_394D9
0x394ac  ldtoken  [System]System.Collections.Specialized.NameValueCollection
0x394b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x394b6  ldstr    aIsreadonly// "IsReadOnly"
0x394bb  ldc.i4.s 0x24
0x394bd  call     instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x394c2  ldarg.0
0x394c3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x394c8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x394cd  ldc.i4.0
0x394ce  box      [mscorlib]System.Boolean
0x394d3  ldnull
0x394d4  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object, object[])
0x394d9  ldarg.0
0x394da  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x394df  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x394e4  ldstr    aText_0// "text"
0x394e9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x394ee  brfalse.s loc_3952A
0x394f0  ldarg.0
0x394f1  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.Crm.Web.Pages.CustomSearchPage::searchTextBox
0x394f6  ldarg.0
0x394f7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x394fc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x39501  ldstr    aText_0// "text"
0x39506  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3950b  callvirt instance string [mscorlib]System.Object::ToString()
0x39510  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x39515  ldarg.0
0x39516  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3951b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x39520  ldstr    aText_0// "text"
0x39525  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x3952a  ldarg.0
0x3952b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x39530  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x39535  ldstr    aOption// "option"
0x3953a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3953f  brfalse.s loc_39556
0x39541  ldarg.0
0x39542  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x39547  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3954c  ldstr    aOption// "option"
0x39551  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x39556  ret
```
