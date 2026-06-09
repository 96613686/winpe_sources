# Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::get_NetBreezeDisclaimer

- ea: `0x8e90`
- end: `0x8f01`
- name: `Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::get_NetBreezeDisclaimer`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8e90`

## string_xrefs

- `0x8ea1`: `Web.Tools.NetBreeze.Config.Disclaimer.TextClaims`
- `0x8edd`: `<a id='NetBreezeGCCPrivacyDisclaimer1' target='_blank' href='http://go.microsoft.com/fwlink/p/?LinkID=513066'>`
- `0x8eed`: `<a id='NetBreezePrivacyDisclaimer2' target='_blank' href='http://go.microsoft.com/fwlink/p/?LinkID=513069'>`

## pseudocode

```c

```

## disassembly

```asm
0x8e90  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsLive()
0x8e95  brtrue.s loc_8EBC
0x8e97  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8e9c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8ea1  ldstr    aWebToolsNetbre// "Web.Tools.NetBreeze.Config.Disclaimer.T"...
0x8ea6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8eab  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x8eb0  ldc.i4.0
0x8eb1  newarr   [mscorlib]System.Object
0x8eb6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8ebb  ret
0x8ebc  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8ec1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8ec6  ldstr    aGcclegaldiscla// "GCCLegalDisclaimer"
0x8ecb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8ed0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x8ed5  ldc.i4.4
0x8ed6  newarr   [mscorlib]System.Object
0x8edb  dup
0x8edc  ldc.i4.0
0x8edd  ldstr    aAIdNetbreezegc// "<a id='NetBreezeGCCPrivacyDisclaimer1' "...
0x8ee2  stelem.ref
0x8ee3  dup
0x8ee4  ldc.i4.1
0x8ee5  ldstr    aA// "</a>"
0x8eea  stelem.ref
0x8eeb  dup
0x8eec  ldc.i4.2
0x8eed  ldstr    aAIdNetbreezepr// "<a id='NetBreezePrivacyDisclaimer2' tar"...
0x8ef2  stelem.ref
0x8ef3  dup
0x8ef4  ldc.i4.3
0x8ef5  ldstr    aA// "</a>"
0x8efa  stelem.ref
0x8efb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8f00  ret
```
