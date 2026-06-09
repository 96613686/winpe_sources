# Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::CreateTempTable

- ea: `0x1000`
- end: `0x1075`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::CreateTempTable`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1f350`

## callees

- `0x1000`

## string_xrefs

- `0x1042`: `CREATE TABLE dbo.{0} (RecordId uniqueidentifier NOT NULL , EntityName nvarchar(128) , Processed bit default 0, QueryIndex int)`

## pseudocode

```c

```

## disassembly

```asm
0x1000  ldarg.2
0x1001  ldc.i4.0
0x1002  stind.i1
0x1003  ldstr    aSelect1FromDbo// "select 1 from dbo.sysobjects where xtyp"...
0x1008  ldc.i4.1
0x1009  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x100e  stloc.0
0x100f  ldloc.0
0x1010  ldstr    aName// "@name"
0x1015  ldarg.1
0x1016  ldloca.s 2
0x1018  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x101e  ldloc.2
0x101f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x1024  ldarg.0
0x1025  ldloc.0
0x1026  ldarg.0
0x1027  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x102c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1031  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteScalar(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, valuetype [mscorlib]System.Guid)
0x1036  brfalse.s loc_103D
0x1038  ldarg.2
0x1039  ldc.i4.1
0x103a  stind.i1
0x103b  ldc.i4.1
0x103c  ret
0x103d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1042  ldstr    aCreateTableDbo// "CREATE TABLE dbo.{0} (RecordId uniqueid"...
0x1047  ldc.i4.1
0x1048  newarr   [mscorlib]System.Object
0x104d  dup
0x104e  ldc.i4.0
0x104f  ldarg.1
0x1050  stelem.ref
0x1051  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1056  ldc.i4.1
0x1057  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x105c  stloc.1
0x105d  ldarg.0
0x105e  ldloc.1
0x105f  ldarg.0
0x1060  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x1065  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x106a  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteScalar(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, valuetype [mscorlib]System.Guid)
0x106f  pop
0x1070  ldarg.2
0x1071  ldc.i4.1
0x1072  stind.i1
0x1073  ldc.i4.0
0x1074  ret
```
