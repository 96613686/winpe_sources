# Microsoft.Crm.Application.Components.UI.HtmlBar::RenderPostControls_0

- ea: `0x19be0`
- end: `0x19c9f`
- name: `Microsoft.Crm.Application.Components.UI.HtmlBar::RenderPostControls_0`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x19bd0`

## callees

- `0x19650`
- `0x19680`
- `0x19690`
- `0x19a90`
- `0x19b10`
- `0x19be0`
- `0x19ca0`

## string_xrefs

- `0x19c54`: `Mscrm.Rte.AddHyperlink(`
- `0x19c74`: `HtmlBar.Button.AddHyperlink`
- `0x19c7e`: `cmd-insertHyperlink`
- `0x19c83`: `addHyperlink`

## pseudocode

```c

```

## disassembly

```asm
0x19be0  ldarg.0
0x19be1  ldarg.1
0x19be2  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddSpacer(class [mscorlib]System.IO.TextWriter output)
0x19be7  ldarg.0
0x19be8  ldc.i4.0
0x19be9  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::set_AllowSpacer(bool value)
0x19bee  ldarg.1
0x19bef  ldstr    aTdStylePadding// "<td style=\"padding:0px;\" ignoreforres"...
0x19bf4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19bf9  ldarg.0
0x19bfa  call     instance bool Microsoft.Crm.Application.Components.UI.HtmlBar::get_AddImage()
0x19bff  brfalse.s loc_19C4A
0x19c01  ldarg.0
0x19c02  ldarg.1
0x19c03  ldstr    aMscrmRteAddima// "Mscrm.Rte.AddImage("
0x19c08  ldarg.0
0x19c09  ldfld    int32 Microsoft.Crm.Application.Components.UI.HtmlBar::_entityCode
0x19c0e  box      [mscorlib]System.Int32
0x19c13  ldstr    asc_3BBA2// ");"
0x19c18  call     string [mscorlib]System.String::Concat(object, object, object)
0x19c1d  ldarg.0
0x19c1e  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19c23  ldstr    aHtmlbarButtonA// "HtmlBar.Button.AddImage"
0x19c28  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19c2d  ldstr    aCmdInsertimage// "cmd-insertImage"
0x19c32  ldstr    aAddimage// "addImage"
0x19c37  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddTextButton(class [mscorlib]System.IO.TextWriter output, string script, string title, string img, string id)
0x19c3c  ldarg.0
0x19c3d  ldc.i4.1
0x19c3e  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::set_AllowSpacer(bool value)
0x19c43  ldarg.0
0x19c44  ldarg.1
0x19c45  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddSpacer(class [mscorlib]System.IO.TextWriter output)
0x19c4a  ldarg.0
0x19c4b  call     instance bool Microsoft.Crm.Application.Components.UI.HtmlBar::get_AddHyperlink()
0x19c50  brfalse.s loc_19C94
0x19c52  ldarg.0
0x19c53  ldarg.1
0x19c54  ldstr    aMscrmRteAddhyp// "Mscrm.Rte.AddHyperlink("
0x19c59  ldarg.0
0x19c5a  ldfld    int32 Microsoft.Crm.Application.Components.UI.HtmlBar::_entityCode
0x19c5f  box      [mscorlib]System.Int32
0x19c64  ldstr    asc_3BBA2// ");"
0x19c69  call     string [mscorlib]System.String::Concat(object, object, object)
0x19c6e  ldarg.0
0x19c6f  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.UI.HtmlBar::_rm
0x19c74  ldstr    aHtmlbarButtonA_0// "HtmlBar.Button.AddHyperlink"
0x19c79  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19c7e  ldstr    aCmdInserthyper// "cmd-insertHyperlink"
0x19c83  ldstr    aAddhyperlink// "addHyperlink"
0x19c88  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::AddTextButton(class [mscorlib]System.IO.TextWriter output, string script, string title, string img, string id)
0x19c8d  ldarg.0
0x19c8e  ldc.i4.1
0x19c8f  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::set_AllowSpacer(bool value)
0x19c94  ldarg.2
0x19c95  brfalse.s loc_19C9E
0x19c97  ldarg.0
0x19c98  ldarg.1
0x19c99  call     instance void Microsoft.Crm.Application.Components.UI.HtmlBar::RenderPostControlsClosingTags(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x19c9e  ret
```
