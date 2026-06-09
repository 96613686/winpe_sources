# Microsoft.Xrm.Sdk.Linq.FilterExpressionExtensions::ForSubtreePreorder_0

- ea: `0xa440`
- end: `0xa480`
- name: `Microsoft.Xrm.Sdk.Linq.FilterExpressionExtensions::ForSubtreePreorder_0`
- size: `64`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xa430`
- `0xa440`
- `0xa490`

## callees

- `0x9170`
- `0xa440`
- `0x22290`

## pseudocode

```c

```

## disassembly

```asm
0xa440  ldarg.2
0xa441  ldarg.0
0xa442  ldarg.1
0xa443  callvirt instance void FilterAction::Invoke(class Microsoft.Xrm.Sdk.Query.FilterExpression exp, class Microsoft.Xrm.Sdk.Query.FilterExpression parent)
0xa448  ldarg.0
0xa449  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Query.FilterExpression> Microsoft.Xrm.Sdk.Query.FilterExpression::get_Filters()
0xa44e  brfalse.s loc_A47F
0xa450  ldarg.0
0xa451  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Query.FilterExpression> Microsoft.Xrm.Sdk.Query.FilterExpression::get_Filters()
0xa456  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Xrm.Sdk.Query.FilterExpression>::GetEnumerator()
0xa45b  stloc.0
0xa45c  br.s     loc_A46B
0xa45e  ldloc.0
0xa45f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.Query.FilterExpression>::get_Current()
0xa464  ldarg.0
0xa465  ldarg.2
0xa466  call     void Microsoft.Xrm.Sdk.Linq.FilterExpressionExtensions::ForSubtreePreorder(class Microsoft.Xrm.Sdk.Query.FilterExpression exp, class Microsoft.Xrm.Sdk.Query.FilterExpression parent, class FilterAction action)
0xa46b  ldloc.0
0xa46c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa471  brtrue.s loc_A45E
0xa473  leave.s  loc_A47F
0xa475  ldloc.0
0xa476  brfalse.s loc_A47E
0xa478  ldloc.0
0xa479  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa47e  endfinally
0xa47f  ret
```
