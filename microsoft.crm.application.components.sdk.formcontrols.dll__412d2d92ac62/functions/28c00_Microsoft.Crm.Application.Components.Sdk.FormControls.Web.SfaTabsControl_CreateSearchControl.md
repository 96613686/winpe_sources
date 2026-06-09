# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateSearchControl

- ea: `0x28c00`
- end: `0x28d4e`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateSearchControl`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `42`
- tags: `broker_com_uri`

## callers

- `0x28820`

## callees

- `0x25850`
- `0x266d0`
- `0x266f0`
- `0x27050`
- `0x27070`
- `0x27090`
- `0x270b0`
- `0x270d0`
- `0x270f0`
- `0x27110`
- `0x27130`
- `0x27150`
- `0x27170`
- `0x27190`
- `0x271b0`
- `0x27250`
- `0x27270`
- `0x27290`
- `0x28640`
- `0x28800`
- `0x28c00`
- `0x29e70`
- `0x29e90`
- `0x29eb0`
- `0x29ed0`
- `0x29f00`
- `0x29f60`
- `0x29f90`
- `0x29fb0`
- `0x29fd0`
- `0x29ff0`
- `0x2a010`
- `0x2a030`
- `0x2a050`
- `0x2a070`
- `0x2a090`
- `0x2a0b0`
- `0x2a0d0`
- `0x2a0f0`
- `0x2a110`
- `0x2a130`
- `0x2a150`

## pseudocode

```c

```

## disassembly

```asm
0x28c00  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x28c05  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsKnowledgebaseFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x28c0a  brfalse  loc_28D4D
0x28c0f  ldarg.0
0x28c10  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_ShowArticleTab()
0x28c15  brfalse  loc_28D4D
0x28c1a  ldarg.0
0x28c1b  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_IsRefreshForm()
0x28c20  brfalse  loc_28D4D
0x28c25  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::.ctor()
0x28c2a  dup
0x28c2b  ldstr    aSearchwidgetco// "searchwidgetcontrol_"
0x28c30  ldarg.0
0x28c31  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x28c36  call     string [mscorlib]System.String::Concat(string, string)
0x28c3b  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x28c40  dup
0x28c41  ldarg.0
0x28c42  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_IsControlReadOnly()
0x28c47  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_IsControlReadOnly(bool value)
0x28c4c  dup
0x28c4d  ldarg.0
0x28c4e  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x28c53  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_MasterComponentId(string value)
0x28c58  dup
0x28c59  ldarg.0
0x28c5a  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_EnableAutoSuggestions()
0x28c5f  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_EnableAutoSuggestions(bool value)
0x28c64  dup
0x28c65  ldarg.0
0x28c66  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_SearchForAutoSuggestionsUsing()
0x28c6b  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_SearchForAutoSuggestionsUsing(string value)
0x28c70  dup
0x28c71  ldarg.0
0x28c72  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_AutoSuggestionSource()
0x28c77  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_AutoSuggestionSource(string value)
0x28c7c  dup
0x28c7d  ldarg.0
0x28c7e  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_ShowLanguageFilter()
0x28c83  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_ShowLanguageFilter(bool value)
0x28c88  dup
0x28c89  ldarg.0
0x28c8a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_SelectDefaultLanguage()
0x28c8f  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_SelectDefaultLanguage(valuetype [mscorlib]System.Guid value)
0x28c94  dup
0x28c95  ldarg.0
0x28c96  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_ShowDepartmentFilter()
0x28c9b  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_ShowDepartmentFilter(bool value)
0x28ca0  dup
0x28ca1  ldarg.0
0x28ca2  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_NumberOfResults()
0x28ca7  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_NumberOfResults(int32 value)
0x28cac  dup
0x28cad  ldarg.0
0x28cae  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_FilterResults()
0x28cb3  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_FilterResults(string value)
0x28cb8  dup
0x28cb9  ldarg.0
0x28cba  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_AllowChangingFiltersOnUI()
0x28cbf  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_AllowChangingFiltersOnUI(bool value)
0x28cc4  dup
0x28cc5  ldarg.0
0x28cc6  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_SelectPrimaryCustomer()
0x28ccb  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_SelectPrimaryCustomer(string value)
0x28cd0  dup
0x28cd1  ldarg.0
0x28cd2  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_ShowContextualActions()
0x28cd7  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_ShowContextualActions(string value)
0x28cdc  dup
0x28cdd  ldarg.0
0x28cde  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_ActionList()
0x28ce3  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_ActionList(string value)
0x28ce8  dup
0x28ce9  ldc.i4.1
0x28cea  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_IsHostedInTabbedControl(bool value)
0x28cef  dup
0x28cf0  ldarg.0
0x28cf1  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_ShowRatingUsing()
0x28cf6  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_ShowRatingUsing(string value)
0x28cfb  dup
0x28cfc  ldarg.0
0x28cfd  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_EnableRating()
0x28d02  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_EnableRating(bool value)
0x28d07  stloc.0
0x28d08  ldarg.0
0x28d09  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_Items()
0x28d0e  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::.ctor()
0x28d13  dup
0x28d14  ldstr    aArticlestab// "ArticlesTab"
0x28d19  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_TabId(string value)
0x28d1e  dup
0x28d1f  ldloc.0
0x28d20  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_Control(class [System.Web]System.Web.UI.Control value)
0x28d25  dup
0x28d26  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x28d2b  ldstr    aSfatabscontrol// "SFATabsControl.KnowledgeBaseRecord"
0x28d30  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x28d35  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_TabName(string value)
0x28d3a  dup
0x28d3b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x28d40  ldc.i4.0
0x28d41  ceq
0x28d43  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_Hidden(bool value)
0x28d48  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer>::Add(var<u1>)
0x28d4d  ret
```
