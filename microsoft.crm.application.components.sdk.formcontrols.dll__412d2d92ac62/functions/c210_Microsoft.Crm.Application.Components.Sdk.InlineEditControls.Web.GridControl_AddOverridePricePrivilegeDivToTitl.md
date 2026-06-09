# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddOverridePricePrivilegeDivToTitleContainer

- ea: `0xc210`
- end: `0xc21c`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddOverridePricePrivilegeDivToTitleContainer`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xbee0`

## callees

- `0xc220`

## string_xrefs

- `0xc211`: `hiddenOverridePricePrivilegeCheck_`

## pseudocode

```c

```

## disassembly

```asm
0xc210  ldarg.0
0xc211  ldstr    aHiddenoverride// "hiddenOverridePricePrivilegeCheck_"
0xc216  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddPrivilegeDivToTitleContainer(string idPrefix)
0xc21b  ret
```
