# Microsoft.Crm.Controls.PageResourceManager::WriteLoadAllScriptIncludesFunction

- ea: `0x66f0`
- end: `0x6834`
- name: `Microsoft.Crm.Controls.PageResourceManager::WriteLoadAllScriptIncludesFunction`
- size: `324`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x68b0`
- `0x68d0`

## callees

- `0x22a0`
- `0x2360`
- `0x2380`
- `0x24a0`
- `0x24f0`
- `0x6400`
- `0x6430`
- `0x66f0`
- `0x6840`
- `0x6a40`

## pseudocode

```c

```

## disassembly

```asm
0x66f0  ldarg.2
0x66f1  brfalse.s loc_66FB
0x66f3  ldarg.2
0x66f4  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Count()
0x66f9  brtrue.s loc_6711
0x66fb  ldarg.0
0x66fc  call     instance string Microsoft.Crm.Controls.PageResourceManager::get_ApplicationInitStatements()
0x6701  brfalse.s loc_6710
0x6703  ldarg.0
0x6704  call     instance string Microsoft.Crm.Controls.PageResourceManager::get_ApplicationInitStatements()
0x6709  call     T0x2B00000E
0x670e  brtrue.s loc_6711
0x6710  ret
0x6711  ldsfld   string [mscorlib]System.String::Empty
0x6716  stloc.0
0x6717  ldarg.0
0x6718  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_LoadRefreshFormInit()
0x671d  brfalse  loc_67C6
0x6722  ldarg.0
0x6723  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Controls.PageResourceManager::scriptReferences
0x6728  ldarg.2
0x6729  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Keys()
0x672e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x6733  ldarg.0
0x6734  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetJSBlockForScriptReferences()
0x6739  stloc.0
0x673a  ldarg.1
0x673b  ldstr    aScript_1// "<script>"
0x6740  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6745  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x674a  stloc.1
0x674b  ldarg.2
0x674c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Values()
0x6751  call     T0x2B00000F
0x6756  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::GetEnumerator()
0x675b  stloc.2
0x675c  br.s     loc_6772
0x675e  ldloca.s 2
0x6760  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Current()
0x6765  stloc.3
0x6766  ldloc.1
0x6767  ldloc.3
0x6768  callvirt instance string [mscorlib]System.Object::ToString()
0x676d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6772  ldloca.s 2
0x6774  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::MoveNext()
0x6779  brtrue.s loc_675E
0x677b  leave.s  loc_678B
0x677d  ldloca.s 2
0x677f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>
0x6785  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x678a  endfinally
0x678b  ldarg.1
0x678c  ldstr    aVarPagescripti// "var PageScriptIncludes = {0}; "
0x6791  ldloc.1
0x6792  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x6797  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x679c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x67a1  ldarg.0
0x67a2  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Controls.PageResourceManager::get_ApplicationInitStatementsList()
0x67a7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x67ac  brfalse.s loc_6821
0x67ae  ldarg.1
0x67af  ldstr    aVarPageapplica// "var PageApplicationInitStatements = {0}"...
0x67b4  ldarg.0
0x67b5  call     instance string Microsoft.Crm.Controls.PageResourceManager::get_ApplicationInitStatements()
0x67ba  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x67bf  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x67c4  br.s     loc_6821
0x67c6  ldarg.0
0x67c7  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_HelpContext()
0x67cc  brtrue.s loc_67D6
0x67ce  ldarg.0
0x67cf  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_UseBundling()
0x67d4  brtrue.s loc_67EB
0x67d6  ldarg.0
0x67d7  ldarg.1
0x67d8  ldarg.2
0x67d9  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Values()
0x67de  ldstr    aScriptTypeText_1// "<script type=\"text/javascript\" src=\""...
0x67e3  ldarg.3
0x67e4  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteList(class [mscorlib]System.IO.TextWriter output, class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> list, string mask, class EncodingFunction encodingFunction)
0x67e9  br.s     loc_67F9
0x67eb  ldarg.0
0x67ec  ldarg.1
0x67ed  ldarg.2
0x67ee  ldstr    aScriptTypeText_1// "<script type=\"text/javascript\" src=\""...
0x67f3  ldarg.3
0x67f4  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteListBundled(class [mscorlib]System.IO.TextWriter output, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> list, string mask, class EncodingFunction encodingFunction)
0x67f9  ldarg.1
0x67fa  ldstr    aScript_1// "<script>"
0x67ff  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6804  ldarg.1
0x6805  ldstr    aSysApplication// "Sys.Application.add_init("
0x680a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x680f  ldarg.0
0x6810  ldarg.1
0x6811  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteApplicationInit(class [mscorlib]System.IO.TextWriter output)
0x6816  ldarg.1
0x6817  ldstr    asc_3BBA2// ");"
0x681c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6821  ldarg.1
0x6822  ldloc.0
0x6823  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6828  ldarg.1
0x6829  ldstr    aScript// "</script>"
0x682e  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x6833  ret
```
