# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::WriteSecurityAttribute

- ea: `0x1c5d0`
- end: `0x1c602`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::WriteSecurityAttribute`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18ee0`
- `0x1c230`

## callees

- `0x1c160`
- `0x1c5d0`
- `0x1c610`

## string_xrefs

- `0x1c5f5`: `security`

## pseudocode

```c

```

## disassembly

```asm
0x1c5d0  ldarg.0
0x1c5d1  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::get_EnableSandbox()
0x1c5d6  brtrue.s loc_1C5E0
0x1c5d8  ldarg.0
0x1c5d9  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::ConfigureSecurity()
0x1c5de  brtrue.s loc_1C5E1
0x1c5e0  ret
0x1c5e1  ldsfld   string [mscorlib]System.String::Empty
0x1c5e6  stloc.0
0x1c5e7  ldarg.0
0x1c5e8  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::ConfigureSecurity()
0x1c5ed  brfalse.s loc_1C5F5
0x1c5ef  ldstr    aRestricted// "restricted"
0x1c5f4  stloc.0
0x1c5f5  ldstr    aSecurity// "security"
0x1c5fa  ldloc.0
0x1c5fb  ldarg.1
0x1c5fc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1c601  ret
```
