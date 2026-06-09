# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddQuickAddHiddenPrivilegeDivToTitleContainer

- ea: `0xc200`
- end: `0xc20c`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddQuickAddHiddenPrivilegeDivToTitleContainer`
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

- `0xc201`: `hiddenAddPrivilegeCheck_`

## pseudocode

```c

```

## disassembly

```asm
0xc200  ldarg.0
0xc201  ldstr    aHiddenaddprivi// "hiddenAddPrivilegeCheck_"
0xc206  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddPrivilegeDivToTitleContainer(string idPrefix)
0xc20b  ret
```
