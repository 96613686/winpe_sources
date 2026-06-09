# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_RelationshipName

- ea: `0x1ca10`
- end: `0x1ca1c`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_RelationshipName`
- size: `12`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xbc80`
- `0x1ca70`
- `0x1cab0`
- `0x1cdf0`
- `0x1d040`
- `0x1d2a0`
- `0x1d330`

## callees

- `0x1ce20`

## pseudocode

```c

```

## disassembly

```asm
0x1ca10  ldarg.0
0x1ca11  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1ca16  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_RelationshipName()
0x1ca1b  ret
```
