# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.TextControl::Render

- ea: `0x8280`
- end: `0x82a1`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.TextControl::Render`
- size: `33`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x81b0`
- `0x9840`
- `0xa430`
- `0x10a30`
- `0x10eb0`
- `0x11070`
- `0x11a00`
- `0x11b20`
- `0x11dd0`
- `0x12a90`

## callees

- `0x1560`
- `0x8240`
- `0x8280`

## pseudocode

```c

```

## disassembly

```asm
0x8280  ldarg.0
0x8281  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.TextControl::get_IsPassword()
0x8286  brfalse.s loc_8299
0x8288  ldarg.1
0x8289  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x828e  ldstr    asc_39914// "***************"
0x8293  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x8298  ret
0x8299  ldarg.0
0x829a  ldarg.1
0x829b  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::Render(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x82a0  ret
```
