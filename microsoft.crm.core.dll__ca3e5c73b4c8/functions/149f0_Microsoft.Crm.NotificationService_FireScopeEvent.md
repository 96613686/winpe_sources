# Microsoft.Crm.NotificationService::FireScopeEvent

- ea: `0x149f0`
- end: `0x14b5c`
- name: `Microsoft.Crm.NotificationService::FireScopeEvent`
- size: `364`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x127b0`
- `0x14960`

## callees

- `0x1f80`
- `0xdab0`
- `0x132c0`
- `0x149f0`
- `0x14b60`
- `0x4af90`
- `0x4d810`
- `0x4e640`
- `0x64bd0`
- `0x64bf0`

## string_xrefs

- `0x14a75`: `D:\a\1\s\src\Platform\Core\DataServices\Notification\NotificationService.cs`
- `0x14a8e`: `D:\a\1\s\src\Platform\Core\DataServices\Notification\NotificationService.cs`
- `0x14af1`: `Host:{0}. ProcessName:{1}. Notification created in datacenter:{2}. OrganizationId:{3}, EventData:{4}, EventId:{5}, CallerStackTrace:{6}.`
- `0x14b4f`: `CreateNotification`

## pseudocode

```c

```

## disassembly

```asm
0x149f0  ldarg.s  4
0x149f2  call     class Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService(valuetype Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x149f7  stloc.0
0x149f8  ldarg.s  5
0x149fa  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x149ff  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x14a04  brfalse.s loc_14A0E
0x14a06  ldloc.0
0x14a07  ldarg.s  5
0x14a09  callvirt instance void Microsoft.Crm.SharedDatabase.IDatabaseService::set_DatacenterId(valuetype [mscorlib]System.Guid value)
0x14a0e  ldloc.0
0x14a0f  ldarg.0
0x14a10  callvirt instance class [System.Data]System.Data.IDbConnection Microsoft.Crm.SharedDatabase.IDatabaseService::NewConnection(valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope)
0x14a15  stloc.1
0x14a16  ldloc.1
0x14a17  callvirt instance void [System.Data]System.Data.IDbConnection::Open()
0x14a1c  ldloc.1
0x14a1d  callvirt instance class [System.Data]System.Data.IDbCommand [System.Data]System.Data.IDbConnection::CreateCommand()
0x14a22  stloc.2
0x14a23  ldloc.2
0x14a24  ldarg.0
0x14a25  call     string Microsoft.Crm.NotificationService::GetBaseNotificationInsertSql(valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope)
0x14a2a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x14a2f  ldloc.2
0x14a30  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x14a35  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x14a3a  dup
0x14a3b  ldstr    aOrganizationid_2// "@OrganizationId"
0x14a40  ldarg.3
0x14a41  box      [mscorlib]System.Guid
0x14a46  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x14a4b  pop
0x14a4c  dup
0x14a4d  ldstr    aEventdata_0// "@EventData"
0x14a52  ldarg.2
0x14a53  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x14a58  pop
0x14a59  ldstr    aEventid_0// "@EventId"
0x14a5e  ldarg.1
0x14a5f  box      Microsoft.Crm.NotificationEventType
0x14a64  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x14a69  pop
0x14a6a  ldloc.2
0x14a6b  ldc.i4   0x97
0x14a70  ldstr    aFirescopeevent// "FireScopeEvent"
0x14a75  ldstr    aDA1SSrcPlatfor_9// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x14a7a  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x14a7f  pop
0x14a80  leave.s  loc_14A9B
0x14a82  pop
0x14a83  ldloc.2
0x14a84  ldc.i4   0x9D
0x14a89  ldstr    aFirescopeevent// "FireScopeEvent"
0x14a8e  ldstr    aDA1SSrcPlatfor_9// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x14a93  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x14a98  pop
0x14a99  leave.s  loc_14A9B
0x14a9b  ldc.i4.1
0x14a9c  ldarg.0
0x14a9d  ldloc.2
0x14a9e  call     void Microsoft.Crm.NotificationInstrumentation::LogResult(valuetype Microsoft.Crm.InstrumentationOperationType operationType, valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope, class [System.Data]System.Data.IDbCommand command)
0x14aa3  leave.s  loc_14AC3
0x14aa5  ldloc.2
0x14aa6  brfalse.s loc_14AAE
0x14aa8  ldloc.2
0x14aa9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14aae  endfinally
0x14aaf  ldloc.1
0x14ab0  brfalse.s loc_14AB8
0x14ab2  ldloc.1
0x14ab3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14ab8  endfinally
0x14ab9  ldloc.0
0x14aba  brfalse.s loc_14AC2
0x14abc  ldloc.0
0x14abd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14ac2  endfinally
0x14ac3  ldarg.0
0x14ac4  brfalse.s loc_14ACD
0x14ac6  ldarg.0
0x14ac7  ldc.i4.2
0x14ac8  bne.un   loc_14B5B
0x14acd  ldarg.1
0x14ace  ldc.i4.s 0x17
0x14ad0  bne.un   loc_14B5B
0x14ad5  ldarg.2
0x14ad6  ldstr    aServersettings// "ServerSettings"
0x14adb  ldc.i4.5
0x14adc  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x14ae1  ldc.i4.m1
0x14ae2  beq.s    loc_14B5B
0x14ae4  ldc.i4.2
0x14ae5  call     valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.BootstrapService::GetSku()
0x14aea  bne.un.s loc_14B5B
0x14aec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14af1  ldstr    aHost0Processna// "Host:{0}. ProcessName:{1}. Notification"...
0x14af6  ldc.i4.7
0x14af7  newarr   [mscorlib]System.Object
0x14afc  dup
0x14afd  ldc.i4.0
0x14afe  call     string [mscorlib]System.Environment::get_MachineName()
0x14b03  stelem.ref
0x14b04  dup
0x14b05  ldc.i4.1
0x14b06  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x14b0b  callvirt instance string [System]System.Diagnostics.Process::get_ProcessName()
0x14b10  stelem.ref
0x14b11  dup
0x14b12  ldc.i4.2
0x14b13  ldarg.s  5
0x14b15  box      [mscorlib]System.Guid
0x14b1a  stelem.ref
0x14b1b  dup
0x14b1c  ldc.i4.3
0x14b1d  ldarg.3
0x14b1e  box      [mscorlib]System.Guid
0x14b23  stelem.ref
0x14b24  dup
0x14b25  ldc.i4.4
0x14b26  ldarg.2
0x14b27  stelem.ref
0x14b28  dup
0x14b29  ldc.i4.5
0x14b2a  ldarg.1
0x14b2b  box      Microsoft.Crm.NotificationEventType
0x14b30  stelem.ref
0x14b31  dup
0x14b32  ldc.i4.6
0x14b33  newobj   instance void [mscorlib]System.Diagnostics.StackTrace::.ctor()
0x14b38  callvirt instance string [mscorlib]System.Object::ToString()
0x14b3d  stelem.ref
0x14b3e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14b43  stloc.3
0x14b44  call     class Microsoft.Crm.ConfigurationDatabase.IAuditHistory Microsoft.Crm.ConfigurationDatabase.AuditHistory::NewService()
0x14b49  ldarg.3
0x14b4a  ldstr    aOrganizationId// "Organization.Id"
0x14b4f  ldstr    aCreatenotifica// "CreateNotification"
0x14b54  ldloc.3
0x14b55  ldc.i4.1
0x14b56  callvirt instance void Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CreateCompletedEntry(valuetype [mscorlib]System.Guid objectId, string objectType, string operation, string details, bool succeeded)
0x14b5b  ret
```
