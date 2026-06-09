# Microsoft.Crm.Application.Utility.Util::GetConfigurableThemeStyleSheetUrl

- ea: `0x49000`
- end: `0x49061`
- name: `Microsoft.Crm.Application.Utility.Util::GetConfigurableThemeStyleSheetUrl`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x2fb90`
- `0x39f50`
- `0x49070`

## string_xrefs

- `0x4900b`: `/_common/styles/configurabletheme.aspx?{0}={1}&{2}={3}`
- `0x49033`: `updateTimeStamp`
- `0x4903c`: `updateTimeStamp`

## pseudocode

```c

```

## disassembly

```asm
0x49000  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Utility.Util::GetConfigurableThemeStyleParameters()
0x49005  stloc.0
0x49006  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4900b  ldstr    aCommonStylesCo// "/_common/styles/configurabletheme.aspx?"...
0x49010  ldc.i4.4
0x49011  newarr   [mscorlib]System.Object
0x49016  dup
0x49017  ldc.i4.0
0x49018  ldstr    aThemeid// "themeId"
0x4901d  stelem.ref
0x4901e  dup
0x4901f  ldc.i4.1
0x49020  ldloc.0
0x49021  ldstr    aThemeid// "themeId"
0x49026  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x4902b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlPathEncode(string)
0x49030  stelem.ref
0x49031  dup
0x49032  ldc.i4.2
0x49033  ldstr    aUpdatetimestam// "updateTimeStamp"
0x49038  stelem.ref
0x49039  dup
0x4903a  ldc.i4.3
0x4903b  ldloc.0
0x4903c  ldstr    aUpdatetimestam// "updateTimeStamp"
0x49041  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x49046  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlPathEncode(string)
0x4904b  stelem.ref
0x4904c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x49051  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x49056  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::Create(string uri, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4905b  callvirt instance string [mscorlib]System.Object::ToString()
0x49060  ret
```
