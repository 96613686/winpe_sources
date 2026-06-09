# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetBuildQFENumber

- ea: `0x6700`
- end: `0x6711`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetBuildQFENumber`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4380`

## callees

- `0x67f0`

## pseudocode

```c

```

## disassembly

```asm
0x6700  ldstr    aSelectBuildqfe// "SELECT BuildQFE from BuildVersion"
0x6705  stloc.0
0x6706  ldc.i4.1
0x6707  stloc.1
0x6708  ldarg.0
0x6709  ldloc.0
0x670a  ldloc.1
0x670b  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneInteger(string sqlCommand, valuetype [System.Data]System.Data.CommandType commandType)
0x6710  ret
```
