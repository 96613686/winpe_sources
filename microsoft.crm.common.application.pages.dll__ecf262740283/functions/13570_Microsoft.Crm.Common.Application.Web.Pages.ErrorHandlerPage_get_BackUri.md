# Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_BackUri

- ea: `0x13570`
- end: `0x1358f`
- name: `Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_BackUri`
- size: `31`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x13390`
- `0x13630`
- `0x13760`

## callees

- `0x135b0`

## string_xrefs

- `0x13578`: `BackUri`

## pseudocode

```c

```

## disassembly

```asm
0x13570  ldarg.0
0x13571  ldarg.0
0x13572  ldarg.0
0x13573  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::_backUri
0x13578  ldstr    aBackuri// "BackUri"
0x1357d  ldc.i4.1
0x1357e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::GetQueryStringUri(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri currentUri, string Key, valuetype [System]System.UriKind uriKind)
0x13583  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::_backUri
0x13588  ldarg.0
0x13589  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::_backUri
0x1358e  ret
```
