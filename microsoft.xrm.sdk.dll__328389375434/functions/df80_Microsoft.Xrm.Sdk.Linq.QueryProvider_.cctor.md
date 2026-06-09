# Microsoft.Xrm.Sdk.Linq.QueryProvider::.cctor

- ea: `0xdf80`
- end: `0xe345`
- name: `Microsoft.Xrm.Sdk.Linq.QueryProvider::.cctor`
- size: `965`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0xe220`: `Compare`

## pseudocode

```c

```

## disassembly

```asm
0xdf80  ldc.i4.1
0xdf81  newarr   [mscorlib]System.String
0xdf86  stsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingRoot
0xdf8b  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingRoot
0xdf90  ldc.i4.1
0xdf91  newarr   [mscorlib]System.String
0xdf96  dup
0xdf97  ldc.i4.0
0xdf98  ldstr    aTolist// "ToList"
0xdf9d  stelem.ref
0xdf9e  call     T0x2B000047
0xdfa3  stsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingFirst
0xdfa8  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingFirst
0xdfad  ldc.i4.6
0xdfae  newarr   [mscorlib]System.String
0xdfb3  dup
0xdfb4  ldc.i4.0
0xdfb5  ldstr    aSelect// "Select"
0xdfba  stelem.ref
0xdfbb  dup
0xdfbc  ldc.i4.1
0xdfbd  ldstr    aFirst_0// "First"
0xdfc2  stelem.ref
0xdfc3  dup
0xdfc4  ldc.i4.2
0xdfc5  ldstr    aFirstordefault// "FirstOrDefault"
0xdfca  stelem.ref
0xdfcb  dup
0xdfcc  ldc.i4.3
0xdfcd  ldstr    aSingle// "Single"
0xdfd2  stelem.ref
0xdfd3  dup
0xdfd4  ldc.i4.4
0xdfd5  ldstr    aSingleordefaul// "SingleOrDefault"
0xdfda  stelem.ref
0xdfdb  dup
0xdfdc  ldc.i4.5
0xdfdd  ldstr    aDistinct// "Distinct"
0xdfe2  stelem.ref
0xdfe3  call     T0x2B000047
0xdfe8  stsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingTake
0xdfed  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingTake
0xdff2  ldc.i4.1
0xdff3  newarr   [mscorlib]System.String
0xdff8  dup
0xdff9  ldc.i4.0
0xdffa  ldstr    aTake// "Take"
0xdfff  stelem.ref
0xe000  call     T0x2B000047
0xe005  stsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingSkip
0xe00a  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingSkip
0xe00f  ldc.i4.1
0xe010  newarr   [mscorlib]System.String
0xe015  dup
0xe016  ldc.i4.0
0xe017  ldstr    aSkip// "Skip"
0xe01c  stelem.ref
0xe01d  call     T0x2B000047
0xe022  stsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingSelect
0xe027  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingSelect
0xe02c  ldc.i4.6
0xe02d  newarr   [mscorlib]System.String
0xe032  dup
0xe033  ldc.i4.0
0xe034  ldstr    aSelect// "Select"
0xe039  stelem.ref
0xe03a  dup
0xe03b  ldc.i4.1
0xe03c  ldstr    aWhere// "Where"
0xe041  stelem.ref
0xe042  dup
0xe043  ldc.i4.2
0xe044  ldstr    aOrderby// "OrderBy"
0xe049  stelem.ref
0xe04a  dup
0xe04b  ldc.i4.3
0xe04c  ldstr    aOrderbydescend// "OrderByDescending"
0xe051  stelem.ref
0xe052  dup
0xe053  ldc.i4.4
0xe054  ldstr    aThenby// "ThenBy"
0xe059  stelem.ref
0xe05a  dup
0xe05b  ldc.i4.5
0xe05c  ldstr    aThenbydescendi// "ThenByDescending"
0xe061  stelem.ref
0xe062  call     T0x2B000047
0xe067  stsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingOrderBy
0xe06c  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingOrderBy
0xe071  ldc.i4.1
0xe072  newarr   [mscorlib]System.String
0xe077  dup
0xe078  ldc.i4.0
0xe079  ldstr    aSelectmany// "SelectMany"
0xe07e  stelem.ref
0xe07f  call     T0x2B000047
0xe084  stsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingWhere
0xe089  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingWhere
0xe08e  ldc.i4.1
0xe08f  newarr   [mscorlib]System.String
0xe094  dup
0xe095  ldc.i4.0
0xe096  ldstr    aJoin// "Join"
0xe09b  stelem.ref
0xe09c  call     T0x2B000047
0xe0a1  stsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingJoin
0xe0a6  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingRoot
0xe0ab  ldc.i4.1
0xe0ac  newarr   [mscorlib]System.String
0xe0b1  dup
0xe0b2  ldc.i4.0
0xe0b3  ldstr    aSelectmany// "SelectMany"
0xe0b8  stelem.ref
0xe0b9  call     T0x2B000047
0xe0be  stsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingGroupJoin
0xe0c3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::.ctor()
0xe0c8  stloc.0
0xe0c9  ldloc.0
0xe0ca  ldstr    aJoin// "Join"
0xe0cf  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingJoin
0xe0d4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::Add(var<u1>, !!T0)
0xe0d9  ldloc.0
0xe0da  ldstr    aGroupjoin// "GroupJoin"
0xe0df  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingGroupJoin
0xe0e4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::Add(var<u1>, !!T0)
0xe0e9  ldloc.0
0xe0ea  ldstr    aWhere// "Where"
0xe0ef  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingWhere
0xe0f4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::Add(var<u1>, !!T0)
0xe0f9  ldloc.0
0xe0fa  ldstr    aOrderby// "OrderBy"
0xe0ff  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingOrderBy
0xe104  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::Add(var<u1>, !!T0)
0xe109  ldloc.0
0xe10a  ldstr    aOrderbydescend// "OrderByDescending"
0xe10f  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingOrderBy
0xe114  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::Add(var<u1>, !!T0)
0xe119  ldloc.0
0xe11a  ldstr    aThenby// "ThenBy"
0xe11f  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingOrderBy
0xe124  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::Add(var<u1>, !!T0)
0xe129  ldloc.0
0xe12a  ldstr    aThenbydescendi// "ThenByDescending"
0xe12f  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingOrderBy
0xe134  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::Add(var<u1>, !!T0)
0xe139  ldloc.0
0xe13a  ldstr    aSelect// "Select"
0xe13f  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingSelect
0xe144  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::Add(var<u1>, !!T0)
0xe149  ldloc.0
0xe14a  ldstr    aSkip// "Skip"
0xe14f  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingSkip
0xe154  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::Add(var<u1>, !!T0)
0xe159  ldloc.0
0xe15a  ldstr    aTake// "Take"
0xe15f  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingTake
0xe164  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::Add(var<u1>, !!T0)
0xe169  ldloc.0
0xe16a  ldstr    aFirst_0// "First"
0xe16f  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingFirst
0xe174  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::Add(var<u1>, !!T0)
0xe179  ldloc.0
0xe17a  ldstr    aFirstordefault// "FirstOrDefault"
0xe17f  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingFirst
0xe184  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::Add(var<u1>, !!T0)
0xe189  ldloc.0
0xe18a  ldstr    aSingle// "Single"
0xe18f  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingFirst
0xe194  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::Add(var<u1>, !!T0)
0xe199  ldloc.0
0xe19a  ldstr    aSingleordefaul// "SingleOrDefault"
0xe19f  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingFirst
0xe1a4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::Add(var<u1>, !!T0)
0xe1a9  ldloc.0
0xe1aa  ldstr    aSelectmany// "SelectMany"
0xe1af  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingOrderBy
0xe1b4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::Add(var<u1>, !!T0)
0xe1b9  ldloc.0
0xe1ba  ldstr    aDistinct// "Distinct"
0xe1bf  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingSkip
0xe1c4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::Add(var<u1>, !!T0)
0xe1c9  ldloc.0
0xe1ca  ldstr    aCast// "Cast"
0xe1cf  ldc.i4.1
0xe1d0  newarr   [mscorlib]System.String
0xe1d5  dup
0xe1d6  ldc.i4.0
0xe1d7  ldstr    aSelect// "Select"
0xe1dc  stelem.ref
0xe1dd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::Add(var<u1>, !!T0)
0xe1e2  ldloc.0
0xe1e3  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> Microsoft.Xrm.Sdk.Linq.QueryProvider::_followingMethodLookup
0xe1e8  ldc.i4.4
0xe1e9  newarr   [mscorlib]System.String
0xe1ee  dup
0xe1ef  ldc.i4.0
0xe1f0  ldstr    aEquals// "Equals"
0xe1f5  stelem.ref
0xe1f6  dup
0xe1f7  ldc.i4.1
0xe1f8  ldstr    aContains// "Contains"
0xe1fd  stelem.ref
0xe1fe  dup
0xe1ff  ldc.i4.2
0xe200  ldstr    aStartswith// "StartsWith"
0xe205  stelem.ref
0xe206  dup
0xe207  ldc.i4.3
0xe208  ldstr    aEndswith// "EndsWith"
0xe20d  stelem.ref
0xe20e  stsfld   string[] Microsoft.Xrm.Sdk.Linq.QueryProvider::_supportedMethods
0xe213  ldsfld   string[] Microsoft.Xrm.Sdk.Linq.QueryProvider::_supportedMethods
0xe218  ldc.i4.3
0xe219  newarr   [mscorlib]System.String
0xe21e  dup
0xe21f  ldc.i4.0
0xe220  ldstr    aCompare// "Compare"
0xe225  stelem.ref
0xe226  dup
0xe227  ldc.i4.1
0xe228  ldstr    aLike// "Like"
0xe22d  stelem.ref
0xe22e  dup
0xe22f  ldc.i4.2
0xe230  ldstr    aGetvalueordefa// "GetValueOrDefault"
0xe235  stelem.ref
0xe236  call     T0x2B000047
0xe23b  call     T0x2B000048
0xe240  stsfld   string[] Microsoft.Xrm.Sdk.Linq.QueryProvider::_validMethods
0xe245  ldc.i4.2
0xe246  newarr   [mscorlib]System.String
0xe24b  dup
0xe24c  ldc.i4.0
0xe24d  ldstr    aId// "Id"
0xe252  stelem.ref
0xe253  dup
0xe254  ldc.i4.1
0xe255  ldstr    aValue_0// "Value"
0xe25a  stelem.ref
0xe25b  stsfld   string[] Microsoft.Xrm.Sdk.Linq.QueryProvider::_validProperties
0xe260  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Core]System.Linq.Expressions.ExpressionType, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator>::.ctor()
0xe265  dup
0xe266  ldc.i4.s 0xD
0xe268  ldc.i4.0
0xe269  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Core]System.Linq.Expressions.ExpressionType, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0xe26e  dup
0xe26f  ldc.i4.s 0xF
0xe271  ldc.i4.2
0xe272  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Core]System.Linq.Expressions.ExpressionType, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0xe277  dup
0xe278  ldc.i4.s 0x10
0xe27a  ldc.i4.4
0xe27b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Core]System.Linq.Expressions.ExpressionType, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0xe280  dup
0xe281  ldc.i4.s 0x14
0xe283  ldc.i4.3
0xe284  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Core]System.Linq.Expressions.ExpressionType, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0xe289  dup
0xe28a  ldc.i4.s 0x15
0xe28c  ldc.i4.5
0xe28d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Core]System.Linq.Expressions.ExpressionType, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0xe292  dup
0xe293  ldc.i4.s 0x23
0xe295  ldc.i4.1
0xe296  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Core]System.Linq.Expressions.ExpressionType, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0xe29b  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Core]System.Linq.Expressions.ExpressionType, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator> Microsoft.Xrm.Sdk.Linq.QueryProvider::_conditionLookup
0xe2a0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator>::.ctor()
0xe2a5  dup
0xe2a6  ldc.i4.0
0xe2a7  ldc.i4.1
0xe2a8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0xe2ad  dup
0xe2ae  ldc.i4.1
0xe2af  ldc.i4.0
0xe2b0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0xe2b5  dup
0xe2b6  ldc.i4.2
0xe2b7  ldc.i4.5
0xe2b8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0xe2bd  dup
0xe2be  ldc.i4.4
0xe2bf  ldc.i4.3
0xe2c0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0xe2c5  dup
0xe2c6  ldc.i4.3
0xe2c7  ldc.i4.4
0xe2c8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0xe2cd  dup
0xe2ce  ldc.i4.5
0xe2cf  ldc.i4.2
0xe2d0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0xe2d5  dup
0xe2d6  ldc.i4.6
0xe2d7  ldc.i4.7
0xe2d8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0xe2dd  dup
0xe2de  ldc.i4.7
0xe2df  ldc.i4.6
0xe2e0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0xe2e5  dup
  ... truncated ...
```
