# Microsoft.Crm.Controls.Header::EnableSystemCustomization

- ea: `0x79f0`
- end: `0x7a82`
- name: `Microsoft.Crm.Controls.Header::EnableSystemCustomization`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x79c0`

## callees

- `0x79f0`

## string_xrefs

- `0x7a08`: `/_static/tools/solution/scripts/solutioncomponentlist.js`

## pseudocode

```c

```

## disassembly

```asm
0x79f0  ldarg.0
0x79f1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_scripts
0x79f6  ldstr    aStaticToolsSys// "/_static/tools/systemcustomization/scri"...
0x79fb  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::ContainsKey(var<u1>)
0x7a00  brtrue.s loc_7A38
0x7a02  ldarg.0
0x7a03  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_scripts
0x7a08  ldstr    aStaticToolsSol// "/_static/tools/solution/scripts/solutio"...
0x7a0d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::ContainsKey(var<u1>)
0x7a12  brtrue.s loc_7A38
0x7a14  ldarg.0
0x7a15  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_scripts
0x7a1a  ldstr    aStaticGridCmds// "/_static/_grid/cmds/multiaction.js"
0x7a1f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::ContainsKey(var<u1>)
0x7a24  brtrue.s loc_7A38
0x7a26  ldarg.0
0x7a27  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_scripts
0x7a2c  ldstr    aStaticGridGrid// "/_static/_grid/gridcontrolforoutlook.js"
0x7a31  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::ContainsKey(var<u1>)
0x7a36  brfalse.s loc_7A3A
0x7a38  ldc.i4.1
0x7a39  ret
0x7a3a  ldarg.0
0x7a3b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_scripts
0x7a40  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Keys()
0x7a45  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::GetEnumerator()
0x7a4a  stloc.0
0x7a4b  br.s     loc_7A65
0x7a4d  ldloca.s 0
0x7a4f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Current()
0x7a54  ldstr    aStaticTools// "/_static/tools"
0x7a59  ldc.i4.4
0x7a5a  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x7a5f  brfalse.s loc_7A65
0x7a61  ldc.i4.1
0x7a62  stloc.1
0x7a63  leave.s  loc_7A80
0x7a65  ldloca.s 0
0x7a67  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::MoveNext()
0x7a6c  brtrue.s loc_7A4D
0x7a6e  leave.s  loc_7A7E
0x7a70  ldloca.s 0
0x7a72  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>
0x7a78  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7a7d  endfinally
0x7a7e  ldc.i4.0
0x7a7f  ret
0x7a80  ldloc.1
0x7a81  ret
```
