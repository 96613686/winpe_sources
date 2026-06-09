# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.UnboundFrameControl::Render

- ea: `0x2c970`
- end: `0x2ca7e`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.UnboundFrameControl::Render`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x179c0`
- `0x17a10`
- `0x1c010`
- `0x1c080`
- `0x1c100`
- `0x1c140`
- `0x1c350`
- `0x1c390`
- `0x1c3d0`
- `0x2c970`

## pseudocode

```c

```

## disassembly

```asm
0x2c970  ldarg.1
0x2c971  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x2c976  dup
0x2c977  ldstr    aIframeFramebor// "<iframe frameborder=0"
0x2c97c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2c981  ldc.i4.s 0x11
0x2c983  stloc.0
0x2c984  ldloca.s 0
0x2c986  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x2c98c  callvirt instance string [mscorlib]System.Object::ToString()
0x2c991  ldarg.0
0x2c992  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c997  ldarg.1
0x2c998  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2c99d  ldc.i4.s 0x14
0x2c99f  stloc.0
0x2c9a0  ldloca.s 0
0x2c9a2  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x2c9a8  callvirt instance string [mscorlib]System.Object::ToString()
0x2c9ad  ldarg.0
0x2c9ae  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2c9b3  ldarg.1
0x2c9b4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2c9b9  ldc.i4.s 0xA
0x2c9bb  stloc.0
0x2c9bc  ldloca.s 0
0x2c9be  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x2c9c4  callvirt instance string [mscorlib]System.Object::ToString()
0x2c9c9  ldarg.0
0x2c9ca  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::get_ClassName()
0x2c9cf  ldarg.1
0x2c9d0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2c9d5  ldarg.0
0x2c9d6  ldarg.1
0x2c9d7  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::WriteStyleAttribute(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x2c9dc  ldstr    aDelayinitializ// "delayinitialize"
0x2c9e1  ldarg.0
0x2c9e2  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::get_UseDelayInitialize()
0x2c9e7  brtrue.s loc_2C9F0
0x2c9e9  ldstr    a0// "0"
0x2c9ee  br.s     loc_2C9F5
0x2c9f0  ldstr    a1_0// "1"
0x2c9f5  ldarg.1
0x2c9f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2c9fb  ldc.i4.s 0x20
0x2c9fd  stloc.0
0x2c9fe  ldloca.s 0
0x2ca00  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x2ca06  callvirt instance string [mscorlib]System.Object::ToString()
0x2ca0b  ldarg.0
0x2ca0c  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x2ca11  stloc.1
0x2ca12  ldloca.s 1
0x2ca14  ldstr    aD// "D"
0x2ca19  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2ca1e  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x2ca23  ldarg.1
0x2ca24  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2ca29  ldarg.0
0x2ca2a  ldarg.1
0x2ca2b  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::WriteUrlAttribute(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x2ca30  ldstr    aScrolling// "scrolling"
0x2ca35  ldarg.0
0x2ca36  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::get_Scrolling()
0x2ca3b  ldarg.1
0x2ca3c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2ca41  ldstr    aPreload// "preload"
0x2ca46  ldarg.0
0x2ca47  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::get_Preload()
0x2ca4c  brtrue.s loc_2CA55
0x2ca4e  ldstr    a0// "0"
0x2ca53  br.s     loc_2CA5A
0x2ca55  ldstr    a1_0// "1"
0x2ca5a  ldarg.1
0x2ca5b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2ca60  ldarg.0
0x2ca61  ldarg.1
0x2ca62  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::WriteSrcAttribute(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x2ca67  dup
0x2ca68  ldarg.0
0x2ca69  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_Expandos()
0x2ca6e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2ca73  ldstr    aIframe_0// "></iframe>"
0x2ca78  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2ca7d  ret
```
