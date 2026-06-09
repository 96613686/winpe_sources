# Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_OriginalRequestUri

- ea: `0x13590`
- end: `0x135af`
- name: `Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::get_OriginalRequestUri`
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

- `0x13598`: `RequestUri`

## pseudocode

```c

```

## disassembly

```asm
0x13590  ldarg.0
0x13591  ldarg.0
0x13592  ldarg.0
0x13593  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::_originalRequestUrl
0x13598  ldstr    aRequesturi// "RequestUri"
0x1359d  ldc.i4.2
0x1359e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::GetQueryStringUri(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri currentUri, string Key, valuetype [System]System.UriKind uriKind)
0x135a3  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::_originalRequestUrl
0x135a8  ldarg.0
0x135a9  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::_originalRequestUrl
0x135ae  ret
```
