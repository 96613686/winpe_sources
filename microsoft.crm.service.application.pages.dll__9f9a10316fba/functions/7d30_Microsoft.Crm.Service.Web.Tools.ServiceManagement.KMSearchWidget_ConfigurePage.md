# Microsoft.Crm.Service.Web.Tools.ServiceManagement.KMSearchWidget::ConfigurePage

- ea: `0x7d30`
- end: `0x7da3`
- name: `Microsoft.Crm.Service.Web.Tools.ServiceManagement.KMSearchWidget::ConfigurePage`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7df0`
- `0x7e30`
- `0x7e90`
- `0x7ed0`
- `0x7f10`
- `0x7f50`

## pseudocode

```c

```

## disassembly

```asm
0x7d30  ldarg.0
0x7d31  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget Microsoft.Crm.Service.Web.Tools.ServiceManagement.KMSearchWidget::searchWidget
0x7d36  ldc.i4.1
0x7d37  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_WidgetContext(valuetype [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidgetContext)
0x7d3c  ldarg.0
0x7d3d  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget Microsoft.Crm.Service.Web.Tools.ServiceManagement.KMSearchWidget::searchWidget
0x7d42  ldarg.0
0x7d43  call     instance bool Microsoft.Crm.Service.Web.Tools.ServiceManagement.KMSearchWidget::AllowChangingFiltersOnUI()
0x7d48  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_AllowChangingFiltersOnUI(bool)
0x7d4d  ldarg.0
0x7d4e  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget Microsoft.Crm.Service.Web.Tools.ServiceManagement.KMSearchWidget::searchWidget
0x7d53  ldarg.0
0x7d54  call     instance bool Microsoft.Crm.Service.Web.Tools.ServiceManagement.KMSearchWidget::ShowLanguageFilter()
0x7d59  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_ShowLanguageFilter(bool)
0x7d5e  ldarg.0
0x7d5f  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget Microsoft.Crm.Service.Web.Tools.ServiceManagement.KMSearchWidget::searchWidget
0x7d64  ldarg.0
0x7d65  call     instance bool Microsoft.Crm.Service.Web.Tools.ServiceManagement.KMSearchWidget::ShowDepartmentFilter()
0x7d6a  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_ShowDepartmentFilter(bool)
0x7d6f  ldarg.0
0x7d70  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget Microsoft.Crm.Service.Web.Tools.ServiceManagement.KMSearchWidget::searchWidget
0x7d75  ldarg.0
0x7d76  call     instance int32 Microsoft.Crm.Service.Web.Tools.ServiceManagement.KMSearchWidget::GetNumberOfResults()
0x7d7b  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_NumberOfResults(int32)
0x7d80  ldarg.0
0x7d81  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget Microsoft.Crm.Service.Web.Tools.ServiceManagement.KMSearchWidget::searchWidget
0x7d86  ldarg.0
0x7d87  call     instance bool Microsoft.Crm.Service.Web.Tools.ServiceManagement.KMSearchWidget::BlockResultClick()
0x7d8c  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_BlockResult(bool)
0x7d91  ldarg.0
0x7d92  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget Microsoft.Crm.Service.Web.Tools.ServiceManagement.KMSearchWidget::searchWidget
0x7d97  ldarg.0
0x7d98  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Web.Tools.ServiceManagement.KMSearchWidget::SelectDefaultLanguage()
0x7d9d  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::set_SelectDefaultLanguage(valuetype [mscorlib]System.Guid)
0x7da2  ret
```
