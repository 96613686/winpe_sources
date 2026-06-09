# Microsoft.Xrm.Sdk.Query.LinkEntity::.ctor_0

- ea: `0x92a0`
- end: `0x92e2`
- name: `Microsoft.Xrm.Sdk.Query.LinkEntity::.ctor_0`
- size: `66`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x9290`
- `0x9450`
- `0x9b50`

## callees

- `0x8cd0`
- `0x90e0`

## pseudocode

```c

```

## disassembly

```asm
0x92a0  ldarg.0
0x92a1  call     instance void [mscorlib]System.Object::.ctor()
0x92a6  ldarg.0
0x92a7  ldarg.1
0x92a8  stfld    string Microsoft.Xrm.Sdk.Query.LinkEntity::_linkFromEntityName
0x92ad  ldarg.0
0x92ae  ldarg.2
0x92af  stfld    string Microsoft.Xrm.Sdk.Query.LinkEntity::_linkToEntityName
0x92b4  ldarg.0
0x92b5  ldarg.3
0x92b6  stfld    string Microsoft.Xrm.Sdk.Query.LinkEntity::_linkFromAttributeName
0x92bb  ldarg.0
0x92bc  ldarg.s  4
0x92be  stfld    string Microsoft.Xrm.Sdk.Query.LinkEntity::_linkToAttributeName
0x92c3  ldarg.0
0x92c4  ldarg.s  5
0x92c6  stfld    valuetype Microsoft.Xrm.Sdk.Query.JoinOperator Microsoft.Xrm.Sdk.Query.LinkEntity::_joinOperator
0x92cb  ldarg.0
0x92cc  newobj   instance void Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor()
0x92d1  stfld    class Microsoft.Xrm.Sdk.Query.ColumnSet Microsoft.Xrm.Sdk.Query.LinkEntity::_columns
0x92d6  ldarg.0
0x92d7  newobj   instance void Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x92dc  stfld    class Microsoft.Xrm.Sdk.Query.FilterExpression Microsoft.Xrm.Sdk.Query.LinkEntity::_linkCriteria
0x92e1  ret
```
