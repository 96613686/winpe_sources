# Microsoft.Xrm.Sdk.Linq.FilterExpressionExtensions::ForSubtreePostorder_0

- ea: `0xa4d0`
- end: `0xa510`
- name: `Microsoft.Xrm.Sdk.Linq.FilterExpressionExtensions::ForSubtreePostorder_0`
- size: `64`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xa4c0`
- `0xa4d0`
- `0xa520`

## callees

- `0x9170`
- `0xa4d0`
- `0x22290`

## pseudocode

```c

```

## disassembly

```asm
0xa4d0  ldarg.0
0xa4d1  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Query.FilterExpression> Microsoft.Xrm.Sdk.Query.FilterExpression::get_Filters()
0xa4d6  brfalse.s loc_A507
0xa4d8  ldarg.0
0xa4d9  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Query.FilterExpression> Microsoft.Xrm.Sdk.Query.FilterExpression::get_Filters()
0xa4de  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Xrm.Sdk.Query.FilterExpression>::GetEnumerator()
0xa4e3  stloc.0
0xa4e4  br.s     loc_A4F3
0xa4e6  ldloc.0
0xa4e7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.Query.FilterExpression>::get_Current()
0xa4ec  ldarg.0
0xa4ed  ldarg.2
0xa4ee  call     void Microsoft.Xrm.Sdk.Linq.FilterExpressionExtensions::ForSubtreePostorder(class Microsoft.Xrm.Sdk.Query.FilterExpression exp, class Microsoft.Xrm.Sdk.Query.FilterExpression parent, class FilterAction action)
0xa4f3  ldloc.0
0xa4f4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa4f9  brtrue.s loc_A4E6
0xa4fb  leave.s  loc_A507
0xa4fd  ldloc.0
0xa4fe  brfalse.s loc_A506
0xa500  ldloc.0
0xa501  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa506  endfinally
0xa507  ldarg.2
0xa508  ldarg.0
0xa509  ldarg.1
0xa50a  callvirt instance void FilterAction::Invoke(class Microsoft.Xrm.Sdk.Query.FilterExpression exp, class Microsoft.Xrm.Sdk.Query.FilterExpression parent)
0xa50f  ret
```
