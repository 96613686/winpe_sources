# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::AddContent

- ea: `0xf020`
- end: `0xf082`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::AddContent`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xee50`

## callees

- `0xf090`
- `0xf0f0`
- `0xf120`
- `0xf160`
- `0xf1c0`

## string_xrefs

- `0xf05b`: `ms-crm-LinkControl-content`

## pseudocode

```c

```

## disassembly

```asm
0xf020  ldarg.1
0xf021  ldc.i4.s 0x11
0xf023  ldarg.0
0xf024  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xf029  ldstr    aFlyoutcontent// "_flyoutContent"
0xf02e  call     string [mscorlib]System.String::Concat(string, string)
0xf033  ldc.i4.0
0xf034  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string, bool)
0xf039  ldarg.0
0xf03a  ldarg.1
0xf03b  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::AddTabIndexAttribute(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xf040  ldarg.0
0xf041  ldarg.1
0xf042  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::AddTitleAttribute(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xf047  ldarg.0
0xf048  ldarg.1
0xf049  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::AddButtonsToolTip(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xf04e  ldarg.0
0xf04f  ldarg.1
0xf050  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::AddEventAttributes(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xf055  ldarg.1
0xf056  ldstr    aClass// "class"
0xf05b  ldstr    aMsCrmLinkcontr// "ms-crm-LinkControl-content"
0xf060  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0xf065  ldarg.0
0xf066  ldarg.1
0xf067  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::AddViewportAttribute(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xf06c  ldarg.1
0xf06d  ldc.i4.s 0x19
0xf06f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0xf074  ldarg.0
0xf075  ldarg.1
0xf076  call     instance void [System.Web]System.Web.UI.Control::RenderChildren(class [System.Web]System.Web.UI.HtmlTextWriter)
0xf07b  ldarg.1
0xf07c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0xf081  ret
```
