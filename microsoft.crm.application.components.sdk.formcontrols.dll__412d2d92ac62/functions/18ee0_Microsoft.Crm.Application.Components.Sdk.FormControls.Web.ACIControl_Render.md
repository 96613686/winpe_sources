# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ACIControl::Render

- ea: `0x18ee0`
- end: `0x18ffc`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ACIControl::Render`
- size: `284`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x179c0`
- `0x17a10`
- `0x18ee0`
- `0x1c010`
- `0x1c080`
- `0x1c100`
- `0x1c140`
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
0x18ee0  ldarg.1
0x18ee1  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x18ee6  dup
0x18ee7  ldstr    aIframeFramebor// "<iframe frameborder=0"
0x18eec  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x18ef1  ldc.i4.s 0x11
0x18ef3  stloc.0
0x18ef4  ldloca.s 0
0x18ef6  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x18efc  callvirt instance string [mscorlib]System.Object::ToString()
0x18f01  ldarg.0
0x18f02  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x18f07  ldarg.1
0x18f08  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x18f0d  ldc.i4.s 0x14
0x18f0f  stloc.0
0x18f10  ldloca.s 0
0x18f12  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x18f18  callvirt instance string [mscorlib]System.Object::ToString()
0x18f1d  ldarg.0
0x18f1e  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x18f23  ldarg.1
0x18f24  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x18f29  ldc.i4.s 0xA
0x18f2b  stloc.0
0x18f2c  ldloca.s 0
0x18f2e  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x18f34  callvirt instance string [mscorlib]System.Object::ToString()
0x18f39  ldarg.0
0x18f3a  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::get_ClassName()
0x18f3f  ldarg.1
0x18f40  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x18f45  ldarg.0
0x18f46  ldarg.1
0x18f47  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::WriteStyleAttribute(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x18f4c  ldstr    aDelayinitializ// "delayinitialize"
0x18f51  ldarg.0
0x18f52  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::get_UseDelayInitialize()
0x18f57  brtrue.s loc_18F60
0x18f59  ldstr    a0// "0"
0x18f5e  br.s     loc_18F65
0x18f60  ldstr    a1_0// "1"
0x18f65  ldarg.1
0x18f66  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x18f6b  ldc.i4.s 0x20
0x18f6d  stloc.0
0x18f6e  ldloca.s 0
0x18f70  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x18f76  callvirt instance string [mscorlib]System.Object::ToString()
0x18f7b  ldarg.0
0x18f7c  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x18f81  stloc.1
0x18f82  ldloca.s 1
0x18f84  ldstr    aD// "D"
0x18f89  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18f8e  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x18f93  ldarg.1
0x18f94  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x18f99  ldarg.0
0x18f9a  ldarg.1
0x18f9b  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::WriteUrlAttribute(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x18fa0  ldarg.0
0x18fa1  ldarg.1
0x18fa2  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::WriteSecurityAttribute(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x18fa7  ldarg.0
0x18fa8  ldarg.1
0x18fa9  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::WriteSandboxAttribute(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x18fae  ldstr    aScrolling// "scrolling"
0x18fb3  ldarg.0
0x18fb4  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::get_Scrolling()
0x18fb9  ldarg.1
0x18fba  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x18fbf  ldstr    aPreload// "preload"
0x18fc4  ldarg.0
0x18fc5  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::get_Preload()
0x18fca  brtrue.s loc_18FD3
0x18fcc  ldstr    a0// "0"
0x18fd1  br.s     loc_18FD8
0x18fd3  ldstr    a1_0// "1"
0x18fd8  ldarg.1
0x18fd9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x18fde  ldarg.0
0x18fdf  ldarg.1
0x18fe0  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::WriteSrcAttribute(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x18fe5  dup
0x18fe6  ldarg.0
0x18fe7  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_Expandos()
0x18fec  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x18ff1  ldstr    aIframe_0// "></iframe>"
0x18ff6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x18ffb  ret
```
