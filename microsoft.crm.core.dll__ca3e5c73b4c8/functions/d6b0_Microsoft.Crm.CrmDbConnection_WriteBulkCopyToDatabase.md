# Microsoft.Crm.CrmDbConnection::WriteBulkCopyToDatabase

- ea: `0xd6b0`
- end: `0xd745`
- name: `Microsoft.Crm.CrmDbConnection::WriteBulkCopyToDatabase`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x61fa0`

## callees

- `0xd6b0`
- `0xe320`
- `0x1be80`
- `0x65840`

## string_xrefs

- `0xd6ca`: `bulkCopy`
- `0xd709`: `Bulk Create {0} rows in {1}`

## pseudocode

```c

```

## disassembly

```asm
0xd6b0  newobj   instance void <>c__DisplayClass63_0::.ctor()
0xd6b5  stloc.0
0xd6b6  ldloc.0
0xd6b7  ldarg.1
0xd6b8  stfld    class [System.Data]System.Data.SqlClient.SqlBulkCopy <>c__DisplayClass63_0::bulkCopy
0xd6bd  ldloc.0
0xd6be  ldarg.2
0xd6bf  stfld    class [System.Data]System.Data.DataTable <>c__DisplayClass63_0::table
0xd6c4  ldloc.0
0xd6c5  ldfld    class [System.Data]System.Data.SqlClient.SqlBulkCopy <>c__DisplayClass63_0::bulkCopy
0xd6ca  ldstr    aBulkcopy// "bulkCopy"
0xd6cf  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0xd6d4  ldloc.0
0xd6d5  ldfld    class [System.Data]System.Data.DataTable <>c__DisplayClass63_0::table
0xd6da  ldstr    aTable// "table"
0xd6df  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0xd6e4  ldloc.0
0xd6e5  ldfld    class [System.Data]System.Data.DataTable <>c__DisplayClass63_0::table
0xd6ea  callvirt instance class [System.Data]System.Data.DataRowCollection [System.Data]System.Data.DataTable::get_Rows()
0xd6ef  callvirt instance int32 [System.Data]System.Data.InternalDataCollectionBase::get_Count()
0xd6f4  brtrue.s loc_D6F7
0xd6f6  ret
0xd6f7  ldloc.0
0xd6f8  ldftn    instance void <>c__DisplayClass63_0::<WriteBulkCopyToDatabase>b__0()
0xd6fe  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0xd703  ldarg.0
0xd704  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd709  ldstr    aBulkCreate0Row// "Bulk Create {0} rows in {1}"
0xd70e  ldc.i4.2
0xd70f  newarr   [mscorlib]System.Object
0xd714  dup
0xd715  ldc.i4.0
0xd716  ldloc.0
0xd717  ldfld    class [System.Data]System.Data.DataTable <>c__DisplayClass63_0::table
0xd71c  callvirt instance class [System.Data]System.Data.DataRowCollection [System.Data]System.Data.DataTable::get_Rows()
0xd721  callvirt instance int32 [System.Data]System.Data.InternalDataCollectionBase::get_Count()
0xd726  box      [mscorlib]System.Int32
0xd72b  stelem.ref
0xd72c  dup
0xd72d  ldc.i4.1
0xd72e  ldloc.0
0xd72f  ldfld    class [System.Data]System.Data.SqlClient.SqlBulkCopy <>c__DisplayClass63_0::bulkCopy
0xd734  callvirt instance string [System.Data]System.Data.SqlClient.SqlBulkCopy::get_DestinationTableName()
0xd739  stelem.ref
0xd73a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd73f  call     void Microsoft.Crm.CrmDbConnection::InternalExecuteWithRetry(class [mscorlib]System.Action ExecuteMethod, class Microsoft.Crm.CrmDbConnection connection, string descriptionText)
0xd744  ret
```
