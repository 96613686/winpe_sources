# Microsoft.Crm.Setup.Common.OnlinePackageSupport.TokenValueMap::<ReplaceTokens>b__2_0

- ea: `0x16d10`
- end: `0x16d4b`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.TokenValueMap::<ReplaceTokens>b__2_0`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x16d10`

## string_xrefs

- `0x16d2f`: `Token {0} not found in TokenValueMap`

## pseudocode

```c

```

## disassembly

```asm
0x16d10  ldarg.1
0x16d11  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x16d16  ldc.i4.1
0x16d17  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(int32)
0x16d1c  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x16d21  stloc.0
0x16d22  ldnull
0x16d23  stloc.1
0x16d24  ldarg.0
0x16d25  ldloc.0
0x16d26  ldloca.s 1
0x16d28  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x16d2d  brtrue.s loc_16D49
0x16d2f  ldstr    aToken0NotFound// "Token {0} not found in TokenValueMap"
0x16d34  ldc.i4.1
0x16d35  newarr   [mscorlib]System.Object
0x16d3a  dup
0x16d3b  ldc.i4.0
0x16d3c  ldloc.0
0x16d3d  stelem.ref
0x16d3e  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x16d43  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x16d48  throw
0x16d49  ldloc.1
0x16d4a  ret
```
