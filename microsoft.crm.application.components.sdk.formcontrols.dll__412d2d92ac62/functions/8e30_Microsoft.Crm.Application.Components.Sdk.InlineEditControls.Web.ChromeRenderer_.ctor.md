# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::.ctor

- ea: `0x8e30`
- end: `0x8e49`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::.ctor`
- size: `25`
- prototype: ``
- caller_count: `18`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x8bd0`
- `0x9840`
- `0xa430`
- `0xb050`
- `0xb120`
- `0xb1d0`
- `0xe810`
- `0xfaf0`
- `0x10a30`
- `0x10eb0`
- `0x11070`
- `0x11a00`
- `0x11b20`
- `0x11dd0`
- `0x12080`
- `0x128e0`
- `0x12970`
- `0x12a90`

## pseudocode

```c

```

## disassembly

```asm
0x8e30  ldarg.0
0x8e31  call     instance void [mscorlib]System.Object::.ctor()
0x8e36  ldarg.0
0x8e37  ldarg.1
0x8e38  stfld    class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::_formDataControl
0x8e3d  ldarg.0
0x8e3e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x8e43  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::_customHtmlAttributes
0x8e48  ret
```
