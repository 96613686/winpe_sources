# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectObjectCountAndTableSizes

- ea: `0x7840`
- end: `0x7881`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectObjectCountAndTableSizes`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x45c0`

## callees

- `0x7840`
- `0xeec0`

## string_xrefs

- `0x784d`: `\ndeclare @tempTable table\n(\n  TableName nvarchar(128),\n  NumberOfRows bigint,\n  ReservedSpace nvarchar(20),\n  DataSpace nvarchar(20),\n  IndexSpace nvarchar(20),\n  UnusedSpace nvarchar(20)\n)\n\ndeclare @returnTable table\n(\n  ObjectTypeCode int,\n  ObjectCount bigint,\n  PrimaryTableSize int default 0,\n  SecondaryTableSize int default 0\n)\n\ndeclare @TableName sysname\n\ndeclare TableCursor cursor FORWARD_ONLY READ_ONLY for\nselect t.name from sys.tables t where `

## pseudocode

```c

```

## disassembly

```asm
0x7840  newobj   instance void <>c__DisplayClass37_0::.ctor()
0x7845  stloc.0
0x7846  ldloc.0
0x7847  ldarg.1
0x7848  stfld    class [Microsoft.Crm]Microsoft.Crm.ISqmSession <>c__DisplayClass37_0::session
0x784d  ldstr    aDeclareTemptab// "\r\ndeclare @tempTable table\r\n(\r\n  "...
0x7852  stloc.1
0x7853  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x7858  stloc.2
0x7859  ldloc.2
0x785a  ldloc.1
0x785b  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7860  ldarg.0
0x7861  ldloc.2
0x7862  ldloc.0
0x7863  ldftn    instance void <>c__DisplayClass37_0::<CollectObjectCountAndTableSizes>b__0(object[] values)
0x7869  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x786e  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x7873  pop
0x7874  leave.s  loc_7880
0x7876  ldloc.2
0x7877  brfalse.s loc_787F
0x7879  ldloc.2
0x787a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x787f  endfinally
0x7880  ret
```
