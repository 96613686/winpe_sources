# Microsoft.Crm.Asynchronous.ImportDataAccess::DuplicateFound

- ea: `0x5570`
- end: `0x55ec`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::DuplicateFound`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x12170`

## callees

- `0x5570`
- `0x1ffb0`

## pseudocode

```c

```

## disassembly

```asm
0x5570  newobj   instance void <>c__DisplayClass41_0::.ctor()
0x5575  stloc.0
0x5576  ldstr    aSelectCountFro_0// "SELECT COUNT(*) From {0} Where {1}0 = @"...
0x557b  stloc.1
0x557c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5581  ldloc.1
0x5582  ldc.i4.2
0x5583  newarr   [mscorlib]System.Object
0x5588  dup
0x5589  ldc.i4.0
0x558a  ldarg.1
0x558b  stelem.ref
0x558c  dup
0x558d  ldc.i4.1
0x558e  ldarg.2
0x558f  stelem.ref
0x5590  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5595  ldloc.0
0x5596  ldc.i4.m1
0x5597  stfld    int32 <>c__DisplayClass41_0::count
0x559c  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x55a1  stloc.2
0x55a2  ldloc.2
0x55a3  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x55a8  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x55ad  ldstr    aPrimarykey// "primaryKey"
0x55b2  ldarg.3
0x55b3  box      [mscorlib]System.Guid
0x55b8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x55bd  pop
0x55be  ldarg.0
0x55bf  ldloc.2
0x55c0  ldloc.0
0x55c1  ldftn    instance void <>c__DisplayClass41_0::<DuplicateFound>b__0(object[] values)
0x55c7  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x55cc  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x55d1  pop
0x55d2  leave.s  loc_55DE
0x55d4  ldloc.2
0x55d5  brfalse.s loc_55DD
0x55d7  ldloc.2
0x55d8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x55dd  endfinally
0x55de  ldloc.0
0x55df  ldfld    int32 <>c__DisplayClass41_0::count
0x55e4  ldarg.s  4
0x55e6  ble.s    loc_55EA
0x55e8  ldc.i4.1
0x55e9  ret
0x55ea  ldc.i4.0
0x55eb  ret
```
