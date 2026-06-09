# Microsoft.Crm.Asynchronous.JobDataAccess::LogPendingOrgDBUpdateJobsInfo

- ea: `0x3730`
- end: `0x37e2`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::LogPendingOrgDBUpdateJobsInfo`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2b30`

## callees

- `0x3730`
- `0x4340`

## string_xrefs

- `0x3763`: `@readyState`
- `0x3741`: `SELECT Count(*), MIN(NextRunTime) FROM ScaleGroupOrganizationMaintenanceJobs\n										WHERE OperationType = 44\n										AND NextRunTime < '9999-01-01 00:00:00.000'\n										AND State = @readyState\n										AND Enabled = 1\n										GROUP BY OperationType`
- `0x37c0`: `[DBUPDATES] Pending org db update jobs count = {0}, Min of NextRunTime = {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x3730  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x3735  stloc.3
0x3736  ldloca.s 3
0x3738  ldc.i4.m1
0x3739  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddYears(int32)
0x373e  stloc.0
0x373f  ldc.i4.0
0x3740  stloc.1
0x3741  ldstr    aSelectCountMin// "SELECT Count(*), MIN(NextRunTime) FROM "...
0x3746  stloc.2
0x3747  ldarg.1
0x3748  callvirt instance class [System.Data]System.Data.IDbCommand [System.Data]System.Data.IDbConnection::CreateCommand()
0x374d  stloc.s  4
0x374f  ldloc.s  4
0x3751  ldloc.2
0x3752  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x3757  ldloc.s  4
0x3759  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x375e  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3763  ldstr    aReadystate// "@readyState"
0x3768  ldc.i4.0
0x3769  box      [mscorlib]System.Int32
0x376e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3773  pop
0x3774  ldloc.s  4
0x3776  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0x377b  stloc.s  5
0x377d  br.s     loc_379D
0x377f  ldloc.s  5
0x3781  ldc.i4.0
0x3782  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(int32)
0x3787  unbox.any [mscorlib]System.Int32
0x378c  stloc.1
0x378d  ldloc.s  5
0x378f  ldc.i4.1
0x3790  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(int32)
0x3795  unbox.any [mscorlib]System.DateTime
0x379a  stloc.0
0x379b  leave.s  loc_37C0
0x379d  ldloc.s  5
0x379f  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x37a4  brtrue.s loc_377F
0x37a6  leave.s  loc_37C0
0x37a8  ldloc.s  5
0x37aa  brfalse.s loc_37B3
0x37ac  ldloc.s  5
0x37ae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37b3  endfinally
0x37b4  ldloc.s  4
0x37b6  brfalse.s loc_37BF
0x37b8  ldloc.s  4
0x37ba  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37bf  endfinally
0x37c0  ldstr    aDbupdatesPendi// "[DBUPDATES] Pending org db update jobs "...
0x37c5  ldloc.1
0x37c6  box      [mscorlib]System.Int32
0x37cb  ldloc.0
0x37cc  box      [mscorlib]System.DateTime
0x37d1  call     string [mscorlib]System.String::Format(string, object, object)
0x37d6  ldc.i4.0
0x37d7  newarr   [mscorlib]System.Object
0x37dc  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x37e1  ret
```
