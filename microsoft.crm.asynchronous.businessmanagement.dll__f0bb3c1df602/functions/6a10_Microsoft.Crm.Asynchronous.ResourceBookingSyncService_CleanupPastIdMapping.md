# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::CleanupPastIdMapping

- ea: `0x6a10`
- end: `0x6b0a`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::CleanupPastIdMapping`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x8b60`

## callees

- `0x6a10`
- `0x8840`
- `0x8ab0`
- `0x13d90`
- `0x157e0`
- `0x157f0`
- `0x16390`
- `0x163e0`

## string_xrefs

- `0x6a6a`: `DELETE CLEANUP_IDMAPPING FROM BookableResourceBookingExchangeSyncIdMappingBase CLEANUP_IDMAPPING`

## pseudocode

```c

```

## disassembly

```asm
0x6a10  ldarg.0
0x6a11  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6a16  ldstr    aMethodcleanupp// "MethodCleanupPastIdMapping"
0x6a1b  callvirt instance void Metrics::StartTimer(string name)
0x6a20  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x6a25  ldc.i4.0
0x6a26  ldc.i4.0
0x6a27  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x6a2c  stloc.0
0x6a2d  ldloc.0
0x6a2e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x6a33  ldarg.1
0x6a34  ldloc.0
0x6a35  callvirt instance void SyncConfig::set_DbConnection(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection value)
0x6a3a  ldarg.1
0x6a3b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection SyncConfig::get_DbConnection()
0x6a40  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x6a45  stloc.1
0x6a46  ldarg.1
0x6a47  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection SyncConfig::get_DbConnection()
0x6a4c  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x6a51  stloc.2
0x6a52  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x6a57  stloc.3
0x6a58  ldloc.2
0x6a59  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x6a5e  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x6a63  dup
0x6a64  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x6a69  ldloc.3
0x6a6a  ldstr    aDeleteCleanupI// "DELETE CLEANUP_IDMAPPING FROM BookableR"...
0x6a6f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x6a74  pop
0x6a75  ldloc.3
0x6a76  ldstr    aJoinBookablere// "JOIN BookableResourceBookingBase"
0x6a7b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x6a80  pop
0x6a81  ldloc.3
0x6a82  ldstr    aOnBookablereso// "ON BookableResourceBookingBase.Bookable"...
0x6a87  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x6a8c  pop
0x6a8d  ldloc.3
0x6a8e  ldstr    aWhereBookabler_1// "WHERE BookableResourceBookingBase.Start"...
0x6a93  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x6a98  pop
0x6a99  ldstr    aUpperbounddate// "@upperBoundDateTime"
0x6a9e  ldarg.0
0x6a9f  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x6aa4  callvirt instance valuetype [mscorlib]System.DateTime ConfigurationSettings::get_UpperBoundDateTimeForCleanupIdMapping()
0x6aa9  box      [mscorlib]System.DateTime
0x6aae  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6ab3  pop
0x6ab4  ldloc.2
0x6ab5  ldloc.3
0x6ab6  callvirt instance string [mscorlib]System.Object::ToString()
0x6abb  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6ac0  ldarg.0
0x6ac1  ldloc.1
0x6ac2  ldloc.2
0x6ac3  ldc.i4.s 0xA
0x6ac5  call     instance int32 Microsoft.Crm.Asynchronous.ResourceBookingSyncService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype DatabaseTransactionType databaseTransactionType)
0x6aca  pop
0x6acb  leave.s  loc_6AF9
0x6acd  ldloc.2
0x6ace  brfalse.s loc_6AD6
0x6ad0  ldloc.2
0x6ad1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6ad6  endfinally
0x6ad7  ldloc.1
0x6ad8  brfalse.s loc_6AE0
0x6ada  ldloc.1
0x6adb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6ae0  endfinally
0x6ae1  ldloc.0
0x6ae2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x6ae7  ldarg.1
0x6ae8  ldnull
0x6ae9  callvirt instance void SyncConfig::set_DbConnection(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection value)
0x6aee  endfinally
0x6aef  ldloc.0
0x6af0  brfalse.s loc_6AF8
0x6af2  ldloc.0
0x6af3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6af8  endfinally
0x6af9  ldarg.0
0x6afa  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6aff  ldstr    aMethodcleanupp// "MethodCleanupPastIdMapping"
0x6b04  callvirt instance void Metrics::StopTimer(string name)
0x6b09  ret
```
