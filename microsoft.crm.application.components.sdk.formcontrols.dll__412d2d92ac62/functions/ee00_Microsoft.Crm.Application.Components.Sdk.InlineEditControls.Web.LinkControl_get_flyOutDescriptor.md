# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::get_flyOutDescriptor

- ea: `0xee00`
- end: `0xee1b`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::get_flyOutDescriptor`
- size: `27`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xed80`
- `0xeda0`
- `0xedf0`
- `0xee50`
- `0xf120`
- `0xf160`
- `0xf1c0`

## callees

- `0xee00`
- `0xee30`

## pseudocode

```c

```

## disassembly

```asm
0xee00  ldarg.0
0xee01  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.FlyOutDefinition.FlyOutDescriptor Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::_flyOutDescriptor
0xee06  brtrue.s loc_EE14
0xee08  ldarg.0
0xee09  ldarg.0
0xee0a  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.FlyOutDefinition.FlyOutDescriptor Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::GetFlyOutDescriptor()
0xee0f  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.FlyOutDefinition.FlyOutDescriptor Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::_flyOutDescriptor
0xee14  ldarg.0
0xee15  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.FlyOutDefinition.FlyOutDescriptor Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::_flyOutDescriptor
0xee1a  ret
```
