# Microsoft.Crm.Application.Components.UI.NavigationBar::RenderFormSelector

- ea: `0x24880`
- end: `0x248f9`
- name: `Microsoft.Crm.Application.Components.UI.NavigationBar::RenderFormSelector`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x24670`

## callees

- `0x24880`
- `0x24900`

## string_xrefs

- `0x24890`: `<div class="ms-crm-FormLeftNav-TabLinksRow">`

## pseudocode

```c

```

## disassembly

```asm
0x24880  ldarg.0
0x24881  ldfld    class Microsoft.Crm.Application.Components.UI.FormSelector Microsoft.Crm.Application.Components.UI.NavigationBar::_formSelector
0x24886  brfalse.s loc_248F8
0x24888  ldarg.1
0x24889  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x2488e  stloc.0
0x2488f  ldloc.0
0x24890  ldstr    aDivClassMsCrmF_1// "<div class=\"ms-crm-FormLeftNav-TabLink"...
0x24895  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2489a  ldarg.0
0x2489b  callvirt instance void Microsoft.Crm.Application.Components.UI.NavigationBar::PreRenderFormSelector()
0x248a0  ldarg.0
0x248a1  ldfld    class Microsoft.Crm.Application.Components.UI.FormSelector Microsoft.Crm.Application.Components.UI.NavigationBar::_formSelector
0x248a6  ldarg.1
0x248a7  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x248ac  ldloc.0
0x248ad  ldstr    aDiv// "</div>"
0x248b2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x248b7  ldloc.0
0x248b8  ldstr    aDivClassMsCrmF_2// "<div class=\"ms-crm-Form-LeftBar-Header"...
0x248bd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x248c2  ldloc.0
0x248c3  ldstr    aNobrClassMsCrm// "<nobr class=\"ms-crm-Nav-Group-Heading"...
0x248c8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x248cd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x248d2  ldstr    aNavbarDetailed// "NavBar_DetailedPage_Area_Header"
0x248d7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x248dc  ldloc.0
0x248dd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x248e2  ldloc.0
0x248e3  ldstr    aNobr_0// "</nobr>"
0x248e8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x248ed  ldloc.0
0x248ee  ldstr    aDiv// "</div>"
0x248f3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x248f8  ret
```
