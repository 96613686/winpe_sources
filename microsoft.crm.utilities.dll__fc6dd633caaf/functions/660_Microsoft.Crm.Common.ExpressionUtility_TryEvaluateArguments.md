# Microsoft.Crm.Common.ExpressionUtility::TryEvaluateArguments

- ea: `0x660`
- end: `0x6a3`
- name: `Microsoft.Crm.Common.ExpressionUtility::TryEvaluateArguments`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4a0`

## callees

- `0x4a0`
- `0x660`

## pseudocode

```c

```

## disassembly

```asm
0x660  ldarg.1
0x661  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<object>::.ctor()
0x666  stind.ref
0x667  ldarg.0
0x668  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.Expression>::GetEnumerator()
0x66d  stloc.0
0x66e  br.s     loc_68B
0x670  ldloc.0
0x671  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression>::get_Current()
0x676  ldloca.s 1
0x678  call     bool Microsoft.Crm.Common.ExpressionUtility::TryEvaluateExpressionFast(class [System.Core]System.Linq.Expressions.Expression expression, [out] object& result)
0x67d  brtrue.s loc_683
0x67f  ldc.i4.0
0x680  stloc.2
0x681  leave.s  loc_6A1
0x683  ldarg.1
0x684  ldind.ref
0x685  ldloc.1
0x686  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0x68b  ldloc.0
0x68c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x691  brtrue.s loc_670
0x693  leave.s  loc_69F
0x695  ldloc.0
0x696  brfalse.s loc_69E
0x698  ldloc.0
0x699  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69e  endfinally
0x69f  ldc.i4.1
0x6a0  ret
0x6a1  ldloc.2
0x6a2  ret
```
