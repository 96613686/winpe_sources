# Microsoft.Crm.CrmLive.SqlUtility::SqlMultipleUser

- ea: `0x9430`
- end: `0x95c7`
- name: `Microsoft.Crm.CrmLive.SqlUtility::SqlMultipleUser`
- size: `407`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x9c30`
- `0x9ce0`
- `0x9d20`

## callees

- `0x9340`
- `0x9430`

## string_xrefs

- `0x943c`: `server={0};database=master;Integrated Security=sspi`
- `0x9474`: `\n				if exists (select * from sys.databases where name={0} and state = 0)\n				begin\n					declare @ConnectedSessions table\n					(\n						program varchar(100) not null,\n						command varchar(100) null,\n						sessionId int not null\n					)\n\n					insert into @ConnectedSessions\n					(program, command, sessionId)\n					select program_name, command, es.session_id from sys.dm_exec_sessions es\n					join sys.databases sysdata on es.database_id = sysdata.database_id\n					left join `
- `0x94af`: `command`
- `0x9505`: `Exception running telemetry on connected sessions during switch to multi-user mode. Exception details: {0}`
- `0x9560`: `Programs {0} were connected to the single-user database, running commands {1}. Exception details: {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x9430  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x9435  stloc.0
0x9436  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x943b  stloc.1
0x943c  ldstr    aServer0Databas// "server={0};database=master;Integrated S"...
0x9441  stloc.2
0x9442  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9447  ldloc.2
0x9448  ldc.i4.1
0x9449  newarr   [mscorlib]System.Object
0x944e  dup
0x944f  ldc.i4.0
0x9450  ldarg.0
0x9451  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0x9456  stelem.ref
0x9457  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x945c  stloc.2
0x945d  ldloc.2
0x945e  newobj   instance void [System.Data]System.Data.SqlClient.SqlConnection::.ctor(string)
0x9463  stloc.3
0x9464  ldloc.3
0x9465  callvirt instance void [System.Data]System.Data.IDbConnection::Open()
0x946a  ldloc.3
0x946b  callvirt instance class [System.Data]System.Data.IDbCommand [System.Data]System.Data.IDbConnection::CreateCommand()
0x9470  stloc.s  4
0x9472  ldloc.s  4
0x9474  ldstr    aIfExistsSelect_5// "\r\n\t\t\t\tif exists (select * from sy"...
0x9479  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x947e  ldloc.s  4
0x9480  ldc.i4   0xE10
0x9485  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandTimeout(int32)
0x948a  ldloc.s  4
0x948c  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0x9491  stloc.s  5
0x9493  br.s     loc_94C3
0x9495  ldloc.0
0x9496  ldloc.s  5
0x9498  ldstr    aProgram// "program"
0x949d  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x94a2  castclass [mscorlib]System.String
0x94a7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x94ac  ldloc.1
0x94ad  ldloc.s  5
0x94af  ldstr    aCommand// "command"
0x94b4  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x94b9  castclass [mscorlib]System.String
0x94be  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x94c3  ldloc.s  5
0x94c5  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x94ca  brtrue.s loc_9495
0x94cc  leave.s  loc_94DA
0x94ce  ldloc.s  5
0x94d0  brfalse.s loc_94D9
0x94d2  ldloc.s  5
0x94d4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x94d9  endfinally
0x94da  leave.s  loc_94E8
0x94dc  ldloc.s  4
0x94de  brfalse.s loc_94E7
0x94e0  ldloc.s  4
0x94e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x94e7  endfinally
0x94e8  ldloc.3
0x94e9  callvirt instance void [System.Data]System.Data.IDbConnection::Close()
0x94ee  leave.s  loc_94FA
0x94f0  ldloc.3
0x94f1  brfalse.s loc_94F9
0x94f3  ldloc.3
0x94f4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x94f9  endfinally
0x94fa  leave.s  loc_9521
0x94fc  stloc.s  6
0x94fe  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x9503  ldc.i4.s 0x1D
0x9505  ldstr    aExceptionRunni// "Exception running telemetry on connecte"...
0x950a  ldc.i4.1
0x950b  newarr   [mscorlib]System.Object
0x9510  dup
0x9511  ldc.i4.0
0x9512  ldloc.s  6
0x9514  callvirt instance string [mscorlib]System.Object::ToString()
0x9519  stelem.ref
0x951a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x951f  leave.s  loc_9521
0x9521  nop
0x9522  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9527  ldstr    aIfExistsSelect_6// "\r\n\t\t\t\tif exists (select * from sy"...
0x952c  ldc.i4.2
0x952d  newarr   [mscorlib]System.Object
0x9532  dup
0x9533  ldc.i4.0
0x9534  ldarg.1
0x9535  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlLiteralEncode(string)
0x953a  stelem.ref
0x953b  dup
0x953c  ldc.i4.1
0x953d  ldarg.1
0x953e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0x9543  stelem.ref
0x9544  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9549  stloc.s  7
0x954b  ldarg.0
0x954c  ldloc.s  7
0x954e  call     void Microsoft.Crm.CrmLive.SqlUtility::SqlMasterExecute(string server, string sql)
0x9553  leave.s  loc_95C6
0x9555  stloc.s  8
0x9557  ldloc.s  8
0x9559  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x955e  ldc.i4.s 0x1D
0x9560  ldstr    aPrograms0WereC// "Programs {0} were connected to the sing"...
0x9565  ldc.i4.3
0x9566  newarr   [mscorlib]System.Object
0x956b  dup
0x956c  ldc.i4.0
0x956d  ldstr    asc_522DA// ", "
0x9572  ldloc.0
0x9573  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x9578  stelem.ref
0x9579  dup
0x957a  ldc.i4.1
0x957b  ldstr    asc_522DA// ", "
0x9580  ldloc.1
0x9581  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x9586  stelem.ref
0x9587  dup
0x9588  ldc.i4.2
0x9589  ldloc.s  8
0x958b  callvirt instance string [mscorlib]System.Object::ToString()
0x9590  stelem.ref
0x9591  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9596  ldarg.2
0x9597  brfalse.s loc_959B
0x9599  rethrow
0x959b  leave.s  loc_95C6
0x959d  stloc.s  9
0x959f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x95a4  ldstr    aExceptionDetai// "Exception details: {0}"
0x95a9  ldc.i4.1
0x95aa  newarr   [mscorlib]System.Object
0x95af  dup
0x95b0  ldc.i4.0
0x95b1  ldloc.s  9
0x95b3  callvirt instance string [mscorlib]System.Object::ToString()
0x95b8  stelem.ref
0x95b9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x95be  ldloc.s  9
0x95c0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x95c5  throw
0x95c6  ret
```
