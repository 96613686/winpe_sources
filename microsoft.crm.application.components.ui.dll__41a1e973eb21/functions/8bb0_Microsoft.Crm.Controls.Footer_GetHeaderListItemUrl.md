# Microsoft.Crm.Controls.Footer::GetHeaderListItemUrl

- ea: `0x8bb0`
- end: `0x8c5c`
- name: `Microsoft.Crm.Controls.Footer::GetHeaderListItemUrl`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x8f00`

## callees

- `0x2360`
- `0x8bb0`

## string_xrefs

- `0x8c24`: `/help/common/`

## pseudocode

```c

```

## disassembly

```asm
0x8bb0  ldstr    asc_3280A// ""
0x8bb5  stloc.0
0x8bb6  ldarg.0
0x8bb7  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_HelpContext()
0x8bbc  brfalse  loc_8C4E
0x8bc1  ldarg.1
0x8bc2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x8bc7  ldstr    aAspx// ".aspx"
0x8bcc  ldc.i4.5
0x8bcd  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x8bd2  brtrue.s loc_8C0D
0x8bd4  ldarg.1
0x8bd5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x8bda  ldstr    aJs// ".js"
0x8bdf  ldc.i4.5
0x8be0  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x8be5  brtrue.s loc_8C0D
0x8be7  ldarg.1
0x8be8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x8bed  ldstr    aCss// ".css"
0x8bf2  ldc.i4.5
0x8bf3  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x8bf8  brtrue.s loc_8C0D
0x8bfa  ldarg.1
0x8bfb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x8c00  ldstr    aAshx// ".ashx"
0x8c05  ldc.i4.5
0x8c06  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x8c0b  brfalse.s loc_8C4E
0x8c0d  ldarg.1
0x8c0e  callvirt instance string [mscorlib]System.Object::ToString()
0x8c13  ldc.i4.1
0x8c14  newarr   [mscorlib]System.Char
0x8c19  dup
0x8c1a  ldc.i4.0
0x8c1b  ldc.i4.s 0x2F
0x8c1d  stelem.i2
0x8c1e  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x8c23  stloc.1
0x8c24  ldstr    aHelpCommon// "/help/common/"
0x8c29  ldloc.1
0x8c2a  ldloc.1
0x8c2b  ldlen
0x8c2c  conv.i4
0x8c2d  ldc.i4.1
0x8c2e  sub
0x8c2f  ldelem.ref
0x8c30  call     string [mscorlib]System.String::Concat(string, string)
0x8c35  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8c3a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8c3f  dup
0x8c40  ldc.i4.0
0x8c41  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_UseOrganizationName(bool)
0x8c46  callvirt instance string [mscorlib]System.Object::ToString()
0x8c4b  stloc.0
0x8c4c  br.s     loc_8C55
0x8c4e  ldarg.1
0x8c4f  callvirt instance string [mscorlib]System.Object::ToString()
0x8c54  stloc.0
0x8c55  ldloc.0
0x8c56  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x8c5b  ret
```
