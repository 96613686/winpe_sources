# Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::RenderHtml

- ea: `0xfa70`
- end: `0xfb31`
- name: `Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::RenderHtml`
- size: `193`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf9c0`
- `0xfa10`

## callees

- `0xfa70`
- `0xfb40`

## string_xrefs

- `0xfb09`: `<LINK rel=stylesheet href='/_forms/controls/controls.css.aspx'/>`

## pseudocode

```c

```

## disassembly

```asm
0xfa70  ldarg.0
0xfa71  ldarg.2
0xfa72  call     instance string Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::InjectWRPCTokenIntoAttachmentDownloadUrls(string data)
0xfa77  starg.s  2
0xfa79  ldarg.2
0xfa7a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfa7f  brtrue.s loc_FA8D
0xfa81  ldarg.3
0xfa82  brtrue.s loc_FA8D
0xfa84  ldarg.2
0xfa85  call     string [Microsoft.Crm.SafeHtml]Microsoft.Crm.SafeHtml::GetSafeHtml(string)
0xfa8a  stloc.0
0xfa8b  br.s     loc_FAA1
0xfa8d  ldarg.2
0xfa8e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfa93  ldc.i4.0
0xfa94  ceq
0xfa96  ldarg.3
0xfa97  and
0xfa98  brfalse.s loc_FA9F
0xfa9a  call     void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext::ValidateTokenState()
0xfa9f  ldarg.2
0xfaa0  stloc.0
0xfaa1  ldarg.0
0xfaa2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xfaa7  ldstr    aMicrosoftCrmMs// "Microsoft_Crm_Msgbody_Default_fonts"
0xfaac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xfab1  stloc.1
0xfab2  ldarg.1
0xfab3  ldstr    aDoctypeHtmlHtm// "<!DOCTYPE html><html><head><base target"...
0xfab8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xfabd  ldarg.1
0xfabe  ldloc.1
0xfabf  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xfac4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xfac9  ldarg.1
0xfaca  ldstr    aMargin0px// "; margin: 0px"
0xfacf  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xfad4  ldarg.1
0xfad5  ldstr    aPositionAbsolu// "; position: absolute; height: 95%; widt"...
0xfada  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xfadf  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xfae4  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xfae9  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0xfaee  brfalse.s loc_FAFD
0xfaf0  ldarg.1
0xfaf1  ldstr    aFontSize12pxDi// "; font-size: 12px; direction: rtl; } pr"...
0xfaf6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xfafb  br.s     loc_FB08
0xfafd  ldarg.1
0xfafe  ldstr    aFontSize12pxPr// "; font-size: 12px; } pre.mscrmpretag { "...
0xfb03  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xfb08  ldarg.1
0xfb09  ldstr    aLinkRelStylesh// "<LINK rel=stylesheet href='/_forms/cont"...
0xfb0e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xfb13  ldarg.1
0xfb14  ldstr    aHead// "</head>"
0xfb19  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xfb1e  ldarg.1
0xfb1f  ldloc.0
0xfb20  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xfb25  ldarg.1
0xfb26  ldstr    aHtml// "</html>"
0xfb2b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xfb30  ret
```
