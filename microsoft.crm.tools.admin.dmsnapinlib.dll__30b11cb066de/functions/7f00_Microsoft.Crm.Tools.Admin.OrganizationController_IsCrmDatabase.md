# Microsoft.Crm.Tools.Admin.OrganizationController::IsCrmDatabase

- ea: `0x7f00`
- end: `0x804d`
- name: `Microsoft.Crm.Tools.Admin.OrganizationController::IsCrmDatabase`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x7e20`

## callees

- `0x7f00`
- `0x8050`

## string_xrefs

- `0x7f25`: `Cannot open the database ({0}) on the SQL Server ({1}) to check if it is a valid CRM database. Please verify that the user has access to this database and correct any other errors.The process will continue, but it returns this database as NOT valid CRM database. Exception: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x7f00  ldarg.3
0x7f01  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7f06  brtrue.s loc_7F14
0x7f08  ldarg.1
0x7f09  ldarg.3
0x7f0a  ldc.i4.5
0x7f0b  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x7f10  brtrue.s loc_7F14
0x7f12  ldc.i4.0
0x7f13  ret
0x7f14  ldarg.0
0x7f15  ldarg.1
0x7f16  call     class [System.Data]System.Data.SqlClient.SqlConnection [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.SqlUtility::GetConnection(string, string)
0x7f1b  stloc.0
0x7f1c  ldloc.0
0x7f1d  callvirt instance void [System.Data]System.Data.Common.DbConnection::Open()
0x7f22  leave.s  loc_7F48
0x7f24  stloc.1
0x7f25  ldstr    aCannotOpenTheD// "Cannot open the database ({0}) on the S"...
0x7f2a  ldc.i4.3
0x7f2b  newarr   [mscorlib]System.Object
0x7f30  dup
0x7f31  ldc.i4.0
0x7f32  ldarg.1
0x7f33  stelem.ref
0x7f34  dup
0x7f35  ldc.i4.1
0x7f36  ldarg.0
0x7f37  stelem.ref
0x7f38  dup
0x7f39  ldc.i4.2
0x7f3a  ldloc.1
0x7f3b  stelem.ref
0x7f3c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x7f41  ldc.i4.0
0x7f42  stloc.2
0x7f43  leave    loc_804B
0x7f48  ldloc.0
0x7f49  callvirt instance class [System.Data]System.Data.SqlClient.SqlCommand [System.Data]System.Data.SqlClient.SqlConnection::CreateCommand()
0x7f4e  stloc.3
0x7f4f  ldloc.3
0x7f50  ldstr    aSelectNameFrom_0// "SELECT name FROM sys.objects WHERE name"...
0x7f55  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7f5a  ldloc.3
0x7f5b  ldc.i4.1
0x7f5c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x7f61  ldloc.3
0x7f62  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0x7f67  stloc.s  4
0x7f69  ldloc.s  4
0x7f6b  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x7f70  brtrue.s loc_7F79
0x7f72  ldc.i4.0
0x7f73  stloc.2
0x7f74  leave    loc_804B
0x7f79  leave.s  loc_7F87
0x7f7b  ldloc.s  4
0x7f7d  brfalse.s loc_7F86
0x7f7f  ldloc.s  4
0x7f81  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7f86  endfinally
0x7f87  nop
0x7f88  ldarga.s 4
0x7f8a  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x7f8f  brfalse.s loc_7FA7
0x7f91  ldarg.0
0x7f92  ldarg.1
0x7f93  ldarg.s  4
0x7f95  ldarg.s  5
0x7f97  ldarg.s  6
0x7f99  call     valuetype [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.CrmDatabaseVersionSupported Microsoft.Crm.Tools.Admin.OrganizationController::IsCrmDatabaseVersionSupported(string sqlServerName, string organizationDatabaseName, valuetype [mscorlib]System.Nullable`1<int32> supportedMajorVersion, bool recognizeUpgrade, string installXmlPath)
0x7f9e  brtrue.s loc_7FA7
0x7fa0  ldc.i4.0
0x7fa1  stloc.2
0x7fa2  leave    loc_804B
0x7fa7  ldarg.2
0x7fa8  brfalse.s loc_8010
0x7faa  ldloc.3
0x7fab  ldstr    aSelectNameFrom_1// "SELECT Name FROM OrganizationBase WHERE"...
0x7fb0  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7fb5  ldloc.3
0x7fb6  ldc.i4.1
0x7fb7  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x7fbc  ldloc.3
0x7fbd  ldloc.0
0x7fbe  callvirt instance void [System.Data]System.Data.IDbCommand::set_Connection(class [System.Data]System.Data.IDbConnection)
0x7fc3  ldloc.3
0x7fc4  callvirt instance class [System.Data]System.Data.IDbDataParameter [System.Data]System.Data.IDbCommand::CreateParameter()
0x7fc9  stloc.s  5
0x7fcb  ldloc.s  5
0x7fcd  ldarg.2
0x7fce  callvirt instance void [System.Data]System.Data.IDataParameter::set_Value(object)
0x7fd3  ldloc.s  5
0x7fd5  ldstr    aName_0// "@Name"
0x7fda  callvirt instance void [System.Data]System.Data.IDataParameter::set_ParameterName(string)
0x7fdf  ldloc.3
0x7fe0  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x7fe5  ldloc.s  5
0x7fe7  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x7fec  pop
0x7fed  ldloc.3
0x7fee  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0x7ff3  stloc.s  6
0x7ff5  ldloc.s  6
0x7ff7  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x7ffc  brtrue.s loc_8002
0x7ffe  ldc.i4.0
0x7fff  stloc.2
0x8000  leave.s  loc_804B
0x8002  leave.s  loc_8010
0x8004  ldloc.s  6
0x8006  brfalse.s loc_800F
0x8008  ldloc.s  6
0x800a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x800f  endfinally
0x8010  leave.s  loc_8049
0x8012  stloc.s  7
0x8014  ldstr    aAnErrorOccurre// "An error occurred when retrieving the v"...
0x8019  ldc.i4.3
0x801a  newarr   [mscorlib]System.Object
0x801f  dup
0x8020  ldc.i4.0
0x8021  ldarg.1
0x8022  stelem.ref
0x8023  dup
0x8024  ldc.i4.1
0x8025  ldarg.0
0x8026  stelem.ref
0x8027  dup
0x8028  ldc.i4.2
0x8029  ldloc.s  7
0x802b  stelem.ref
0x802c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x8031  ldc.i4.0
0x8032  stloc.2
0x8033  leave.s  loc_804B
0x8035  ldloc.3
0x8036  brfalse.s loc_803E
0x8038  ldloc.3
0x8039  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x803e  endfinally
0x803f  ldloc.0
0x8040  brfalse.s loc_8048
0x8042  ldloc.0
0x8043  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8048  endfinally
0x8049  ldc.i4.1
0x804a  ret
0x804b  ldloc.2
0x804c  ret
```
