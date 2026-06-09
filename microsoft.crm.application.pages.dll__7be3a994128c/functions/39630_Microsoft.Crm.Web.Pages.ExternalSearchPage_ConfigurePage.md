# Microsoft.Crm.Web.Pages.ExternalSearchPage::ConfigurePage

- ea: `0x39630`
- end: `0x3981f`
- name: `Microsoft.Crm.Web.Pages.ExternalSearchPage::ConfigurePage`
- size: `495`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x39630`
- `0x39ac0`

## string_xrefs

- `0x39636`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0x39646`: `/_static/_common/scripts/InlineEditCommon.js`
- `0x39666`: `/_static/_controls/GlobalQuickCreate/GlobalQuickCreateBehavior.js`
- `0x39776`: `IsReadOnly`
- `0x39686`: `/_static/_common/scripts/ExternalSearch.js`
- `0x39696`: `/_common/styles/externalsearch.css`
- `0x396b6`: `/_common/styles/jqueryui.css`
- `0x396c6`: `/_common/styles/search.css`
- `0x396d6`: `/_common/styles/bootstrap.css`
- `0x396e6`: `/_common/styles/bootstrap.rtl.min.css`
- `0x396f6`: `/_static/_common/scripts/barchartlib.js`

## pseudocode

```c

```

## disassembly

```asm
0x39630  ldarg.0
0x39631  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39636  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/jquery_ui_1.8."...
0x3963b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39640  ldarg.0
0x39641  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39646  ldstr    aStaticCommonSc_15// "/_static/_common/scripts/InlineEditComm"...
0x3964b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39650  ldarg.0
0x39651  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39656  ldstr    aStaticControls_8// "/_static/_controls/inlineedit/InlineEdi"...
0x3965b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39660  ldarg.0
0x39661  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39666  ldstr    aStaticControls_9// "/_static/_controls/GlobalQuickCreate/Gl"...
0x3966b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39670  ldarg.0
0x39671  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39676  ldstr    aStaticControls_10// "/_static/_controls/NavBar/NavBar.js"
0x3967b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39680  ldarg.0
0x39681  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39686  ldstr    aStaticCommonSc_17// "/_static/_common/scripts/ExternalSearch"...
0x3968b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39690  ldarg.0
0x39691  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39696  ldstr    aCommonStylesEx// "/_common/styles/externalsearch.css"
0x3969b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x396a0  ldarg.0
0x396a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x396a6  ldstr    aExternalsearch_1// "/ExternalSearch/externalsearch.css.aspx"
0x396ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x396b0  ldarg.0
0x396b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x396b6  ldstr    aCommonStylesJq// "/_common/styles/jqueryui.css"
0x396bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x396c0  ldarg.0
0x396c1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x396c6  ldstr    aCommonStylesSe_0// "/_common/styles/search.css"
0x396cb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x396d0  ldarg.0
0x396d1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x396d6  ldstr    aCommonStylesBo// "/_common/styles/bootstrap.css"
0x396db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x396e0  ldarg.0
0x396e1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x396e6  ldstr    aCommonStylesBo_0// "/_common/styles/bootstrap.rtl.min.css"
0x396eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x396f0  ldarg.0
0x396f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x396f6  ldstr    aStaticCommonSc_18// "/_static/_common/scripts/barchartlib.js"
0x396fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39700  ldarg.0
0x39701  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.SearchUtility::GetSearchInfo()
0x39706  brtrue.s loc_3970B
0x39708  ldc.i4.0
0x39709  br.s     loc_39715
0x3970b  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.SearchUtility::GetSearchInfo()
0x39710  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations::get_IsEnabled()
0x39715  stfld    bool Microsoft.Crm.Web.Pages.ExternalSearchPage::IsCustomSearchEnabled
0x3971a  ldarg.0
0x3971b  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.SearchUtility::GetSearchInfo()
0x39720  brtrue.s loc_39729
0x39722  ldstr    asc_11EF2A// ""
0x39727  br.s     loc_39733
0x39729  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.SearchUtility::GetSearchInfo()
0x3972e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations::get_SearchProviderName()
0x39733  stfld    string Microsoft.Crm.Web.Pages.ExternalSearchPage::SearchProviderName
0x39738  ldarg.0
0x39739  call     instance void Microsoft.Crm.Web.Pages.ExternalSearchPage::PopulateSearchNames()
0x3973e  ldarg.0
0x3973f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x39744  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x39749  ldstr    aText_0// "text"
0x3974e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x39753  brtrue.s loc_3976C
0x39755  ldarg.0
0x39756  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3975b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x39760  ldstr    aOption// "option"
0x39765  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3976a  brfalse.s loc_39799
0x3976c  ldtoken  [System]System.Collections.Specialized.NameValueCollection
0x39771  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x39776  ldstr    aIsreadonly// "IsReadOnly"
0x3977b  ldc.i4.s 0x24
0x3977d  call     instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x39782  ldarg.0
0x39783  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x39788  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3978d  ldc.i4.0
0x3978e  box      [mscorlib]System.Boolean
0x39793  ldnull
0x39794  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object, object[])
0x39799  ldarg.0
0x3979a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3979f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x397a4  ldstr    aText_0// "text"
0x397a9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x397ae  brfalse.s loc_397EA
0x397b0  ldarg.0
0x397b1  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.Crm.Web.Pages.ExternalSearchPage::searchTextBox
0x397b6  ldarg.0
0x397b7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x397bc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x397c1  ldstr    aText_0// "text"
0x397c6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x397cb  callvirt instance string [mscorlib]System.Object::ToString()
0x397d0  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x397d5  ldarg.0
0x397d6  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x397db  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x397e0  ldstr    aText_0// "text"
0x397e5  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x397ea  ldarg.0
0x397eb  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x397f0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x397f5  ldstr    aOption// "option"
0x397fa  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x397ff  brfalse.s loc_39816
0x39801  ldarg.0
0x39802  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x39807  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3980c  ldstr    aOption// "option"
0x39811  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x39816  ldarg.0
0x39817  ldc.i4.s 0x14
0x39819  stfld    int32 Microsoft.Crm.Web.Pages.ExternalSearchPage::pageSize
0x3981e  ret
```
