# Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords_6

- ea: `0xd9c0`
- end: `0xda1e`
- name: `Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords_6`
- size: `94`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xd6e0`
- `0xd780`
- `0xda20`

## callees

- `0xd9c0`
- `0x17bc0`

## pseudocode

```c

```

## disassembly

```asm
0xd9c0  newobj   instance void <>c__DisplayClass22_0::.ctor()
0xd9c5  stloc.0
0xd9c6  ldloc.0
0xd9c7  ldarg.2
0xd9c8  stfld    class RecordProcessor <>c__DisplayClass22_0::recordProcessor
0xd9cd  ldloc.0
0xd9ce  ldc.i4.0
0xd9cf  stfld    int32 <>c__DisplayClass22_0::numberOfRecordsProcessed
0xd9d4  ldarg.s  4
0xd9d6  ldstr    aDeprecated// "<Deprecated>"
0xd9db  stind.ref
0xd9dc  ldarg.3
0xd9dd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd9e2  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xd9e7  brfalse.s loc_D9F4
0xd9e9  ldstr    aInputParameter// "Input parameter OrganizationId is Empty"...
0xd9ee  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xd9f3  throw
0xd9f4  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::DefaultInstance
0xd9f9  ldarg.3
0xd9fa  ldc.i4.0
0xd9fb  ldc.i4.0
0xd9fc  ldc.i4.0
0xd9fd  ldnull
0xd9fe  ldc.i4.0
0xd9ff  ldc.i4.0
0xda00  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::Get(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ConnectionAccessType, int32, string, bool, int32)
0xda05  ldarg.1
0xda06  ldloc.0
0xda07  ldftn    instance void <>c__DisplayClass22_0::<ExecuteSqlCommandAndProcessRecords>b__0(class [System.Data]System.Data.IDataReader reader)
0xda0d  newobj   instance void class [mscorlib]System.Action`1<class [System.Data]System.Data.IDataReader>::.ctor(object, native int)
0xda12  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess::ExecuteReaderAction(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, class [mscorlib]System.Action`1<class [System.Data]System.Data.IDataReader>)
0xda17  ldloc.0
0xda18  ldfld    int32 <>c__DisplayClass22_0::numberOfRecordsProcessed
0xda1d  ret
```
