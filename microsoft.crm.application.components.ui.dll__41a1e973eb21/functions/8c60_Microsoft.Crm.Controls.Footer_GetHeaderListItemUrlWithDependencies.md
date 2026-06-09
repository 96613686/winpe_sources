# Microsoft.Crm.Controls.Footer::GetHeaderListItemUrlWithDependencies

- ea: `0x8c60`
- end: `0x8d72`
- name: `Microsoft.Crm.Controls.Footer::GetHeaderListItemUrlWithDependencies`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x8f00`

## callees

- `0x2360`
- `0x6520`
- `0x8c60`

## string_xrefs

- `0x8cd4`: `/help/common/`

## pseudocode

```c

```

## disassembly

```asm
0x8c60  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x8c65  stloc.0
0x8c66  ldarg.0
0x8c67  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_HelpContext()
0x8c6c  brfalse  loc_8D0A
0x8c71  ldarg.1
0x8c72  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x8c77  ldstr    aAspx// ".aspx"
0x8c7c  ldc.i4.5
0x8c7d  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x8c82  brtrue.s loc_8CBD
0x8c84  ldarg.1
0x8c85  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x8c8a  ldstr    aJs// ".js"
0x8c8f  ldc.i4.5
0x8c90  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x8c95  brtrue.s loc_8CBD
0x8c97  ldarg.1
0x8c98  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x8c9d  ldstr    aCss// ".css"
0x8ca2  ldc.i4.5
0x8ca3  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x8ca8  brtrue.s loc_8CBD
0x8caa  ldarg.1
0x8cab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x8cb0  ldstr    aAshx// ".ashx"
0x8cb5  ldc.i4.5
0x8cb6  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x8cbb  brfalse.s loc_8D0A
0x8cbd  ldarg.1
0x8cbe  callvirt instance string [mscorlib]System.Object::ToString()
0x8cc3  ldc.i4.1
0x8cc4  newarr   [mscorlib]System.Char
0x8cc9  dup
0x8cca  ldc.i4.0
0x8ccb  ldc.i4.s 0x2F
0x8ccd  stelem.i2
0x8cce  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x8cd3  stloc.1
0x8cd4  ldstr    aHelpCommon// "/help/common/"
0x8cd9  ldloc.1
0x8cda  ldloc.1
0x8cdb  ldlen
0x8cdc  conv.i4
0x8cdd  ldc.i4.1
0x8cde  sub
0x8cdf  ldelem.ref
0x8ce0  call     string [mscorlib]System.String::Concat(string, string)
0x8ce5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8cea  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8cef  stloc.2
0x8cf0  ldloc.2
0x8cf1  ldc.i4.0
0x8cf2  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_UseOrganizationName(bool)
0x8cf7  ldloc.0
0x8cf8  ldloc.2
0x8cf9  callvirt instance string [mscorlib]System.Object::ToString()
0x8cfe  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x8d03  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8d08  br.s     loc_8D6B
0x8d0a  ldarg.0
0x8d0b  ldarg.1
0x8d0c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x8d11  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Controls.PageResourceManager::JsScriptBlockGetBundleUrlWithDependencies(string filename)
0x8d16  stloc.3
0x8d17  ldloc.3
0x8d18  brtrue.s loc_8D32
0x8d1a  ldloc.0
0x8d1b  ldarg.1
0x8d1c  callvirt instance string [mscorlib]System.Object::ToString()
0x8d21  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x8d26  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8d2b  ldloc.0
0x8d2c  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x8d31  ret
0x8d32  ldloc.3
0x8d33  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x8d38  stloc.s  4
0x8d3a  br.s     loc_8D52
0x8d3c  ldloca.s 4
0x8d3e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x8d43  stloc.s  5
0x8d45  ldloc.0
0x8d46  ldloc.s  5
0x8d48  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x8d4d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8d52  ldloca.s 4
0x8d54  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x8d59  brtrue.s loc_8D3C
0x8d5b  leave.s  loc_8D6B
0x8d5d  ldloca.s 4
0x8d5f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x8d65  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8d6a  endfinally
0x8d6b  ldloc.0
0x8d6c  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x8d71  ret
```
