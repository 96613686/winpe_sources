# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::Render

- ea: `0x293e0`
- end: `0x294a0`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::Render`
- size: `192`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x293e0`
- `0x294a0`
- `0x294d0`
- `0x29610`
- `0x29660`
- `0x296b0`
- `0x297c0`
- `0x29810`
- `0x29860`
- `0x298b0`
- `0x29970`
- `0x29a20`
- `0x29a60`
- `0x29b00`

## pseudocode

```c

```

## disassembly

```asm
0x293e0  ldarg.0
0x293e1  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::get_IsWorkflowEditorPage()
0x293e6  brfalse.s loc_29414
0x293e8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x293ed  ldstr    aQuickformWorkf// "Quickform.Workflow.Message"
0x293f2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x293f7  ldarg.1
0x293f8  ldstr    aDivStyleBorder_1// "<div style=\"border:1px solid #D6D6D6;h"...
0x293fd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x29402  ldarg.1
0x29403  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x29408  ldarg.1
0x29409  ldstr    aDiv_0// "</div>"
0x2940e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x29413  ret
0x29414  ldarg.0
0x29415  ldarg.1
0x29416  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x2941b  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::WriteOpeningTag(class [mscorlib]System.IO.TextWriter writer)
0x29420  ldarg.0
0x29421  ldarg.1
0x29422  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x29427  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::RenderTitleAndButtons(class [mscorlib]System.IO.TextWriter writer)
0x2942c  ldarg.0
0x2942d  ldarg.1
0x2942e  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x29433  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::RenderSpinner(class [mscorlib]System.IO.TextWriter writer)
0x29438  ldarg.0
0x29439  ldarg.1
0x2943a  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x2943f  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::RenderNewEntityScreen(class [mscorlib]System.IO.TextWriter writer)
0x29444  ldarg.0
0x29445  ldarg.1
0x29446  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x2944b  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::RenderConfigurationDiv(class [mscorlib]System.IO.TextWriter writer)
0x29450  ldarg.0
0x29451  ldarg.1
0x29452  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x29457  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::RenderUnauthorizedDiv(class [mscorlib]System.IO.TextWriter writer)
0x2945c  ldarg.0
0x2945d  ldarg.1
0x2945e  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x29463  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::RenderDisabledDiv(class [mscorlib]System.IO.TextWriter writer)
0x29468  ldarg.0
0x29469  ldarg.1
0x2946a  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x2946f  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::RenderOutlookOfflineDiv(class [mscorlib]System.IO.TextWriter writer)
0x29474  ldarg.0
0x29475  ldarg.1
0x29476  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x2947b  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::RenderSignInRequiredDiv(class [mscorlib]System.IO.TextWriter writer)
0x29480  ldarg.0
0x29481  ldarg.1
0x29482  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x29487  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::RenderSessionExpiredDiv(class [mscorlib]System.IO.TextWriter writer)
0x2948c  ldarg.0
0x2948d  ldarg.1
0x2948e  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::RenderInnerIFrameControl(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x29493  ldarg.0
0x29494  ldarg.1
0x29495  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x2949a  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::WriteClosingTag(class [mscorlib]System.IO.TextWriter writer)
0x2949f  ret
```
