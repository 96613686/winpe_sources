# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid

- ea: `0x1cde0`
- end: `0x1cdec`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid`
- size: `12`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xbc80`
- `0xbd60`
- `0xde80`
- `0x1c740`
- `0x1ceb0`
- `0x1d040`
- `0x1d2a0`
- `0x1d330`
- `0x1dbd0`
- `0x1dfc0`
- `0x1e1b0`
- `0x1e230`
- `0x1e650`

## callees

- `0x1ce20`

## pseudocode

```c

```

## disassembly

```asm
0x1cde0  ldarg.0
0x1cde1  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1cde6  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x1cdeb  ret
```
