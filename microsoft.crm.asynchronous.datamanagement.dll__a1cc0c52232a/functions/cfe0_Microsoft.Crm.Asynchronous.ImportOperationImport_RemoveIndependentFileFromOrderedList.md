# Microsoft.Crm.Asynchronous.ImportOperationImport::RemoveIndependentFileFromOrderedList

- ea: `0xcfe0`
- end: `0xd035`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImport::RemoveIndependentFileFromOrderedList`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xc5a0`
- `0xd4b0`

## callees

- `0xcfe0`

## pseudocode

```c

```

## disassembly

```asm
0xcfe0  ldarg.1
0xcfe1  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Values()
0xcfe6  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::GetEnumerator()
0xcfeb  stloc.0
0xcfec  br.s     loc_D00A
0xcfee  ldloca.s 0
0xcff0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Current()
0xcff5  stloc.1
0xcff6  ldloc.1
0xcff7  brfalse.s loc_D00A
0xcff9  ldloc.1
0xcffa  ldarg.2
0xcffb  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0xd000  brfalse.s loc_D00A
0xd002  ldloc.1
0xd003  ldarg.2
0xd004  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Remove(var<u1>)
0xd009  pop
0xd00a  ldloca.s 0
0xd00c  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::MoveNext()
0xd011  brtrue.s loc_CFEE
0xd013  leave.s  loc_D023
0xd015  ldloca.s 0
0xd017  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>
0xd01d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd022  endfinally
0xd023  ldarg.1
0xd024  ldarg.2
0xd025  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0xd02a  brfalse.s loc_D034
0xd02c  ldarg.1
0xd02d  ldarg.2
0xd02e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::Remove(var<u1>)
0xd033  pop
0xd034  ret
```
