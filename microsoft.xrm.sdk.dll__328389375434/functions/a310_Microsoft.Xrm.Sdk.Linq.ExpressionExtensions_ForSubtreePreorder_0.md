# Microsoft.Xrm.Sdk.Linq.ExpressionExtensions::ForSubtreePreorder_0

- ea: `0xa310`
- end: `0xa348`
- name: `Microsoft.Xrm.Sdk.Linq.ExpressionExtensions::ForSubtreePreorder_0`
- size: `56`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xa300`
- `0xa310`

## callees

- `0xa310`
- `0xa350`
- `0x210b0`

## pseudocode

```c

```

## disassembly

```asm
0xa310  ldarg.2
0xa311  ldarg.0
0xa312  ldarg.1
0xa313  callvirt instance void ExpressionAction::Invoke(class [System.Core]System.Linq.Expressions.Expression exp, class [System.Core]System.Linq.Expressions.Expression parent)
0xa318  ldarg.0
0xa319  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.Expression> Microsoft.Xrm.Sdk.Linq.ExpressionExtensions::GetChildren(class [System.Core]System.Linq.Expressions.Expression exp)
0xa31e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.Expression>::GetEnumerator()
0xa323  stloc.0
0xa324  br.s     loc_A333
0xa326  ldloc.0
0xa327  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression>::get_Current()
0xa32c  ldarg.0
0xa32d  ldarg.2
0xa32e  call     void Microsoft.Xrm.Sdk.Linq.ExpressionExtensions::ForSubtreePreorder(class [System.Core]System.Linq.Expressions.Expression exp, class [System.Core]System.Linq.Expressions.Expression parent, class ExpressionAction action)
0xa333  ldloc.0
0xa334  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa339  brtrue.s loc_A326
0xa33b  leave.s  loc_A347
0xa33d  ldloc.0
0xa33e  brfalse.s loc_A346
0xa340  ldloc.0
0xa341  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa346  endfinally
0xa347  ret
```
