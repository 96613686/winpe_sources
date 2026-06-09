# Microsoft.Crm.Application.Components.UI.ProgressBar::Render

- ea: `0x20de0`
- end: `0x20f28`
- name: `Microsoft.Crm.Application.Components.UI.ProgressBar::Render`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x20cd0`
- `0x20cf0`
- `0x20d10`
- `0x20d30`
- `0x20d50`
- `0x20d70`
- `0x20d90`
- `0x20de0`
- `0x24120`

## pseudocode

```c

```

## disassembly

```asm
0x20de0  ldarg.1
0x20de1  ldstr    aSpan_4// "<span"
0x20de6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20deb  ldstr    aId// "id"
0x20df0  ldarg.0
0x20df1  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x20df6  ldarg.1
0x20df7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20dfc  ldarg.1
0x20dfd  ldstr    aClass_1// "class"
0x20e02  ldstr    aProgressbar// "progressbar"
0x20e07  ldc.i4.0
0x20e08  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x20e0d  ldstr    aLeftonpict// "leftOnPict"
0x20e12  ldarg.0
0x20e13  call     instance string Microsoft.Crm.Application.Components.UI.ProgressBar::get_LeftOnPict()
0x20e18  ldarg.1
0x20e19  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20e1e  ldstr    aLeftoffpict// "leftOffPict"
0x20e23  ldarg.0
0x20e24  call     instance string Microsoft.Crm.Application.Components.UI.ProgressBar::get_LeftOffPict()
0x20e29  ldarg.1
0x20e2a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20e2f  ldstr    aMidonpict// "midOnPict"
0x20e34  ldarg.0
0x20e35  call     instance string Microsoft.Crm.Application.Components.UI.ProgressBar::get_MidOnPict()
0x20e3a  ldarg.1
0x20e3b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20e40  ldstr    aMidoffpict// "midOffPict"
0x20e45  ldarg.0
0x20e46  call     instance string Microsoft.Crm.Application.Components.UI.ProgressBar::get_MidOffPict()
0x20e4b  ldarg.1
0x20e4c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20e51  ldstr    aRightonpict// "rightOnPict"
0x20e56  ldarg.0
0x20e57  call     instance string Microsoft.Crm.Application.Components.UI.ProgressBar::get_RightOnPict()
0x20e5c  ldarg.1
0x20e5d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20e62  ldstr    aRightoffpict// "rightOffPict"
0x20e67  ldarg.0
0x20e68  call     instance string Microsoft.Crm.Application.Components.UI.ProgressBar::get_RightOffPict()
0x20e6d  ldarg.1
0x20e6e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20e73  ldarg.1
0x20e74  ldstr    aMaxsteps// "maxSteps"
0x20e79  ldarg.0
0x20e7a  call     instance int32 Microsoft.Crm.Application.Components.UI.ProgressBar::get_Steps()
0x20e7f  stloc.0
0x20e80  ldloca.s 0
0x20e82  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20e87  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x20e8c  ldc.i4.0
0x20e8d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x20e92  ldarg.1
0x20e93  ldarg.0
0x20e94  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x20e99  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20e9e  ldarg.1
0x20e9f  ldstr    asc_2B7B6// ">"
0x20ea4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20ea9  ldarg.1
0x20eaa  ldstr    aImgAltSrc// "<img alt=\"\" src=\""
0x20eaf  ldarg.0
0x20eb0  call     instance string Microsoft.Crm.Application.Components.UI.ProgressBar::get_LeftOffPict()
0x20eb5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x20eba  ldstr    asc_59BB0// "\"/>"
0x20ebf  call     string [mscorlib]System.String::Concat(string, string, string)
0x20ec4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20ec9  ldc.i4.1
0x20eca  stloc.1
0x20ecb  br.s     loc_20EF1
0x20ecd  ldarg.1
0x20ece  ldstr    aImgAltSrc// "<img alt=\"\" src=\""
0x20ed3  ldarg.0
0x20ed4  call     instance string Microsoft.Crm.Application.Components.UI.ProgressBar::get_MidOffPict()
0x20ed9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x20ede  ldstr    asc_59BB0// "\"/>"
0x20ee3  call     string [mscorlib]System.String::Concat(string, string, string)
0x20ee8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20eed  ldloc.1
0x20eee  ldc.i4.1
0x20eef  add
0x20ef0  stloc.1
0x20ef1  ldloc.1
0x20ef2  ldarg.0
0x20ef3  ldfld    int32 Microsoft.Crm.Application.Components.UI.ProgressBar::_steps
0x20ef8  ldc.i4.1
0x20ef9  sub
0x20efa  blt.s    loc_20ECD
0x20efc  ldarg.1
0x20efd  ldstr    aImgAltSrc// "<img alt=\"\" src=\""
0x20f02  ldarg.0
0x20f03  call     instance string Microsoft.Crm.Application.Components.UI.ProgressBar::get_RightOffPict()
0x20f08  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x20f0d  ldstr    asc_59BB0// "\"/>"
0x20f12  call     string [mscorlib]System.String::Concat(string, string, string)
0x20f17  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20f1c  ldarg.1
0x20f1d  ldstr    aSpan// "</span>"
0x20f22  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20f27  ret
```
