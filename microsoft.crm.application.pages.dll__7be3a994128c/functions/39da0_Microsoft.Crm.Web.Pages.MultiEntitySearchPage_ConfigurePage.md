# Microsoft.Crm.Web.Pages.MultiEntitySearchPage::ConfigurePage

- ea: `0x39da0`
- end: `0x3a000`
- name: `Microsoft.Crm.Web.Pages.MultiEntitySearchPage::ConfigurePage`
- size: `608`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x39da0`
- `0x3a2a0`

## string_xrefs

- `0x39da6`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0x39dc6`: `/_static/_common/scripts/InlineEditCommon.js`
- `0x39de6`: `/_static/_controls/GlobalQuickCreate/GlobalQuickCreateBehavior.js`
- `0x39e06`: `/_static/_common/scripts/MultiEntityQuickFind.js`
- `0x39e26`: `/_common/styles/multientityquickfind.css`
- `0x39f3a`: `IsReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x39da0  ldarg.0
0x39da1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39da6  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/jquery_ui_1.8."...
0x39dab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39db0  ldarg.0
0x39db1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39db6  ldstr    aStaticControls_7// "/_static/_controls/FlyoutDialog/FlyoutD"...
0x39dbb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39dc0  ldarg.0
0x39dc1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39dc6  ldstr    aStaticCommonSc_15// "/_static/_common/scripts/InlineEditComm"...
0x39dcb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39dd0  ldarg.0
0x39dd1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39dd6  ldstr    aStaticControls_8// "/_static/_controls/inlineedit/InlineEdi"...
0x39ddb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39de0  ldarg.0
0x39de1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39de6  ldstr    aStaticControls_9// "/_static/_controls/GlobalQuickCreate/Gl"...
0x39deb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39df0  ldarg.0
0x39df1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39df6  ldstr    aStaticControls_10// "/_static/_controls/NavBar/NavBar.js"
0x39dfb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39e00  ldarg.0
0x39e01  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39e06  ldstr    aStaticCommonSc_16// "/_static/_common/scripts/MultiEntityQui"...
0x39e0b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x39e10  ldarg.0
0x39e11  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39e16  ldstr    aControlsRefres// "/_controls/refreshform/flyoutdialog.css"...
0x39e1b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x39e20  ldarg.0
0x39e21  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39e26  ldstr    aCommonStylesMu// "/_common/styles/multientityquickfind.cs"...
0x39e2b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x39e30  ldarg.0
0x39e31  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x39e36  ldstr    aMultientityqui_0// "/MultiEntityQuickfind/multiEntityQuickF"...
0x39e3b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x39e40  ldarg.0
0x39e41  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x39e46  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.ElasticSearchIndexUtility::IsElasticSearchEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x39e4b  stfld    bool Microsoft.Crm.Web.Pages.MultiEntitySearchPage::IsExternalSearchEnabled
0x39e50  ldarg.0
0x39e51  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.SearchUtility::GetSearchInfo()
0x39e56  brtrue.s loc_39E5B
0x39e58  ldc.i4.0
0x39e59  br.s     loc_39E65
0x39e5b  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.SearchUtility::GetSearchInfo()
0x39e60  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations::get_IsEnabled()
0x39e65  stfld    bool Microsoft.Crm.Web.Pages.MultiEntitySearchPage::IsCustomSearchEnabled
0x39e6a  ldarg.0
0x39e6b  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.SearchUtility::GetSearchInfo()
0x39e70  brtrue.s loc_39E79
0x39e72  ldstr    asc_11EF2A// ""
0x39e77  br.s     loc_39E83
0x39e79  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.SearchUtility::GetSearchInfo()
0x39e7e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations::get_SearchProviderName()
0x39e83  stfld    string Microsoft.Crm.Web.Pages.MultiEntitySearchPage::SearchProviderName
0x39e88  ldarg.0
0x39e89  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x39e8e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x39e93  stfld    bool Microsoft.Crm.Web.Pages.MultiEntitySearchPage::IsWebClientVisualRefreshFeatureAvailable
0x39e98  ldarg.0
0x39e99  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Web.Pages.MultiEntitySearchPage::meqfStartLabel
0x39e9e  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x39ea3  ldstr    aTitle// "title"
0x39ea8  ldarg.0
0x39ea9  ldfld    bool Microsoft.Crm.Web.Pages.MultiEntitySearchPage::IsExternalSearchEnabled
0x39eae  brtrue.s loc_39EC2
0x39eb0  ldarg.0
0x39eb1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x39eb6  ldstr    aSearchLabelMeq// "Search_Label_Meqf"
0x39ebb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x39ec0  br.s     loc_39ED2
0x39ec2  ldarg.0
0x39ec3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x39ec8  ldstr    aCategorizedsea// "CategorizedSearch_Label_Tooltip"
0x39ecd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x39ed2  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x39ed7  ldarg.0
0x39ed8  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Web.Pages.MultiEntitySearchPage::useRelevanceSearch
0x39edd  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x39ee2  ldstr    aTitle// "title"
0x39ee7  ldarg.0
0x39ee8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x39eed  ldstr    aExternalsearch_0// "ExternalSearch_Use_Relevance_Search"
0x39ef2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x39ef7  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x39efc  ldarg.0
0x39efd  call     instance void Microsoft.Crm.Web.Pages.MultiEntitySearchPage::PopulateEntityNames()
0x39f02  ldarg.0
0x39f03  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x39f08  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x39f0d  ldstr    aText_0// "text"
0x39f12  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x39f17  brtrue.s loc_39F30
0x39f19  ldarg.0
0x39f1a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x39f1f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x39f24  ldstr    aOption// "option"
0x39f29  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x39f2e  brfalse.s loc_39F5D
0x39f30  ldtoken  [System]System.Collections.Specialized.NameValueCollection
0x39f35  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x39f3a  ldstr    aIsreadonly// "IsReadOnly"
0x39f3f  ldc.i4.s 0x24
0x39f41  call     instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x39f46  ldarg.0
0x39f47  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x39f4c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x39f51  ldc.i4.0
0x39f52  box      [mscorlib]System.Boolean
0x39f57  ldnull
0x39f58  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object, object[])
0x39f5d  ldarg.0
0x39f5e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x39f63  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x39f68  ldstr    aText_0// "text"
0x39f6d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x39f72  brfalse.s loc_39FAE
0x39f74  ldarg.0
0x39f75  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.Crm.Web.Pages.MultiEntitySearchPage::searchTextBox
0x39f7a  ldarg.0
0x39f7b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x39f80  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x39f85  ldstr    aText_0// "text"
0x39f8a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x39f8f  callvirt instance string [mscorlib]System.Object::ToString()
0x39f94  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x39f99  ldarg.0
0x39f9a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x39f9f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x39fa4  ldstr    aText_0// "text"
0x39fa9  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x39fae  ldarg.0
0x39faf  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x39fb4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x39fb9  ldstr    aOption// "option"
0x39fbe  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x39fc3  brfalse.s loc_39FFF
0x39fc5  ldarg.0
0x39fc6  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Pages.MultiEntitySearchPage::filterCombo
0x39fcb  ldarg.0
0x39fcc  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x39fd1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x39fd6  ldstr    aOption// "option"
0x39fdb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x39fe0  callvirt instance string [mscorlib]System.Object::ToString()
0x39fe5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x39fea  ldarg.0
0x39feb  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x39ff0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x39ff5  ldstr    aOption// "option"
0x39ffa  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x39fff  ret
```
