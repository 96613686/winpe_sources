# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::UpdateUserSyncVersion

- ea: `0x82b0`
- end: `0x8394`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::UpdateUserSyncVersion`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x6b10`

## callees

- `0x82b0`
- `0x8840`
- `0x8ab0`
- `0x16390`
- `0x163e0`

## string_xrefs

- `0x82b6`: `MethodUpdateUserSyncVersion`
- `0x8389`: `MethodUpdateUserSyncVersion`
- `0x82e6`: `UPDATE UserSettingsBase SET`

## pseudocode

```c

```

## disassembly

```asm
0x82b0  ldarg.0
0x82b1  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x82b6  ldstr    aMethodupdateus// "MethodUpdateUserSyncVersion"
0x82bb  callvirt instance void Metrics::StartTimer(string name)
0x82c0  ldarg.1
0x82c1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x82c6  stloc.0
0x82c7  ldarg.1
0x82c8  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x82cd  stloc.1
0x82ce  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x82d3  stloc.3
0x82d4  ldloc.1
0x82d5  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x82da  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x82df  dup
0x82e0  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x82e5  ldloc.3
0x82e6  ldstr    aUpdateUsersett// "UPDATE UserSettingsBase SET"
0x82eb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x82f0  pop
0x82f1  ldloc.3
0x82f2  ldstr    aResourcebookin_2// "ResourceBookingExchangeSyncVersion = @l"...
0x82f7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x82fc  pop
0x82fd  ldloc.3
0x82fe  ldstr    aWhereSystemuse// "WHERE SystemUserId = @systemUserId"
0x8303  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x8308  pop
0x8309  ldloc.3
0x830a  ldstr    aAndResourceboo// "AND ResourceBookingExchangeSyncVersion "...
0x830f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x8314  pop
0x8315  dup
0x8316  ldstr    aLastsyncedvers// "@lastSyncedVersionNumber"
0x831b  ldarg.3
0x831c  box      [mscorlib]System.Int64
0x8321  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8326  pop
0x8327  ldstr    aSystemuserid// "@systemUserId"
0x832c  ldarga.s 2
0x832e  constrained. [mscorlib]System.Guid
0x8334  callvirt instance string [mscorlib]System.Object::ToString()
0x8339  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x833e  pop
0x833f  ldc.i4.8
0x8340  stloc.2
0x8341  ldloc.1
0x8342  ldloc.3
0x8343  callvirt instance string [mscorlib]System.Object::ToString()
0x8348  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x834d  ldarg.0
0x834e  ldloc.0
0x834f  ldloc.1
0x8350  ldloc.2
0x8351  call     instance int32 Microsoft.Crm.Asynchronous.ResourceBookingSyncService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype DatabaseTransactionType databaseTransactionType)
0x8356  pop
0x8357  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x835c  ldarg.2
0x835d  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x8362  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x8367  ldc.i4.1
0x8368  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::RemoveEntry(var<u1>, !!T0, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x836d  leave.s  loc_8383
0x836f  ldloc.1
0x8370  brfalse.s loc_8378
0x8372  ldloc.1
0x8373  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8378  endfinally
0x8379  ldloc.0
0x837a  brfalse.s loc_8382
0x837c  ldloc.0
0x837d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8382  endfinally
0x8383  ldarg.0
0x8384  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8389  ldstr    aMethodupdateus// "MethodUpdateUserSyncVersion"
0x838e  callvirt instance void Metrics::StopTimer(string name)
0x8393  ret
```
