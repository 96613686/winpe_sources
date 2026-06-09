# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl

- ea: `0x1ce20`
- end: `0x1ce3f`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl`
- size: `31`
- prototype: ``
- caller_count: `41`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xbee0`
- `0xc1b0`
- `0xc7d0`
- `0xc910`
- `0xca90`
- `0xcd00`
- `0xcee0`
- `0xd0a0`
- `0xd290`
- `0xd480`
- `0xd560`
- `0xd700`
- `0xde50`
- `0x1c720`
- `0x1c730`
- `0x1c740`
- `0x1c7a0`
- `0x1c7b0`
- `0x1c7c0`
- `0x1c7d0`
- `0x1ca00`
- `0x1ca10`
- `0x1ca50`
- `0x1ca60`
- `0x1cb00`
- `0x1cb10`
- `0x1cbc0`
- `0x1cbd0`
- `0x1cbe0`
- `0x1cc20`
- `0x1cce0`
- `0x1cd00`
- `0x1cd20`
- `0x1cd30`
- `0x1cde0`
- `0x1d040`
- `0x1d330`
- `0x1def0`
- `0x1dfc0`
- `0x1e230`
- `0x1e5f0`

## callees

- `0x1ce20`

## pseudocode

```c

```

## disassembly

```asm
0x1ce20  ldarg.0
0x1ce21  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::_compositeControl
0x1ce26  brtrue.s loc_1CE38
0x1ce28  ldarg.0
0x1ce29  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.CustomGridProviderFactory::.ctor()
0x1ce2e  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::.ctor(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ICustomGridProviderFactory)
0x1ce33  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::_compositeControl
0x1ce38  ldarg.0
0x1ce39  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::_compositeControl
0x1ce3e  ret
```
