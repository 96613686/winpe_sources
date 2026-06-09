# Microsoft.Crm.SpreadsheetMLMetadata::SetNewValueIndexToOldValueIndexDictionary

- ea: `0x24260`
- end: `0x2431b`
- name: `Microsoft.Crm.SpreadsheetMLMetadata::SetNewValueIndexToOldValueIndexDictionary`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x24180`

## callees

- `0x24260`

## string_xrefs

- `0x24297`: `each of the values in this comma separated list should be a valid integer`

## pseudocode

```c

```

## disassembly

```asm
0x24260  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x24265  stloc.0
0x24266  ldarg.1
0x24267  ldstr    asc_6B1E0// ","
0x2426c  call     string[] [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::Split(string, string)
0x24271  stloc.1
0x24272  ldc.i4.0
0x24273  stloc.2
0x24274  br.s     loc_242C8
0x24276  ldloc.1
0x24277  ldloc.2
0x24278  ldelem.ref
0x24279  stloc.3
0x2427a  ldloc.3
0x2427b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x24280  brtrue.s loc_242C4
0x24282  ldloc.3
0x24283  ldc.i4   0x1FF
0x24288  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2428d  ldloca.s 4
0x2428f  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0x24294  brtrue.s loc_242A1
0x24296  ldc.i4.0
0x24297  ldstr    aEachOfTheValue// "each of the values in this comma separa"...
0x2429c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x242a1  ldloc.0
0x242a2  ldloc.s  4
0x242a4  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<int32>::Contains(var<u1>)
0x242a9  brfalse.s loc_242BC
0x242ab  ldc.i4   0x8004F601
0x242b0  ldc.i4.0
0x242b1  newarr   [mscorlib]System.Object
0x242b6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x242bb  throw
0x242bc  ldloc.0
0x242bd  ldloc.s  4
0x242bf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x242c4  ldloc.2
0x242c5  ldc.i4.1
0x242c6  add
0x242c7  stloc.2
0x242c8  ldloc.2
0x242c9  ldloc.1
0x242ca  ldlen
0x242cb  conv.i4
0x242cc  blt.s    loc_24276
0x242ce  ldc.i4.0
0x242cf  stloc.s  5
0x242d1  br.s     loc_242FE
0x242d3  ldloc.0
0x242d4  ldloc.s  5
0x242d6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<int32>::get_Item(!!T0)
0x242db  stloc.s  6
0x242dd  ldloc.0
0x242de  ldloc.s  5
0x242e0  ldc.i4.1
0x242e1  add
0x242e2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<int32>::get_Item(!!T0)
0x242e7  stloc.s  7
0x242e9  ldarg.0
0x242ea  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.SpreadsheetMLMetadata::_newValueIndexToOldValueIndexDictionary
0x242ef  ldloc.s  6
0x242f1  ldloc.s  7
0x242f3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::Add(var<u1>, !!T0)
0x242f8  ldloc.s  5
0x242fa  ldc.i4.2
0x242fb  add
0x242fc  stloc.s  5
0x242fe  ldloc.s  5
0x24300  ldloc.0
0x24301  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0x24306  blt.s    loc_242D3
0x24308  leave.s  loc_2431A
0x2430a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2430f  ldc.i4   0x8004F601
0x24314  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x24319  throw
0x2431a  ret
```
