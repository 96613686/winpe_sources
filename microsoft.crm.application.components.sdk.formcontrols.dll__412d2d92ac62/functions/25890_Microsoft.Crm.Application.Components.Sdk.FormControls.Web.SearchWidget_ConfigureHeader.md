# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::ConfigureHeader

- ea: `0x25890`
- end: `0x25df1`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::ConfigureHeader`
- size: `1377`
- prototype: ``
- caller_count: `0`
- callee_count: `35`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x25890`
- `0x264c0`
- `0x264e0`
- `0x26560`
- `0x266c0`
- `0x266e0`
- `0x26700`
- `0x26870`
- `0x27040`
- `0x27080`
- `0x270a0`
- `0x270c0`
- `0x270e0`
- `0x27100`
- `0x27120`
- `0x27140`
- `0x27160`
- `0x27180`
- `0x271a0`
- `0x271f0`
- `0x27210`
- `0x27240`
- `0x27260`
- `0x27280`
- `0x272a0`
- `0x27510`
- `0x27540`
- `0x27650`
- `0x27710`
- `0x27770`
- `0x27860`
- `0x278c0`
- `0x27900`
- `0x27950`
- `0x27980`

## string_xrefs

- `0x258df`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0x258cf`: `/_static/_common/scripts/SalesCommonFramework.js`
- `0x2596f`: `/_static/_common/scripts/Wall.Interfaces.js`
- `0x2597f`: `/_static/_common/scripts/Wall.Control.js`
- `0x25b81`: `masterComponentId`
- `0x25b66`: `isControlReadOnly`
- `0x2598f`: `/_static/_controls/ActivityContainer/ActivityCommandBar.js`
- `0x2592f`: `/_common/styles/global.css.aspx`
- `0x2593f`: `/_common/styles/appportal.css.aspx`
- `0x2594f`: `/_static/_common/scripts/app_portal_shared.js`
- `0x2595f`: `/_static/_common/scripts/watermarktextbox.js`
- `0x259bf`: `/_static/_controls/SearchWidget/ExternalInteractionService.js`
- `0x25bad`: `publicLinkPrefix`
- `0x25bc3`: `canCreateEmail`
- `0x25bf4`: `externalServiceUrl`
- `0x25c79`: `isKMConfigured`
- `0x25ce9`: `isKMConfigured`
- `0x25d30`: `isParatureConfigured`
- `0x25d66`: `isRelevanceSearchConfiguredForKM`

## pseudocode

```c

```

## disassembly

```asm
0x25890  ldarg.0
0x25891  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x25896  ldarg.0
0x25897  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_IsBulkEditMode()
0x2589c  brfalse.s loc_2589F
0x2589e  ret
0x2589f  ldarg.0
0x258a0  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_IsWorkFlowMode()
0x258a5  brfalse.s loc_258A8
0x258a7  ret
0x258a8  ldarg.0
0x258a9  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x258ae  ldc.i4.1
0x258af  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x258b4  ldarg.0
0x258b5  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x258ba  ldc.i4.1
0x258bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQueryTemplate(bool)
0x258c0  ldarg.0
0x258c1  call     instance valuetype Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidgetContext Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_WidgetContext()
0x258c6  ldc.i4.1
0x258c7  bne.un.s loc_25919
0x258c9  ldarg.0
0x258ca  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x258cf  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/SalesCommonFra"...
0x258d4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x258d9  ldarg.0
0x258da  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x258df  ldstr    aStaticCommonSc// "/_static/_common/scripts/jquery_ui_1.8."...
0x258e4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x258e9  ldarg.0
0x258ea  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x258ef  ldstr    aStaticControls_4// "/_static/_controls/datetime/date.js"
0x258f4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x258f9  ldarg.0
0x258fa  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x258ff  ldstr    aStaticControls_5// "/_static/_controls/datetime/time.js"
0x25904  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x25909  ldarg.0
0x2590a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2590f  ldstr    aStaticControls_2// "/_static/_controls/activitycontainer/ac"...
0x25914  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x25919  ldarg.0
0x2591a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2591f  ldstr    aStaticControls_9// "/_static/_controls/FlyoutDialog/FlyoutD"...
0x25924  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x25929  ldarg.0
0x2592a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2592f  ldstr    aCommonStylesGl// "/_common/styles/global.css.aspx"
0x25934  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x25939  ldarg.0
0x2593a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2593f  ldstr    aCommonStylesAp// "/_common/styles/appportal.css.aspx"
0x25944  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x25949  ldarg.0
0x2594a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2594f  ldstr    aStaticCommonSc_13// "/_static/_common/scripts/app_portal_sha"...
0x25954  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x25959  ldarg.0
0x2595a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2595f  ldstr    aStaticCommonSc_14// "/_static/_common/scripts/watermarktextb"...
0x25964  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x25969  ldarg.0
0x2596a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2596f  ldstr    aStaticCommonSc_4// "/_static/_common/scripts/Wall.Interface"...
0x25974  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x25979  ldarg.0
0x2597a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2597f  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/Wall.Control.j"...
0x25984  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x25989  ldarg.0
0x2598a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2598f  ldstr    aStaticControls_1// "/_static/_controls/ActivityContainer/Ac"...
0x25994  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x25999  ldarg.0
0x2599a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2599f  ldstr    aSearchwidgetSe// "/SearchWidget/SearchWidget.css.aspx"
0x259a4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x259a9  ldarg.0
0x259aa  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x259af  ldstr    aStaticControls_20// "/_static/_controls/SearchWidget/SearchW"...
0x259b4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x259b9  ldarg.0
0x259ba  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x259bf  ldstr    aStaticControls_21// "/_static/_controls/SearchWidget/Externa"...
0x259c4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x259c9  ldarg.0
0x259ca  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x259cf  ldstr    aSearchwidgetwa// "searchWidgetWallStrings"
0x259d4  ldarg.0
0x259d5  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::GenerateClientStrings()
0x259da  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>)
0x259df  ldarg.0
0x259e0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x259e5  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x259ea  ldstr    aSearchwidgetSe_0// "/SearchWidget/SearchWidgetWallContent.a"...
0x259ef  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x259f4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x259f9  stloc.0
0x259fa  ldloc.0
0x259fb  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x25a00  ldstr    aHc// "hc"
0x25a05  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x25a0a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UseImageStrips()
0x25a0f  brfalse.s loc_25A18
0x25a11  ldstr    a0// "0"
0x25a16  br.s     loc_25A1D
0x25a18  ldstr    a1_0// "1"
0x25a1d  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x25a22  ldloc.0
0x25a23  ldc.i4.1
0x25a24  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_UseVersionStamp(bool)
0x25a29  ldarg.0
0x25a2a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25a2f  ldstr    aWallcontentpag// "wallContentPageUrl"
0x25a34  ldloc.0
0x25a35  callvirt instance string [mscorlib]System.Object::ToString()
0x25a3a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25a3f  ldarg.0
0x25a40  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25a45  ldstr    aShowlanguagefi// "showLanguageFilter"
0x25a4a  ldarg.0
0x25a4b  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_ShowLanguageFilter()
0x25a50  box      [mscorlib]System.Boolean
0x25a55  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25a5a  ldarg.0
0x25a5b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25a60  ldstr    aShowdepartment// "showDepartmentFilter"
0x25a65  ldc.i4.0
0x25a66  box      [mscorlib]System.Boolean
0x25a6b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25a70  ldarg.0
0x25a71  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25a76  ldstr    aNumberofresult// "numberOfResults"
0x25a7b  ldarg.0
0x25a7c  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_NumberOfResults()
0x25a81  box      [mscorlib]System.Int32
0x25a86  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25a8b  ldarg.0
0x25a8c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25a91  ldstr    aFilterresults// "filterResults"
0x25a96  ldarg.0
0x25a97  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_FilterResults()
0x25a9c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25aa1  ldarg.0
0x25aa2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25aa7  ldstr    aEnableautosugg// "enableAutoSuggestions"
0x25aac  ldarg.0
0x25aad  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_EnableAutoSuggestions()
0x25ab2  box      [mscorlib]System.Boolean
0x25ab7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25abc  ldarg.0
0x25abd  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25ac2  ldstr    aSearchforautos// "searchForAutoSuggestionsUsing"
0x25ac7  ldarg.0
0x25ac8  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_SearchForAutoSuggestionsUsing()
0x25acd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25ad2  ldarg.0
0x25ad3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25ad8  ldstr    aAutosuggestion// "autoSuggestionSource"
0x25add  ldarg.0
0x25ade  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_AutoSuggestionSource()
0x25ae3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25ae8  ldarg.0
0x25ae9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25aee  ldstr    aSelectprimaryc// "selectPrimaryCustomer"
0x25af3  ldarg.0
0x25af4  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_SelectPrimaryCustomer()
0x25af9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25afe  ldarg.0
0x25aff  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25b04  ldstr    aAllowchangingf// "allowChangingFiltersOnUI"
0x25b09  ldarg.0
0x25b0a  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_AllowChangingFiltersOnUI()
0x25b0f  box      [mscorlib]System.Boolean
0x25b14  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25b19  ldarg.0
0x25b1a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25b1f  ldstr    aSelectdefaultl// "selectDefaultLanguage"
0x25b24  ldarg.0
0x25b25  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_SelectDefaultLanguage()
0x25b2a  box      [mscorlib]System.Guid
0x25b2f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25b34  ldarg.0
0x25b35  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25b3a  ldstr    aShowcontextual// "showContextualActions"
0x25b3f  ldarg.0
0x25b40  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_ShowContextualActions()
0x25b45  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25b4a  ldarg.0
0x25b4b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25b50  ldstr    aActionlist// "actionList"
0x25b55  ldarg.0
0x25b56  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_ActionList()
0x25b5b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25b60  ldarg.0
0x25b61  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25b66  ldstr    aIscontrolreado// "isControlReadOnly"
0x25b6b  ldarg.0
0x25b6c  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_IsControlReadOnly()
0x25b71  box      [mscorlib]System.Boolean
0x25b76  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25b7b  ldarg.0
0x25b7c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25b81  ldstr    aMastercomponen// "masterComponentId"
0x25b86  ldarg.0
0x25b87  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_MasterComponentId()
0x25b8c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25b91  ldarg.0
0x25b92  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25b97  ldstr    aPortaldomain// "portalDomain"
0x25b9c  ldarg.0
0x25b9d  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::GetPortalDomain()
0x25ba2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25ba7  ldarg.0
0x25ba8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25bad  ldstr    aPubliclinkpref// "publicLinkPrefix"
0x25bb2  ldarg.0
0x25bb3  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::GetPublicLinkPrefix()
0x25bb8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25bbd  ldarg.0
0x25bbe  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25bc3  ldstr    aCancreateemail// "canCreateEmail"
0x25bc8  ldarg.0
0x25bc9  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::CanCreateEmail()
0x25bce  box      [mscorlib]System.Boolean
0x25bd3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25bd8  ldarg.0
0x25bd9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25bde  ldstr    aDepartmentid// "departmentId"
0x25be3  ldarg.0
0x25be4  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::GetDepartmentId()
0x25be9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25bee  ldarg.0
0x25bef  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25bf4  ldstr    aExternalservic// "externalServiceUrl"
0x25bf9  ldarg.0
0x25bfa  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_ExternalServiceUrl()
0x25bff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25c04  ldarg.0
0x25c05  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25c0a  ldstr    aIshostedintabb// "isHostedInTabbedControl"
0x25c0f  ldarg.0
0x25c10  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_IsHostedInTabbedControl()
0x25c15  box      [mscorlib]System.Boolean
0x25c1a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25c1f  ldarg.0
0x25c20  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25c25  ldstr    aShowratingusin// "showRatingUsing"
0x25c2a  ldarg.0
0x25c2b  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_ShowRatingUsing()
0x25c30  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25c35  ldarg.0
0x25c36  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25c3b  ldstr    aEnablerating// "enableRating"
0x25c40  ldarg.0
0x25c41  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_EnableRating()
0x25c46  box      [mscorlib]System.Boolean
0x25c4b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25c50  ldarg.0
0x25c51  call     instance valuetype Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidgetContext Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_WidgetContext()
0x25c56  brtrue.s loc_25CCD
0x25c58  ldarg.0
0x25c59  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25c5e  ldstr    aIskmenabled// "isKMEnabled"
0x25c63  ldarg.0
0x25c64  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_IsKnowledgeMangementEnabled()
0x25c69  box      [mscorlib]System.Boolean
0x25c6e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25c73  ldarg.0
0x25c74  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25c79  ldstr    aIskmconfigured// "isKMConfigured"
0x25c7e  ldarg.0
0x25c7f  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_IsKnowledgeMangementParatureConfigured()
0x25c84  brtrue.s loc_25C8E
0x25c86  ldarg.0
0x25c87  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_IsKnowledgeManagementNativeCrmConfigured()
0x25c8c  br.s     loc_25C8F
0x25c8e  ldc.i4.1
0x25c8f  box      [mscorlib]System.Boolean
0x25c94  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25c99  ldarg.0
0x25c9a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25c9f  ldstr    aBlockresult// "blockResult"
0x25ca4  ldc.i4.0
0x25ca5  box      [mscorlib]System.Boolean
0x25caa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25caf  ldarg.0
0x25cb0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25cb5  ldstr    aIsusdcontext// "isUsdContext"
0x25cba  ldc.i4.0
0x25cbb  box      [mscorlib]System.Boolean
0x25cc0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x25cc5  ldarg.0
0x25cc6  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::PopulateRelationShipNameAndIntersectTable()
0x25ccb  br.s     loc_25D2A
0x25ccd  ldarg.0
0x25cce  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x25cd3  ldstr    aIskmenabled// "isKMEnabled"
0x25cd8  ldc.i4.1
  ... truncated ...
```
