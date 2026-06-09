# Microsoft.Crm.Setup.Common.DatabaseFilesValidator::DoDatabaseFilesExist

- ea: `0x45f0`
- end: `0x480c`
- name: `Microsoft.Crm.Setup.Common.DatabaseFilesValidator::DoDatabaseFilesExist`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4340`

## callees

- `0x45f0`

## string_xrefs

- `0x463d`: `CREATE DATABASE "{0}" ON (NAME = temp_crm_dat, FILENAME = "{1}") LOG ON (NAME = temp_crm_log, FILENAME = "{2}");`

## pseudocode

```c

```

## disassembly

```asm
0x45f0  ldarg.1
0x45f1  ldstr    aMaster// "master"
0x45f6  ldc.i4.0
0x45f7  ldc.i4.0
0x45f8  call     string [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.Helpers::GetConnectionString(string, string, bool, bool)
0x45fd  newobj   instance void [System.Data]System.Data.SqlClient.SqlConnection::.ctor(string)
0x4602  stloc.0
0x4603  ldloc.0
0x4604  callvirt instance class [System.Data]System.Data.SqlClient.SqlCommand [System.Data]System.Data.SqlClient.SqlConnection::CreateCommand()
0x4609  stloc.1
0x460a  ldc.i4.0
0x460b  stloc.2
0x460c  ldc.i4.0
0x460d  stloc.3
0x460e  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x4613  stloc.s  0xC
0x4615  ldloca.s 0xC
0x4617  ldstr    aN// "N"
0x461c  call     instance string [mscorlib]System.Guid::ToString(string)
0x4621  ldc.i4.0
0x4622  ldc.i4.2
0x4623  callvirt instance string [mscorlib]System.String::Remove(int32, int32)
0x4628  stloc.s  4
0x462a  ldstr    aExecSpAttachDb// "EXEC sp_attach_db @dbname = @databaseNa"...
0x462f  stloc.s  5
0x4631  ldstr    aExecSpDetachDb// "EXEC sp_detach_db @dbname = @databaseNa"...
0x4636  stloc.s  6
0x4638  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x463d  ldstr    aCreateDatabase// "CREATE DATABASE \"{0}\" ON (NAME = temp"...
0x4642  ldc.i4.3
0x4643  newarr   [mscorlib]System.Object
0x4648  dup
0x4649  ldc.i4.0
0x464a  ldloc.s  4
0x464c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0x4651  stelem.ref
0x4652  dup
0x4653  ldc.i4.1
0x4654  ldarg.2
0x4655  stelem.ref
0x4656  dup
0x4657  ldc.i4.2
0x4658  ldarg.3
0x4659  stelem.ref
0x465a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x465f  stloc.s  7
0x4661  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4666  ldstr    aDropDatabase0// "DROP DATABASE \"{0}\";"
0x466b  ldc.i4.1
0x466c  newarr   [mscorlib]System.Object
0x4671  dup
0x4672  ldc.i4.0
0x4673  ldloc.s  4
0x4675  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0x467a  stelem.ref
0x467b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4680  stloc.s  8
0x4682  ldstr    aDatabasename// "@databaseName"
0x4687  ldc.i4.s 0x16
0x4689  ldc.i4.s 0x1E
0x468b  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x4690  stloc.s  9
0x4692  ldstr    aDbfile// "@dbFile"
0x4697  ldc.i4.s 0xC
0x4699  ldc.i4   0x104
0x469e  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x46a3  stloc.s  0xA
0x46a5  ldstr    aLogfile// "@logFile"
0x46aa  ldc.i4.s 0xC
0x46ac  ldc.i4   0x104
0x46b1  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x46b6  stloc.s  0xB
0x46b8  ldloc.s  9
0x46ba  ldloc.s  4
0x46bc  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x46c1  ldloc.s  0xA
0x46c3  ldarg.2
0x46c4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x46c9  ldloc.s  0xB
0x46cb  ldarg.3
0x46cc  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x46d1  ldloc.1
0x46d2  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x46d7  ldloc.s  9
0x46d9  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x46de  pop
0x46df  ldloc.1
0x46e0  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x46e5  ldloc.s  0xA
0x46e7  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x46ec  pop
0x46ed  ldloc.1
0x46ee  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x46f3  ldloc.s  0xB
0x46f5  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x46fa  pop
0x46fb  ldloc.1
0x46fc  ldc.i4.1
0x46fd  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x4702  ldloc.0
0x4703  callvirt instance void [System.Data]System.Data.Common.DbConnection::Open()
0x4708  ldloc.1
0x4709  ldloc.s  5
0x470b  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x4710  ldloc.1
0x4711  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x4716  pop
0x4717  ldloc.1
0x4718  ldloc.s  6
0x471a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x471f  ldloc.1
0x4720  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x4725  pop
0x4726  ldc.i4.1
0x4727  stloc.2
0x4728  leave.s  loc_478E
0x472a  stloc.s  0xD
0x472c  ldloc.s  0xD
0x472e  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x4733  ldc.i4   0x1400
0x4738  bne.un.s loc_4783
0x473a  ldloc.s  0xD
0x473c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4741  ldstr    a2S// " 2\\s*:"
0x4746  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::IsMatch(string, string)
0x474b  brfalse.s loc_4783
0x474d  ldloc.s  0xD
0x474f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4754  ldarg.3
0x4755  callvirt instance bool [mscorlib]System.String::Contains(string)
0x475a  brfalse.s loc_477F
0x475c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4761  ldstr    aTheDatabaseFil// "The database file ({0}) is present, but"...
0x4766  ldc.i4.2
0x4767  newarr   [mscorlib]System.Object
0x476c  dup
0x476d  ldc.i4.0
0x476e  ldarg.2
0x476f  stelem.ref
0x4770  dup
0x4771  ldc.i4.1
0x4772  ldarg.3
0x4773  stelem.ref
0x4774  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4779  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupException::.ctor(string)
0x477e  throw
0x477f  ldc.i4.1
0x4780  stloc.3
0x4781  br.s     loc_4785
0x4783  rethrow
0x4785  leave.s  loc_478E
0x4787  ldloc.0
0x4788  callvirt instance void [System.Data]System.Data.Common.DbConnection::Close()
0x478d  endfinally
0x478e  ldloc.3
0x478f  brfalse.s loc_47F0
0x4791  ldloc.0
0x4792  callvirt instance void [System.Data]System.Data.Common.DbConnection::Open()
0x4797  ldloc.1
0x4798  ldloc.s  7
0x479a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x479f  ldloc.1
0x47a0  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x47a5  pop
0x47a6  ldloc.1
0x47a7  ldloc.s  8
0x47a9  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x47ae  ldloc.1
0x47af  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x47b4  pop
0x47b5  leave.s  loc_47F0
0x47b7  callvirt instance string [mscorlib]System.Exception::get_Message()
0x47bc  ldarg.3
0x47bd  callvirt instance bool [mscorlib]System.String::Contains(string)
0x47c2  brfalse.s loc_47E7
0x47c4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x47c9  ldstr    aTheLogFile0IsP// "The log file ({0}) is present, but the "...
0x47ce  ldc.i4.2
0x47cf  newarr   [mscorlib]System.Object
0x47d4  dup
0x47d5  ldc.i4.0
0x47d6  ldarg.3
0x47d7  stelem.ref
0x47d8  dup
0x47d9  ldc.i4.1
0x47da  ldarg.2
0x47db  stelem.ref
0x47dc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x47e1  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupException::.ctor(string)
0x47e6  throw
0x47e7  rethrow
0x47e9  ldloc.0
0x47ea  callvirt instance void [System.Data]System.Data.Common.DbConnection::Close()
0x47ef  endfinally
0x47f0  ldloc.2
0x47f1  stloc.s  0xE
0x47f3  leave.s  loc_4809
0x47f5  ldloc.1
0x47f6  brfalse.s loc_47FE
0x47f8  ldloc.1
0x47f9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x47fe  endfinally
0x47ff  ldloc.0
0x4800  brfalse.s loc_4808
0x4802  ldloc.0
0x4803  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4808  endfinally
0x4809  ldloc.s  0xE
0x480b  ret
```
