# Microsoft.Crm.Entities.RollupProperties::ConvertExpressionOperatorToRollupAggregate

- ea: `0x34c0`
- end: `0x34f4`
- name: `Microsoft.Crm.Entities.RollupProperties::ConvertExpressionOperatorToRollupAggregate`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x31f0`

## callees

- `0x34c0`

## pseudocode

```c

```

## disassembly

```asm
0x34c0  ldarg.1
0x34c1  ldc.i4.s 0x23
0x34c3  sub
0x34c4  switch   loc_34DF, loc_34E1, loc_34E3, loc_34E5, loc_34E7
0x34dd  br.s     loc_34E9
0x34df  ldc.i4.1
0x34e0  ret
0x34e1  ldc.i4.0
0x34e2  ret
0x34e3  ldc.i4.2
0x34e4  ret
0x34e5  ldc.i4.3
0x34e6  ret
0x34e7  ldc.i4.4
0x34e8  ret
0x34e9  ldstr    aAggregationtyp// "AggregationType is not supported"
0x34ee  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentOutOfRangeException::.ctor(string)
0x34f3  throw
```
