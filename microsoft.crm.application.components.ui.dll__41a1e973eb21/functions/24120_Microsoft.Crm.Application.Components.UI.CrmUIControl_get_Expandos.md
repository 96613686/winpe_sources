# Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos

- ea: `0x24120`
- end: `0x241b7`
- name: `Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos`
- size: `151`
- prototype: ``
- caller_count: `24`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14720`
- `0x15210`
- `0x15680`
- `0x160c0`
- `0x16b50`
- `0x171a0`
- `0x17a60`
- `0x18e00`
- `0x19550`
- `0x1a410`
- `0x1a610`
- `0x1a780`
- `0x1ec60`
- `0x1f810`
- `0x204e0`
- `0x20a80`
- `0x20de0`
- `0x21530`
- `0x21970`
- `0x22ac0`
- `0x22fc0`
- `0x25f10`
- `0x26290`
- `0x26880`

## callees

- `0x24120`

## pseudocode

```c

```

## disassembly

```asm
0x24120  ldarg.0
0x24121  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.UI.CrmUIControl::_expandos
0x24126  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Count()
0x2412b  brtrue.s loc_24133
0x2412d  ldsfld   string [mscorlib]System.String::Empty
0x24132  ret
0x24133  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x24138  stloc.0
0x24139  ldarg.0
0x2413a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.UI.CrmUIControl::_expandos
0x2413f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Keys()
0x24144  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, string>::GetEnumerator()
0x24149  stloc.1
0x2414a  br.s     loc_24197
0x2414c  ldloca.s 1
0x2414e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::get_Current()
0x24153  stloc.2
0x24154  ldloc.0
0x24155  ldc.i4.s 0x20
0x24157  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x2415c  pop
0x2415d  ldloc.0
0x2415e  ldloc.2
0x2415f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x24164  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x24169  pop
0x2416a  ldloc.0
0x2416b  ldstr    asc_5C7C0// "=\""
0x24170  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x24175  pop
0x24176  ldloc.0
0x24177  ldarg.0
0x24178  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.UI.CrmUIControl::_expandos
0x2417d  ldloc.2
0x2417e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x24183  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x24188  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2418d  pop
0x2418e  ldloc.0
0x2418f  ldc.i4.s 0x22
0x24191  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x24196  pop
0x24197  ldloca.s 1
0x24199  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::MoveNext()
0x2419e  brtrue.s loc_2414C
0x241a0  leave.s  loc_241B0
0x241a2  ldloca.s 1
0x241a4  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>
0x241aa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x241af  endfinally
0x241b0  ldloc.0
0x241b1  callvirt instance string [mscorlib]System.Object::ToString()
0x241b6  ret
```
