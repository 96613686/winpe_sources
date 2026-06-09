# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSqlProductLevel

- ea: `0x6850`
- end: `0x6861`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSqlProductLevel`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x43c0`

## callees

- `0x6890`

## pseudocode

```c

```

## disassembly

```asm
0x6850  ldstr    aSelectServerpr_1// "SELECT SERVERPROPERTY('ProductLevel')"
0x6855  stloc.0
0x6856  ldc.i4.1
0x6857  stloc.1
0x6858  ldarg.0
0x6859  ldloc.0
0x685a  ldloc.1
0x685b  call     instance string Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneString(string sqlCommand, valuetype [System.Data]System.Data.CommandType commandType)
0x6860  ret
```
