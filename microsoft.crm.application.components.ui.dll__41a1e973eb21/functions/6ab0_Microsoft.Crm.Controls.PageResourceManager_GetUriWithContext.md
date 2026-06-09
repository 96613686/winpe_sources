# Microsoft.Crm.Controls.PageResourceManager::GetUriWithContext

- ea: `0x6ab0`
- end: `0x6b2f`
- name: `Microsoft.Crm.Controls.PageResourceManager::GetUriWithContext`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x65c0`
- `0x80a0`

## callees

- `0x2360`
- `0x6ab0`

## string_xrefs

- `0x6b0a`: `/help/common/`

## pseudocode

```c

```

## disassembly

```asm
0x6ab0  ldarg.1
0x6ab1  stloc.0
0x6ab2  ldarg.0
0x6ab3  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_HelpContext()
0x6ab8  brfalse.s loc_6B2D
0x6aba  ldarg.1
0x6abb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x6ac0  ldstr    aAspx// ".aspx"
0x6ac5  ldc.i4.5
0x6ac6  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x6acb  brtrue.s loc_6AF3
0x6acd  ldarg.1
0x6ace  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x6ad3  ldstr    aJs// ".js"
0x6ad8  ldc.i4.5
0x6ad9  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x6ade  brtrue.s loc_6AF3
0x6ae0  ldarg.1
0x6ae1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x6ae6  ldstr    aCss// ".css"
0x6aeb  ldc.i4.5
0x6aec  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x6af1  brfalse.s loc_6B2D
0x6af3  ldarg.1
0x6af4  callvirt instance string [mscorlib]System.Object::ToString()
0x6af9  ldc.i4.1
0x6afa  newarr   [mscorlib]System.Char
0x6aff  dup
0x6b00  ldc.i4.0
0x6b01  ldc.i4.s 0x2F
0x6b03  stelem.i2
0x6b04  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x6b09  stloc.1
0x6b0a  ldstr    aHelpCommon// "/help/common/"
0x6b0f  ldloc.1
0x6b10  ldloc.1
0x6b11  ldlen
0x6b12  conv.i4
0x6b13  ldc.i4.1
0x6b14  sub
0x6b15  ldelem.ref
0x6b16  call     string [mscorlib]System.String::Concat(string, string)
0x6b1b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6b20  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6b25  stloc.0
0x6b26  ldloc.0
0x6b27  ldc.i4.0
0x6b28  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_UseOrganizationName(bool)
0x6b2d  ldloc.0
0x6b2e  ret
```
