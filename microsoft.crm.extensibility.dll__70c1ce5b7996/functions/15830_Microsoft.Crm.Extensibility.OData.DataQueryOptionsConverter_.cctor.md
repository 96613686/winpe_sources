# Microsoft.Crm.Extensibility.OData.DataQueryOptionsConverter::.cctor

- ea: `0x15830`
- end: `0x15928`
- name: `Microsoft.Crm.Extensibility.OData.DataQueryOptionsConverter::.cctor`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x158e1`: `$skiptoken`
- `0x158ec`: `$deltatoken`

## pseudocode

```c

```

## disassembly

```asm
0x15830  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::.ctor()
0x15835  dup
0x15836  ldc.i4.0
0x15837  ldc.i4.1
0x15838  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0x1583d  dup
0x1583e  ldc.i4.1
0x1583f  ldc.i4.0
0x15840  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0x15845  dup
0x15846  ldc.i4.2
0x15847  ldc.i4.5
0x15848  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0x1584d  dup
0x1584e  ldc.i4.4
0x1584f  ldc.i4.3
0x15850  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0x15855  dup
0x15856  ldc.i4.3
0x15857  ldc.i4.4
0x15858  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0x1585d  dup
0x1585e  ldc.i4.5
0x1585f  ldc.i4.2
0x15860  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0x15865  dup
0x15866  ldc.i4.6
0x15867  ldc.i4.7
0x15868  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0x1586d  dup
0x1586e  ldc.i4.7
0x1586f  ldc.i4.6
0x15870  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0x15875  dup
0x15876  ldc.i4.s 0xC
0x15878  ldc.i4.s 0xD
0x1587a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0x1587f  dup
0x15880  ldc.i4.s 0xD
0x15882  ldc.i4.s 0xC
0x15884  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>, !!T0)
0x15889  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator> Microsoft.Crm.Extensibility.OData.DataQueryOptionsConverter::_operatorNegationLookup
0x1588e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x15893  dup
0x15894  ldstr    aSkip// "$skip"
0x15899  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1589e  dup
0x1589f  ldstr    aSelect// "$select"
0x158a4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x158a9  dup
0x158aa  ldstr    aTop// "$top"
0x158af  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x158b4  dup
0x158b5  ldstr    aCount// "$count"
0x158ba  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x158bf  dup
0x158c0  ldstr    aExpand// "$expand"
0x158c5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x158ca  dup
0x158cb  ldstr    aOrderby// "$orderby"
0x158d0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x158d5  dup
0x158d6  ldstr    aFilter_0// "$filter"
0x158db  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x158e0  dup
0x158e1  ldstr    aSkiptoken// "$skiptoken"
0x158e6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x158eb  dup
0x158ec  ldstr    aDeltatoken// "$deltatoken"
0x158f1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x158f6  dup
0x158f7  ldstr    aSolutionVersio// "solution-versions"
0x158fc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x15901  dup
0x15902  ldstr    aLabellanguages// "LabelLanguages"
0x15907  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1590c  dup
0x1590d  ldstr    aNolock// "NoLock"
0x15912  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x15917  dup
0x15918  ldstr    aApply// "$apply"
0x1591d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x15922  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Extensibility.OData.DataQueryOptionsConverter::allowedQueryOptions
0x15927  ret
```
