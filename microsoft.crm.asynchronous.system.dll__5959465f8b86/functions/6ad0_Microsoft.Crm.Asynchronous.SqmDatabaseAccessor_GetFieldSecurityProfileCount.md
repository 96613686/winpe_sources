# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetFieldSecurityProfileCount

- ea: `0x6ad0`
- end: `0x6ae1`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetFieldSecurityProfileCount`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4d60`

## callees

- `0x67f0`

## string_xrefs

- `0x6ad0`: `SELECT COUNT(*) FROM FieldSecurityProfile WHERE FieldSecurityProfileId <> '572329C1-A042-4E22-BE47-367C6374EA45'`

## pseudocode

```c

```

## disassembly

```asm
0x6ad0  ldstr    aSelectCountFro_3// "SELECT COUNT(*) FROM FieldSecurityProfi"...
0x6ad5  stloc.0
0x6ad6  ldc.i4.1
0x6ad7  stloc.1
0x6ad8  ldarg.0
0x6ad9  ldloc.0
0x6ada  ldloc.1
0x6adb  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneInteger(string sqlCommand, valuetype [System.Data]System.Data.CommandType commandType)
0x6ae0  ret
```
