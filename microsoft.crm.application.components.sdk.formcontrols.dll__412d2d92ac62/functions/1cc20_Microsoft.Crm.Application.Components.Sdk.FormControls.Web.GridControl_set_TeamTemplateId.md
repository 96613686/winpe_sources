# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_TeamTemplateId

- ea: `0x1cc20`
- end: `0x1cc44`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_TeamTemplateId`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1ce20`

## string_xrefs

- `0x1cc2d`: `teamTemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x1cc20  ldarg.0
0x1cc21  ldarg.1
0x1cc22  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::_teamTemplateId
0x1cc27  ldarg.0
0x1cc28  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1cc2d  ldstr    aTeamtemplateid// "teamTemplateId"
0x1cc32  ldarga.s 1
0x1cc34  ldstr    aB// "B"
0x1cc39  call     instance string [mscorlib]System.Guid::ToString(string)
0x1cc3e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::SetParameter(string, string)
0x1cc43  ret
```
