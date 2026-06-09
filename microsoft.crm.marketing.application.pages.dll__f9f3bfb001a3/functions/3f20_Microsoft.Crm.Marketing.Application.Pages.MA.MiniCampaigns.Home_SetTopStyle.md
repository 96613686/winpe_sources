# Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaigns.Home::SetTopStyle

- ea: `0x3f20`
- end: `0x3f4f`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaigns.Home::SetTopStyle`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3f10`

## pseudocode

```c

```

## disassembly

```asm
0x3f20  ldc.i4.s 0x3E
0x3f22  stloc.0
0x3f23  ldarg.0
0x3f24  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaigns.Home::mcGridContainer
0x3f29  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x3f2e  ldstr    aTop// "top"
0x3f33  ldloca.s 0
0x3f35  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3f3a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x3f3f  ldstr    aPx// "px"
0x3f44  call     string [mscorlib]System.String::Concat(string, string)
0x3f49  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x3f4e  ret
```
