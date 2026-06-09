# Microsoft.Crm.Controls.ScriptResource::get_ScriptResourceInclude

- ea: `0xa340`
- end: `0xa37e`
- name: `Microsoft.Crm.Controls.ScriptResource::get_ScriptResourceInclude`
- size: `62`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3ae0`
- `0x80a0`
- `0x8f00`

## string_xrefs

- `0xa340`: `/_common/ScriptResx.ashx`

## pseudocode

```c

```

## disassembly

```asm
0xa340  ldstr    aCommonScriptre_0// "/_common/ScriptResx.ashx"
0xa345  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa34a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa34f  dup
0xa350  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xa355  ldstr    aLcid// "lcid"
0xa35a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xa35f  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xa364  stloc.0
0xa365  ldloca.s 0
0xa367  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa36c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa371  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa376  dup
0xa377  ldc.i4.1
0xa378  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_UseVersionStamp(bool)
0xa37d  ret
```
