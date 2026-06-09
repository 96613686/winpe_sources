# Microsoft.Crm.Web.Tools.BulkDelete.BulkDeleteFailures::ConfigurePage

- ea: `0x8e220`
- end: `0x8e3a2`
- name: `Microsoft.Crm.Web.Tools.BulkDelete.BulkDeleteFailures::ConfigurePage`
- size: `386`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8e220`
- `0x8fd10`
- `0x8fdf0`
- `0x8fe40`
- `0x903a0`
- `0x903c0`

## string_xrefs

- `0x8e226`: `/_static/_common/scripts/stage.js`
- `0x8e251`: `Web.BulkDelete.HomeFailures.aspx_NoGrid`
- `0x8e277`: `bulkdeleteid`
- `0x8e33a`: `bulkdeleteopid`
- `0x8e392`: `BulkDelete_EmptyFailureGrid`

## pseudocode

```c

```

## disassembly

```asm
0x8e220  ldarg.0
0x8e221  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8e226  ldstr    aStaticCommonSc_4// "/_static/_common/scripts/stage.js"
0x8e22b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8e230  ldarg.0
0x8e231  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8e236  ldstr    aStaticFormsAdd// "/_static/_forms/addrelated.js"
0x8e23b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8e240  ldarg.0
0x8e241  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8e246  ldstr    aLocidGridNotFo// "LOCID_GRID_NOT_FOUND"
0x8e24b  ldarg.0
0x8e24c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8e251  ldstr    aWebBulkdeleteH// "Web.BulkDelete.HomeFailures.aspx_NoGrid"
0x8e256  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8e25b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8e260  ldarg.0
0x8e261  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.BulkDelete.BulkDeleteFailures::queryTypeSelector
0x8e266  ldc.i4.1
0x8e267  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8e26c  ldarg.0
0x8e26d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x8e272  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x8e277  ldstr    aBulkdeleteid// "bulkdeleteid"
0x8e27c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8e281  stloc.0
0x8e282  ldloc.0
0x8e283  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x8e288  ldc.i4.0
0x8e289  stloc.1
0x8e28a  call     string[] Microsoft.Crm.Web.Tools.BulkDelete.BulkDeleteHelper::GetOrderedQuerySet(valuetype [mscorlib]System.Guid bulkOperationId)
0x8e28f  stloc.2
0x8e290  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::.ctor()
0x8e295  stloc.3
0x8e296  ldloc.2
0x8e297  brfalse.s loc_8E2FE
0x8e299  ldloc.2
0x8e29a  ldlen
0x8e29b  brfalse.s loc_8E2FE
0x8e29d  ldloc.2
0x8e29e  call     string[] Microsoft.Crm.Web.Tools.BulkDelete.BulkDeleteHelper::GetEntityNamesFromFetchXml(string[] fetchXml)
0x8e2a3  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Web.Tools.BulkDelete.EntityFormattedNames> Microsoft.Crm.Web.Tools.BulkDelete.BulkDeleteHelper::GetDisplayNamesForEntities(string[] entityNames)
0x8e2a8  stloc.s  4
0x8e2aa  ldloc.s  4
0x8e2ac  ldc.i4.0
0x8e2ad  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Web.Tools.BulkDelete.EntityFormattedNames>::get_Item(!!T0)
0x8e2b2  callvirt instance int32 Microsoft.Crm.Web.Tools.BulkDelete.EntityFormattedNames::get_FetchXmlIndex()
0x8e2b7  stloc.1
0x8e2b8  ldc.i4.0
0x8e2b9  stloc.s  5
0x8e2bb  br.s     loc_8E2F3
0x8e2bd  ldloc.3
0x8e2be  ldloc.s  4
0x8e2c0  ldloc.s  5
0x8e2c2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Web.Tools.BulkDelete.EntityFormattedNames>::get_Item(!!T0)
0x8e2c7  callvirt instance string Microsoft.Crm.Web.Tools.BulkDelete.EntityFormattedNames::get_EntityName()
0x8e2cc  ldloc.s  4
0x8e2ce  ldloc.s  5
0x8e2d0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Web.Tools.BulkDelete.EntityFormattedNames>::get_Item(!!T0)
0x8e2d5  callvirt instance int32 Microsoft.Crm.Web.Tools.BulkDelete.EntityFormattedNames::get_FetchXmlIndex()
0x8e2da  stloc.s  6
0x8e2dc  ldloca.s 6
0x8e2de  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e2e3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8e2e8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x8e2ed  ldloc.s  5
0x8e2ef  ldc.i4.1
0x8e2f0  add
0x8e2f1  stloc.s  5
0x8e2f3  ldloc.s  5
0x8e2f5  ldloc.s  4
0x8e2f7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Web.Tools.BulkDelete.EntityFormattedNames>::get_Count()
0x8e2fc  blt.s    loc_8E2BD
0x8e2fe  ldarg.0
0x8e2ff  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.BulkDelete.BulkDeleteFailures::queryTypeSelector
0x8e304  ldloc.3
0x8e305  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddOptionGroup(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup)
0x8e30a  ldloc.3
0x8e30b  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::get_Options()
0x8e310  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x8e315  ldc.i4.1
0x8e316  ble.s    loc_8E324
0x8e318  ldarg.0
0x8e319  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.BulkDelete.BulkDeleteFailures::queryTypeSelector
0x8e31e  ldc.i4.0
0x8e31f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8e324  ldarg.0
0x8e325  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.Tools.BulkDelete.BulkDeleteFailures::crmGrid
0x8e32a  ldstr    a75612f8c0a2e49// "{75612F8C-0A2E-4942-A6D8-1B8D9BCACEF9}"
0x8e32f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewId(string)
0x8e334  ldarg.0
0x8e335  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.Tools.BulkDelete.BulkDeleteFailures::crmGrid
0x8e33a  ldstr    aBulkdeleteopid// "bulkdeleteopid"
0x8e33f  ldloc.0
0x8e340  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x8e345  ldarg.0
0x8e346  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.Tools.BulkDelete.BulkDeleteFailures::crmGrid
0x8e34b  ldstr    aQueryindex// "queryindex"
0x8e350  ldloca.s 1
0x8e352  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e357  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8e35c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x8e361  ldarg.0
0x8e362  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.Tools.BulkDelete.BulkDeleteFailures::crmGrid
0x8e367  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.BulkDeleteFailureGridDataProvider::.ctor()
0x8e36c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_DataProvider(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider)
0x8e371  ldarg.0
0x8e372  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.Tools.BulkDelete.BulkDeleteFailures::crmGrid
0x8e377  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.CustomGridProviderFactory::.ctor()
0x8e37c  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridUIProvider::.ctor(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ICustomGridProviderFactory)
0x8e381  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_UIProvider(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.IGridUIProvider)
0x8e386  ldarg.0
0x8e387  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.Tools.BulkDelete.BulkDeleteFailures::crmGrid
0x8e38c  ldarg.0
0x8e38d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8e392  ldstr    aBulkdeleteEmpt// "BulkDelete_EmptyFailureGrid"
0x8e397  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8e39c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_EmptyGridMessage(string)
0x8e3a1  ret
```
