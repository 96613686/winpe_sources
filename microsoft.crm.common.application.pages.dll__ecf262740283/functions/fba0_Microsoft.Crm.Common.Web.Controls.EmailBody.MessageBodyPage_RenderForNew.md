# Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::RenderForNew

- ea: `0xfba0`
- end: `0xfbf1`
- name: `Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::RenderForNew`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xf7c0`

## callees

- `0xfba0`

## string_xrefs

- `0xfbaf`: `<LINK rel=stylesheet href='/_forms/controls/controls.css.aspx'/>`

## pseudocode

```c

```

## disassembly

```asm
0xfba0  ldarg.1
0xfba1  ldstr    aDoctypeHtmlHtm_0// "<!DOCTYPE html><html><head>"
0xfba6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xfbab  ldarg.2
0xfbac  brfalse.s loc_FBB9
0xfbae  ldarg.1
0xfbaf  ldstr    aLinkRelStylesh// "<LINK rel=stylesheet href='/_forms/cont"...
0xfbb4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xfbb9  ldarg.1
0xfbba  ldstr    aBrHeadBodyStyl// "<br></head><body style=\"font-size:12px"...
0xfbbf  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xfbc4  ldarg.1
0xfbc5  ldarg.0
0xfbc6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xfbcb  ldstr    aMicrosoftCrmMs// "Microsoft_Crm_Msgbody_Default_fonts"
0xfbd0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xfbd5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xfbda  ldarg.1
0xfbdb  ldstr    aPositionAbsolu// "; position: absolute; height: 95%; widt"...
0xfbe0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xfbe5  ldarg.1
0xfbe6  ldstr    aDivDivBodyHtml// "\"><div></div></body></html>"
0xfbeb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xfbf0  ret
```
