# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::Render

- ea: `0x1c230`
- end: `0x1c34c`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::Render`
- size: `284`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x179c0`
- `0x17a10`
- `0x1c010`
- `0x1c080`
- `0x1c100`
- `0x1c140`
- `0x1c230`
- `0x1c350`
- `0x1c390`
- `0x1c3d0`
- `0x1c570`
- `0x1c5d0`

## pseudocode

```c

```

## disassembly

```asm
0x1c230  ldarg.1
0x1c231  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1c236  dup
0x1c237  ldstr    aIframeFramebor// "<iframe frameborder=0"
0x1c23c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c241  ldc.i4.s 0x11
0x1c243  stloc.0
0x1c244  ldloca.s 0
0x1c246  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x1c24c  callvirt instance string [mscorlib]System.Object::ToString()
0x1c251  ldarg.0
0x1c252  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1c257  ldarg.1
0x1c258  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1c25d  ldc.i4.s 0x14
0x1c25f  stloc.0
0x1c260  ldloca.s 0
0x1c262  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x1c268  callvirt instance string [mscorlib]System.Object::ToString()
0x1c26d  ldarg.0
0x1c26e  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1c273  ldarg.1
0x1c274  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1c279  ldc.i4.s 0xA
0x1c27b  stloc.0
0x1c27c  ldloca.s 0
0x1c27e  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x1c284  callvirt instance string [mscorlib]System.Object::ToString()
0x1c289  ldarg.0
0x1c28a  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::get_ClassName()
0x1c28f  ldarg.1
0x1c290  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1c295  ldarg.0
0x1c296  ldarg.1
0x1c297  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::WriteStyleAttribute(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x1c29c  ldstr    aDelayinitializ// "delayinitialize"
0x1c2a1  ldarg.0
0x1c2a2  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::get_UseDelayInitialize()
0x1c2a7  brtrue.s loc_1C2B0
0x1c2a9  ldstr    a0// "0"
0x1c2ae  br.s     loc_1C2B5
0x1c2b0  ldstr    a1_0// "1"
0x1c2b5  ldarg.1
0x1c2b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1c2bb  ldc.i4.s 0x20
0x1c2bd  stloc.0
0x1c2be  ldloca.s 0
0x1c2c0  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x1c2c6  callvirt instance string [mscorlib]System.Object::ToString()
0x1c2cb  ldarg.0
0x1c2cc  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x1c2d1  stloc.1
0x1c2d2  ldloca.s 1
0x1c2d4  ldstr    aD// "D"
0x1c2d9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c2de  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1c2e3  ldarg.1
0x1c2e4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1c2e9  ldarg.0
0x1c2ea  ldarg.1
0x1c2eb  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::WriteUrlAttribute(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x1c2f0  ldarg.0
0x1c2f1  ldarg.1
0x1c2f2  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::WriteSecurityAttribute(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x1c2f7  ldarg.0
0x1c2f8  ldarg.1
0x1c2f9  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::WriteSandboxAttribute(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x1c2fe  ldstr    aScrolling// "scrolling"
0x1c303  ldarg.0
0x1c304  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::get_Scrolling()
0x1c309  ldarg.1
0x1c30a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1c30f  ldstr    aPreload// "preload"
0x1c314  ldarg.0
0x1c315  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::get_Preload()
0x1c31a  brtrue.s loc_1C323
0x1c31c  ldstr    a0// "0"
0x1c321  br.s     loc_1C328
0x1c323  ldstr    a1_0// "1"
0x1c328  ldarg.1
0x1c329  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1c32e  ldarg.0
0x1c32f  ldarg.1
0x1c330  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::WriteSrcAttribute(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x1c335  dup
0x1c336  ldarg.0
0x1c337  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_Expandos()
0x1c33c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c341  ldstr    aIframe_0// "></iframe>"
0x1c346  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c34b  ret
```
