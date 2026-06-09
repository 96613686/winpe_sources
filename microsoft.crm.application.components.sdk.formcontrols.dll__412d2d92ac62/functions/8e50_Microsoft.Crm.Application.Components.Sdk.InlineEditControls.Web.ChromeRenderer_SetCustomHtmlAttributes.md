# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes

- ea: `0x8e50`
- end: `0x8e5e`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes`
- size: `14`
- prototype: ``
- caller_count: `14`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x8bd0`
- `0xb120`
- `0xb1d0`
- `0xfaf0`
- `0x10a30`
- `0x11070`
- `0x11590`
- `0x11a90`
- `0x11b20`
- `0x11dd0`
- `0x12080`
- `0x128e0`
- `0x12970`
- `0x14dc0`

## pseudocode

```c

```

## disassembly

```asm
0x8e50  ldarg.0
0x8e51  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::_customHtmlAttributes
0x8e56  ldarg.1
0x8e57  ldarg.2
0x8e58  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x8e5d  ret
```
