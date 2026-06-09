# Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::get_DisclaimerTextWhat

- ea: `0x77b0`
- end: `0x7833`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::get_DisclaimerTextWhat`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x77b0`

## string_xrefs

- `0x77b7`: `<a href="http://go.microsoft.com/fwlink/?LinkID=313946" target="_blank">`
- `0x780f`: `<a id='YammerGCCPrivacyDisclaimer1' target='_blank' href='http://go.microsoft.com/fwlink/p/?LinkID=513066'>`
- `0x781f`: `<a id='YammerGCCPrivacyDisclaimer2' target='_blank' href='http://go.microsoft.com/fwlink/p/?LinkID=513267'>`

## pseudocode

```c

```

## disassembly

```asm
0x77b0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsLive()
0x77b5  brtrue.s loc_77EE
0x77b7  ldstr    aAHrefHttpGoMic// "<a href=\"http://go.microsoft.com/fwlin"...
0x77bc  stloc.0
0x77bd  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x77c2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x77c7  ldstr    aWebToolsYammer_0// "Web.Tools.Yammer.Disclaimer.TextWhatDCR"
0x77cc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x77d1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x77d6  ldc.i4.2
0x77d7  newarr   [mscorlib]System.Object
0x77dc  dup
0x77dd  ldc.i4.0
0x77de  ldloc.0
0x77df  stelem.ref
0x77e0  dup
0x77e1  ldc.i4.1
0x77e2  ldstr    aA// "</a>"
0x77e7  stelem.ref
0x77e8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x77ed  ret
0x77ee  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x77f3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x77f8  ldstr    aGcclegaldiscla// "GCCLegalDisclaimer"
0x77fd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7802  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x7807  ldc.i4.4
0x7808  newarr   [mscorlib]System.Object
0x780d  dup
0x780e  ldc.i4.0
0x780f  ldstr    aAIdYammergccpr// "<a id='YammerGCCPrivacyDisclaimer1' tar"...
0x7814  stelem.ref
0x7815  dup
0x7816  ldc.i4.1
0x7817  ldstr    aA// "</a>"
0x781c  stelem.ref
0x781d  dup
0x781e  ldc.i4.2
0x781f  ldstr    aAIdYammergccpr_0// "<a id='YammerGCCPrivacyDisclaimer2' tar"...
0x7824  stelem.ref
0x7825  dup
0x7826  ldc.i4.3
0x7827  ldstr    aA// "</a>"
0x782c  stelem.ref
0x782d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7832  ret
```
