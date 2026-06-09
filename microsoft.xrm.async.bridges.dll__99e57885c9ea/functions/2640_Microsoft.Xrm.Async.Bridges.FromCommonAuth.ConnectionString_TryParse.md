# Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::TryParse

- ea: `0x2640`
- end: `0x2760`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::TryParse`
- size: `288`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2620`
- `0x2850`

## callees

- `0x2640`
- `0x2800`

## pseudocode

```c

```

## disassembly

```asm
0x2640  ldarg.0
0x2641  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2646  brfalse.s loc_2653
0x2648  ldstr    aConnectionstri_0// "connectionString"
0x264d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2652  throw
0x2653  ldsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::PropertyRegularExpression
0x2658  ldarg.0
0x2659  callvirt instance class [System]System.Text.RegularExpressions.MatchCollection [System]System.Text.RegularExpressions.Regex::Matches(string)
0x265e  stloc.0
0x265f  ldloc.0
0x2660  callvirt instance int32 [System]System.Text.RegularExpressions.MatchCollection::get_Count()
0x2665  brtrue.s loc_266C
0x2667  ldarg.1
0x2668  ldnull
0x2669  stind.ref
0x266a  ldc.i4.0
0x266b  ret
0x266c  ldarg.1
0x266d  newobj   instance void Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::.ctor()
0x2672  stind.ref
0x2673  ldloc.0
0x2674  call     T0x2B00006A
0x2679  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System]System.Text.RegularExpressions.Match>::GetEnumerator()
0x267e  stloc.1
0x267f  br       loc_2747
0x2684  ldloc.1
0x2685  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System]System.Text.RegularExpressions.Match>::get_Current()
0x268a  dup
0x268b  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x2690  ldstr    aKey// "key"
0x2695  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x269a  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x269f  stloc.2
0x26a0  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x26a5  ldstr    aValue// "value"
0x26aa  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x26af  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x26b4  stloc.3
0x26b5  ldloc.3
0x26b6  ldstr    asc_5698// "'"
0x26bb  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x26c0  brfalse.s loc_26F7
0x26c2  ldloc.3
0x26c3  ldstr    asc_5698// "'"
0x26c8  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x26cd  brfalse.s loc_26F7
0x26cf  ldloc.3
0x26d0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x26d5  ldc.i4.2
0x26d6  ble.s    loc_26F7
0x26d8  ldloc.3
0x26d9  ldc.i4.1
0x26da  ldloc.3
0x26db  callvirt instance int32 [mscorlib]System.String::get_Length()
0x26e0  ldc.i4.2
0x26e1  sub
0x26e2  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x26e7  ldstr    asc_569C// "\\'"
0x26ec  ldstr    asc_5698// "'"
0x26f1  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x26f6  stloc.3
0x26f7  ldloc.3
0x26f8  ldstr    asc_56A2// "\""
0x26fd  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x2702  brfalse.s loc_2739
0x2704  ldloc.3
0x2705  ldstr    asc_56A2// "\""
0x270a  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x270f  brfalse.s loc_2739
0x2711  ldloc.3
0x2712  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2717  ldc.i4.2
0x2718  ble.s    loc_2739
0x271a  ldloc.3
0x271b  ldc.i4.1
0x271c  ldloc.3
0x271d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2722  ldc.i4.2
0x2723  sub
0x2724  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x2729  ldstr    asc_56A6// "\\\""
0x272e  ldstr    asc_56A2// "\""
0x2733  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x2738  stloc.3
0x2739  ldarg.1
0x273a  ldind.ref
0x273b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::properties
0x2740  ldloc.2
0x2741  ldloc.3
0x2742  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2747  ldloc.1
0x2748  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x274d  brtrue   loc_2684
0x2752  leave.s  loc_275E
0x2754  ldloc.1
0x2755  brfalse.s loc_275D
0x2757  ldloc.1
0x2758  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x275d  endfinally
0x275e  ldc.i4.1
0x275f  ret
```
