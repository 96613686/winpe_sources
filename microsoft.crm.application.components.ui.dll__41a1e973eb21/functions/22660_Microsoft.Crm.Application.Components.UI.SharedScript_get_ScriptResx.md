# Microsoft.Crm.Application.Components.UI.SharedScript::get_ScriptResx

- ea: `0x22660`
- end: `0x226d6`
- name: `Microsoft.Crm.Application.Components.UI.SharedScript::get_ScriptResx`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x3ae0`

## callees

- `0x226f0`
- `0x22710`
- `0x227a0`

## string_xrefs

- `0x22660`: `/_common/ScriptResx.ashx`

## pseudocode

```c

```

## disassembly

```asm
0x22660  ldstr    aCommonScriptre_0// "/_common/ScriptResx.ashx"
0x22665  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2266a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2266f  stloc.0
0x22670  ldloc.0
0x22671  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x22676  ldstr    aLcid// "lcid"
0x2267b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x22680  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x22685  stloc.1
0x22686  ldloca.s 1
0x22688  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2268d  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x22692  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x22697  ldloc.0
0x22698  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x2269d  ldstr    aVer_0// "ver"
0x226a2  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_StaticFileVersionStamp()
0x226a7  stloc.1
0x226a8  ldloca.s 1
0x226aa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x226af  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x226b4  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x226b9  newobj   instance void Microsoft.Crm.Application.Components.UI.SharedScript::.ctor()
0x226be  dup
0x226bf  ldloc.0
0x226c0  callvirt instance string [mscorlib]System.Object::ToString()
0x226c5  callvirt instance void Microsoft.Crm.Application.Components.UI.SharedScript::set_Url(string value)
0x226ca  dup
0x226cb  ldstr    aFunctionHostHo// "function(host){host.LoadScriptResx(wind"...
0x226d0  callvirt instance void Microsoft.Crm.Application.Components.UI.SharedScript::set_ImportJavaScript(string value)
0x226d5  ret
```
