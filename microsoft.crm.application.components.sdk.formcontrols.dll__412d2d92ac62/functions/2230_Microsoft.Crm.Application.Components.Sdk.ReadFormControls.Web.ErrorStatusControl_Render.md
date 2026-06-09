# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ErrorStatusControl::Render

- ea: `0x2230`
- end: `0x22d1`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ErrorStatusControl::Render`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1290`

## string_xrefs

- `0x228c`: `\n				<div class='status-message-flyout' id='footer-status-message-flyout' style='display: none;'>\n					<div class='status-message-detail' style='display: block; '></div>\n					<div class='status-message-flyout-arrow' style='display: block; '>\n						<img src='/_imgs/imagestrips/transparent_spacer.gif' class='ms-crm-ImageStrip-inlineedit_arrow' alt=''>\n					</div>\n				</div>\n				<div class='ms-crm-Read-Message' id='{0}' role='alert' aria-live='polite' aria-atomic='true'>\n					<div c`

## pseudocode

```c

```

## disassembly

```asm
0x2230  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x2235  ldc.i4.1
0x2236  newarr   [mscorlib]System.Char
0x223b  dup
0x223c  ldc.i4.0
0x223d  ldc.i4.s 0x2F
0x223f  stelem.i2
0x2240  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x2245  ldstr    aImgsInlineedit// "/_imgs/inlineedit/alert.png"
0x224a  call     string [mscorlib]System.String::Concat(string, string)
0x224f  stloc.0
0x2250  ldarg.0
0x2251  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x2256  stloc.s  4
0x2258  ldloca.s 4
0x225a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x225f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2264  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x2269  stloc.1
0x226a  ldarg.0
0x226b  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x2270  ldc.i4.s 0xA
0x2272  add
0x2273  stloc.s  4
0x2275  ldloca.s 4
0x2277  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x227c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2281  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x2286  stloc.2
0x2287  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x228c  ldstr    aDivClassStatus// "\r\n\t\t\t\t<div class='status-message-"...
0x2291  ldc.i4.5
0x2292  newarr   [mscorlib]System.Object
0x2297  dup
0x2298  ldc.i4.0
0x2299  ldarg.0
0x229a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x229f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x22a4  stelem.ref
0x22a5  dup
0x22a6  ldc.i4.1
0x22a7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x22ac  ldstr    aFooterStatusco// "Footer_StatusControl_Save_ToolTip"
0x22b1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22b6  stelem.ref
0x22b7  dup
0x22b8  ldc.i4.2
0x22b9  ldloc.1
0x22ba  stelem.ref
0x22bb  dup
0x22bc  ldc.i4.3
0x22bd  ldloc.2
0x22be  stelem.ref
0x22bf  dup
0x22c0  ldc.i4.4
0x22c1  ldloc.0
0x22c2  stelem.ref
0x22c3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22c8  stloc.3
0x22c9  ldarg.1
0x22ca  ldloc.3
0x22cb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x22d0  ret
```
