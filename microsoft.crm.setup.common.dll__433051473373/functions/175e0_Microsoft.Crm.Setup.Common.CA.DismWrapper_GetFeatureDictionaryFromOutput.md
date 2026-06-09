# Microsoft.Crm.Setup.Common.CA.DismWrapper::GetFeatureDictionaryFromOutput

- ea: `0x175e0`
- end: `0x17697`
- name: `Microsoft.Crm.Setup.Common.CA.DismWrapper::GetFeatureDictionaryFromOutput`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x17160`

## callees

- `0x175e0`

## string_xrefs

- `0x17625`: `featureName`
- `0x175f9`: `Feature Name :\s+(?<featureName>.*)\r\nState :\s+(?<state>.*)\r\n`

## pseudocode

```c

```

## disassembly

```asm
0x175e0  ldarg.1
0x175e1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x175e6  brfalse.s loc_175F3
0x175e8  ldstr    aFeatures// "features"
0x175ed  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x175f2  throw
0x175f3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::.ctor()
0x175f8  stloc.0
0x175f9  ldstr    aFeatureNameSFe_0// "Feature Name :\\s+(?<featureName>.*)\\r"...
0x175fe  ldc.i4.s 0xA
0x17600  call     class [System]System.Text.RegularExpressions.Regex [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::GetRegex(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x17605  ldarg.1
0x17606  callvirt instance class [System]System.Text.RegularExpressions.MatchCollection [System]System.Text.RegularExpressions.Regex::Matches(string)
0x1760b  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.Text.RegularExpressions.MatchCollection::GetEnumerator()
0x17610  stloc.1
0x17611  br.s     loc_17677
0x17613  ldloc.1
0x17614  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x17619  castclass [System]System.Text.RegularExpressions.Match
0x1761e  stloc.2
0x1761f  ldloc.2
0x17620  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x17625  ldstr    aFeaturename// "featureName"
0x1762a  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x1762f  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x17634  stloc.3
0x17635  ldstr    aEnabled// "Enabled"
0x1763a  ldloc.2
0x1763b  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x17640  ldstr    aState// "state"
0x17645  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x1764a  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x1764f  ldc.i4.5
0x17650  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x17655  stloc.s  4
0x17657  ldloc.3
0x17658  ldstr    asc_265CA// " "
0x1765d  ldloca.s 4
0x1765f  call     instance string [mscorlib]System.Boolean::ToString()
0x17664  call     string [mscorlib]System.String::Concat(string, string, string)
0x17669  call     void [mscorlib]System.Console::WriteLine(string)
0x1766e  ldloc.0
0x1766f  ldloc.3
0x17670  ldloc.s  4
0x17672  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Add(var<u1>, !!T0)
0x17677  ldloc.1
0x17678  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1767d  brtrue.s loc_17613
0x1767f  leave.s  loc_17695
0x17681  ldloc.1
0x17682  isinst   [mscorlib]System.IDisposable
0x17687  stloc.s  5
0x17689  ldloc.s  5
0x1768b  brfalse.s loc_17694
0x1768d  ldloc.s  5
0x1768f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17694  endfinally
0x17695  ldloc.0
0x17696  ret
```
