# Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::InitializeAppPageHeader

- ea: `0xe3940`
- end: `0xe3a53`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::InitializeAppPageHeader`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe4430`

## callees

- `0xe3940`
- `0xe3a60`
- `0xe4000`
- `0xe42e0`
- `0xea130`
- `0xea180`
- `0xea260`

## string_xrefs

- `0xe3a41`: `_BusinessRuleEditorJsonData`
- `0xe39a1`: `/_forms/styles/read.css.aspx`
- `0xe3991`: `BusinessRulesWebService`
- `0xe3a1f`: `_BusinessRuleJsonData`

## pseudocode

```c

```

## disassembly

```asm
0xe3940  ldarg.0
0xe3941  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3946  brtrue.s loc_E3953
0xe3948  ldstr    aExpectedManage// "Expected ManageBusinessRuleView.AppPage"...
0xe394d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0xe3952  throw
0xe3953  ldarg.0
0xe3954  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3959  ldc.i4.1
0xe395a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0xe395f  ldarg.0
0xe3960  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3965  ldarg.0
0xe3966  ldfld    class Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.IManageBusinessRuleViewModel Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::_viewModel
0xe396b  callvirt instance class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.IManageRuleCommonViewModel::get_RequiredScriptReferencesQueue()
0xe3970  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header::AppendScriptReferences(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0xe3975  ldarg.0
0xe3976  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe397b  ldarg.0
0xe397c  ldfld    class Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.IManageBusinessRuleViewModel Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::_viewModel
0xe3981  callvirt instance class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.IManageBusinessRuleViewModel::get_OnLoadScriptBlocksQueue()
0xe3986  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header::InsertOnLoadScriptBlocks(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock>)
0xe398b  ldarg.0
0xe398c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3991  ldstr    aBusinessrulesw// "BusinessRulesWebService"
0xe3996  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xe399b  ldarg.0
0xe399c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe39a1  ldstr    aFormsStylesRea// "/_forms/styles/read.css.aspx"
0xe39a6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe39ab  ldarg.0
0xe39ac  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe39b1  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0xe39b6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe39bb  ldarg.0
0xe39bc  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe39c1  ldstr    aNavMenuCssAspx// "/_nav/menu.css.aspx"
0xe39c6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe39cb  ldarg.0
0xe39cc  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe39d1  ldstr    aControlsRefres// "/_controls/refreshform/flyoutdialog.css"...
0xe39d6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe39db  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xe39e0  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xe39e5  stloc.3
0xe39e6  ldloca.s 3
0xe39e8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe39ed  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xe39f2  stloc.0
0xe39f3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe39f8  ldstr    aStaticCss0Busi// "/_static/css/{0}/BusinessRules.css"
0xe39fd  ldc.i4.1
0xe39fe  newarr   [mscorlib]System.Object
0xe3a03  dup
0xe3a04  ldc.i4.0
0xe3a05  ldloc.0
0xe3a06  stelem.ref
0xe3a07  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe3a0c  stloc.1
0xe3a0d  ldarg.0
0xe3a0e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3a13  ldloc.1
0xe3a14  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe3a19  ldarg.0
0xe3a1a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3a1f  ldstr    aBusinessrulejs// "_BusinessRuleJsonData"
0xe3a24  ldarg.0
0xe3a25  ldfld    class Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.IManageBusinessRuleViewModel Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::_viewModel
0xe3a2a  callvirt instance string Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.IManageBusinessRuleViewModel::get_Json()
0xe3a2f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xe3a34  ldarg.0
0xe3a35  callvirt instance string Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::BuildEditorClientData()
0xe3a3a  stloc.2
0xe3a3b  ldarg.0
0xe3a3c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3a41  ldstr    aBusinessruleed// "_BusinessRuleEditorJsonData"
0xe3a46  ldloc.2
0xe3a47  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xe3a4c  ldarg.0
0xe3a4d  callvirt instance void Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::SetResourceVars()
0xe3a52  ret
```
