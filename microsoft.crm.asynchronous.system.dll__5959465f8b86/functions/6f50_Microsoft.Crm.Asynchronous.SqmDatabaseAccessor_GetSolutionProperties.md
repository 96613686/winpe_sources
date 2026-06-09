# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSolutionProperties

- ea: `0x6f50`
- end: `0x6fc7`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSolutionProperties`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x6d90`

## callees

- `0x6f50`
- `0xeb00`

## pseudocode

```c

```

## disassembly

```asm
0x6f50  newobj   instance void <>c__DisplayClass29_0::.ctor()
0x6f55  stloc.0
0x6f56  ldloc.0
0x6f57  ldc.i4.0
0x6f58  stfld    int32 <>c__DisplayClass29_0::solutionProperties
0x6f5d  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x6f62  stloc.1
0x6f63  ldloc.1
0x6f64  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6f69  ldstr    aSelectIsnullPi// "SELECT ISNULL(PinpointSolutionId,0), Is"...
0x6f6e  ldc.i4.0
0x6f6f  newarr   [mscorlib]System.Object
0x6f74  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6f79  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6f7e  ldloc.1
0x6f7f  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x6f84  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x6f89  ldstr    aSolutionid// "@SolutionId"
0x6f8e  ldc.i4.s 0xE
0x6f90  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6f95  ldarg.1
0x6f96  box      [mscorlib]System.Guid
0x6f9b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6fa0  ldarg.0
0x6fa1  ldloc.1
0x6fa2  ldloc.0
0x6fa3  ldftn    instance void <>c__DisplayClass29_0::<GetSolutionProperties>b__0(object[] values)
0x6fa9  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x6fae  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x6fb3  pop
0x6fb4  leave.s  loc_6FC0
0x6fb6  ldloc.1
0x6fb7  brfalse.s loc_6FBF
0x6fb9  ldloc.1
0x6fba  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6fbf  endfinally
0x6fc0  ldloc.0
0x6fc1  ldfld    int32 <>c__DisplayClass29_0::solutionProperties
0x6fc6  ret
```
