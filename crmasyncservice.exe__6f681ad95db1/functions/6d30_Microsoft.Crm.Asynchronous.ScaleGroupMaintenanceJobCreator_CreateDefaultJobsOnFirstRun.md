# Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobCreator::CreateDefaultJobsOnFirstRun

- ea: `0x6d30`
- end: `0x6dac`
- name: `Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobCreator::CreateDefaultJobsOnFirstRun`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x6d30`

## string_xrefs

- `0x6d30`: `MaintenanceJobsVersionUpdate`
- `0x6d71`: `CreateDefaultJobsOnFirstRun`
- `0x6d76`: `d:\dbs\sh\dccm2\1101_190851\cmd\34\src\Core\ObjectModel\Async\AsyncService\ScalegroupMaintenanceJobs\ScalegroupMaintenanceJobCreator.cs`

## pseudocode

```c

```

## disassembly

```asm
0x6d30  ldstr    aMaintenancejob// "MaintenanceJobsVersionUpdate"
0x6d35  ldc.i4.0
0x6d36  ldc.i4.1
0x6d37  ldc.i4.0
0x6d38  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IConfigDBLock [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigDBLock::NewLock(string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope, int32)
0x6d3d  stloc.0
0x6d3e  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0x6d43  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0x6d48  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService(valuetype [mscorlib]System.Guid)
0x6d4d  stloc.1
0x6d4e  ldloc.1
0x6d4f  ldc.i4.1
0x6d50  callvirt instance class [System.Data]System.Data.IDbConnection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::NewConnection(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope)
0x6d55  stloc.2
0x6d56  ldloc.2
0x6d57  callvirt instance void [System.Data]System.Data.IDbConnection::Open()
0x6d5c  ldloc.2
0x6d5d  callvirt instance class [System.Data]System.Data.IDbCommand [System.Data]System.Data.IDbConnection::CreateCommand()
0x6d62  stloc.3
0x6d63  ldloc.3
0x6d64  ldstr    aIfExistsSelect_1// "\r\n\t\t\tif exists (select * from sys."...
0x6d69  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6d6e  ldloc.3
0x6d6f  ldc.i4.s 0x17
0x6d71  ldstr    aCreatedefaultj// "CreateDefaultJobsOnFirstRun"
0x6d76  ldstr    aDDbsShDccm2110_2// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x6d7b  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x6d80  pop
0x6d81  leave.s  loc_6DAB
0x6d83  ldloc.3
0x6d84  brfalse.s loc_6D8C
0x6d86  ldloc.3
0x6d87  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d8c  endfinally
0x6d8d  ldloc.2
0x6d8e  brfalse.s loc_6D96
0x6d90  ldloc.2
0x6d91  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d96  endfinally
0x6d97  ldloc.1
0x6d98  brfalse.s loc_6DA0
0x6d9a  ldloc.1
0x6d9b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6da0  endfinally
0x6da1  ldloc.0
0x6da2  brfalse.s loc_6DAA
0x6da4  ldloc.0
0x6da5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6daa  endfinally
0x6dab  ret
```
