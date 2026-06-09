# <>c__DisplayClass20_0::<CleanUpExpiredSubscriptions>b__0

- ea: `0xa9bd0`
- end: `0xa9ede`
- name: `<>c__DisplayClass20_0::<CleanUpExpiredSubscriptions>b__0`
- size: `782`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task`

## callees

- `0x24e0`
- `0xaf40`
- `0xaf50`
- `0xaff0`
- `0xa9bd0`

## string_xrefs

- `0xa9c76`: `D:\a\1\s\src\ManagedPlatform\SDK\DeletionService\DeletionService.cs`
- `0xa9be3`: `DeletionService: Inside DeletionService.CleanUpExpiredSubscriptions`
- `0xa9c08`: `DeletionService: Inside DeletionService.CleanUpExpiredSubscriptions`
- `0xa9ce4`: `DeletionService: {0} SubscriptionId(s) found in table Subscription to delete based on LastSyncStartedOn`
- `0xa9d17`: `DeletionService: {0} SubscriptionId(s) found in table Subscription to delete based on LastSyncStartedOn`
- `0xa9d79`: `DeletionService: Deletion Service deleted expired subscription {0}.`
- `0xa9dcd`: `DeletionService: Deletion Service deleted expired subscription {0}.`
- `0xa9dfc`: `DeletionService: Deletion Service deleted expired subscription {0}.`
- `0xa9e43`: `DeletionService: SubscriptionId {0} ; Exception : {1}`
- `0xa9e81`: `DeletionService: SubscriptionId {0} ; Exception : {1}`

## pseudocode

```c

```

## disassembly

```asm
0xa9bd0  ldsfld   string [mscorlib]System.String::Empty
0xa9bd5  stloc.0
0xa9bd6  ldarg.0
0xa9bd7  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass20_0::<>4__this
0xa9bdc  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa9be1  ldc.i4.s 0x14
0xa9be3  ldstr    aDeletionservic_75// "DeletionService: Inside DeletionService"...
0xa9be8  ldc.i4.0
0xa9be9  newarr   [mscorlib]System.Object
0xa9bee  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa9bf3  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0xa9bf8  ldarg.0
0xa9bf9  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass20_0::<>4__this
0xa9bfe  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa9c03  ldstr    aCleanupexpired// "CleanUpExpiredSubscriptions"
0xa9c08  ldstr    aDeletionservic_75// "DeletionService: Inside DeletionService"...
0xa9c0d  ldc.i4.0
0xa9c0e  ldc.i4.0
0xa9c0f  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0xa9c14  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xa9c19  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xa9c1e  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xa9c23  ldc.i4.0
0xa9c24  ldsfld   string [mscorlib]System.String::Empty
0xa9c29  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0xa9c2e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::.ctor()
0xa9c33  stloc.1
0xa9c34  ldarg.0
0xa9c35  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass20_0::<>4__this
0xa9c3a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa9c3f  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xa9c44  ldc.i4.0
0xa9c45  ldc.i4.0
0xa9c46  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xa9c4b  stloc.2
0xa9c4c  ldloc.2
0xa9c4d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xa9c52  ldloc.2
0xa9c53  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0xa9c58  stloc.3
0xa9c59  ldloc.3
0xa9c5a  ldstr    aDeclareExpires_1// "DECLARE @expireSubscriptionInDays int\r"...
0xa9c5f  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xa9c64  ldloc.3
0xa9c65  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0xa9c6a  stloc.0
0xa9c6b  ldloc.3
0xa9c6c  ldc.i4   0x213
0xa9c71  ldstr    aCleanupexpired// "CleanUpExpiredSubscriptions"
0xa9c76  ldstr    aDA1SSrcManaged// "D:\\a\\1\\s\\src\\ManagedPlatform\\SDK"...
0xa9c7b  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xa9c80  stloc.s  4
0xa9c82  br.s     loc_A9CAC
0xa9c84  ldloc.1
0xa9c85  ldloc.s  4
0xa9c87  ldstr    aSubscriptionid// "SubscriptionId"
0xa9c8c  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xa9c91  unbox.any [mscorlib]System.Guid
0xa9c96  ldloc.s  4
0xa9c98  ldstr    aSystemuserid_0// "SystemUserId"
0xa9c9d  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xa9ca2  unbox.any [mscorlib]System.Guid
0xa9ca7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0xa9cac  ldloc.s  4
0xa9cae  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xa9cb3  brtrue.s loc_A9C84
0xa9cb5  leave.s  loc_A9CD7
0xa9cb7  ldloc.s  4
0xa9cb9  brfalse.s loc_A9CC2
0xa9cbb  ldloc.s  4
0xa9cbd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa9cc2  endfinally
0xa9cc3  ldloc.3
0xa9cc4  brfalse.s loc_A9CCC
0xa9cc6  ldloc.3
0xa9cc7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa9ccc  endfinally
0xa9ccd  ldloc.2
0xa9cce  brfalse.s loc_A9CD6
0xa9cd0  ldloc.2
0xa9cd1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa9cd6  endfinally
0xa9cd7  ldarg.0
0xa9cd8  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass20_0::<>4__this
0xa9cdd  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa9ce2  ldc.i4.s 0x14
0xa9ce4  ldstr    aDeletionservic_76// "DeletionService: {0} SubscriptionId(s) "...
0xa9ce9  ldc.i4.1
0xa9cea  newarr   [mscorlib]System.Object
0xa9cef  dup
0xa9cf0  ldc.i4.0
0xa9cf1  ldloc.1
0xa9cf2  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Count()
0xa9cf7  box      [mscorlib]System.Int32
0xa9cfc  stelem.ref
0xa9cfd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa9d02  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0xa9d07  ldarg.0
0xa9d08  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass20_0::<>4__this
0xa9d0d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa9d12  ldstr    aCleanupexpired// "CleanUpExpiredSubscriptions"
0xa9d17  ldstr    aDeletionservic_76// "DeletionService: {0} SubscriptionId(s) "...
0xa9d1c  ldloc.1
0xa9d1d  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Count()
0xa9d22  box      [mscorlib]System.Int32
0xa9d27  call     string [mscorlib]System.String::Format(string, object)
0xa9d2c  ldc.i4.0
0xa9d2d  ldc.i4.m1
0xa9d2e  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0xa9d33  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xa9d38  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xa9d3d  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xa9d42  ldc.i4.0
0xa9d43  ldloc.0
0xa9d44  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0xa9d49  ldloc.1
0xa9d4a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Keys()
0xa9d4f  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::GetEnumerator()
0xa9d54  stloc.s  5
0xa9d56  br       loc_A9EC1
0xa9d5b  ldloca.s 5
0xa9d5d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Current()
0xa9d62  stloc.s  6
0xa9d64  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0xa9d69  ldarg.0
0xa9d6a  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass20_0::<>4__this
0xa9d6f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa9d74  ldstr    aCleanupexpired// "CleanUpExpiredSubscriptions"
0xa9d79  ldstr    aDeletionservic_77// "DeletionService: Deletion Service delet"...
0xa9d7e  ldloc.s  6
0xa9d80  box      [mscorlib]System.Guid
0xa9d85  call     string [mscorlib]System.String::Format(string, object)
0xa9d8a  ldc.i4.0
0xa9d8b  ldc.i4.0
0xa9d8c  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0xa9d91  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xa9d96  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xa9d9b  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xa9da0  ldc.i4.0
0xa9da1  ldsfld   string [mscorlib]System.String::Empty
0xa9da6  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0xa9dab  ldarg.0
0xa9dac  ldfld    class Microsoft.Crm.IDeletionServiceProvider <>c__DisplayClass20_0::deletionServiceProvider
0xa9db1  ldloc.s  6
0xa9db3  ldloc.1
0xa9db4  ldloc.s  6
0xa9db6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Item(void)
0xa9dbb  callvirt instance void Microsoft.Crm.IDeletionServiceProvider::DeleteSubscription(valuetype [mscorlib]System.Guid subscriptionId, valuetype [mscorlib]System.Guid userId)
0xa9dc0  ldarg.0
0xa9dc1  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass20_0::<>4__this
0xa9dc6  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa9dcb  ldc.i4.s 0x14
0xa9dcd  ldstr    aDeletionservic_77// "DeletionService: Deletion Service delet"...
0xa9dd2  ldc.i4.1
0xa9dd3  newarr   [mscorlib]System.Object
0xa9dd8  dup
0xa9dd9  ldc.i4.0
0xa9dda  ldloc.s  6
0xa9ddc  box      [mscorlib]System.Guid
0xa9de1  stelem.ref
0xa9de2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa9de7  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0xa9dec  ldarg.0
0xa9ded  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass20_0::<>4__this
0xa9df2  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa9df7  ldstr    aCleanupexpired// "CleanUpExpiredSubscriptions"
0xa9dfc  ldstr    aDeletionservic_77// "DeletionService: Deletion Service delet"...
0xa9e01  ldloc.s  6
0xa9e03  box      [mscorlib]System.Guid
0xa9e08  call     string [mscorlib]System.String::Format(string, object)
0xa9e0d  ldc.i4.0
0xa9e0e  ldc.i4.m1
0xa9e0f  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0xa9e14  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xa9e19  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xa9e1e  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xa9e23  ldc.i4.1
0xa9e24  ldsfld   string [mscorlib]System.String::Empty
0xa9e29  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0xa9e2e  leave    loc_A9EC1
0xa9e33  stloc.s  7
0xa9e35  ldnull
0xa9e36  ldarg.0
0xa9e37  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass20_0::<>4__this
0xa9e3c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa9e41  ldc.i4.s 0x15
0xa9e43  ldstr    aDeletionservic_78// "DeletionService: SubscriptionId {0} ; E"...
0xa9e48  ldc.i4.2
0xa9e49  newarr   [mscorlib]System.Object
0xa9e4e  dup
0xa9e4f  ldc.i4.0
0xa9e50  ldloc.s  6
0xa9e52  box      [mscorlib]System.Guid
0xa9e57  stelem.ref
0xa9e58  dup
0xa9e59  ldc.i4.1
0xa9e5a  ldloc.s  7
0xa9e5c  callvirt instance string [mscorlib]System.Object::ToString()
0xa9e61  stelem.ref
0xa9e62  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa9e67  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0xa9e6c  ldarg.0
0xa9e6d  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass20_0::<>4__this
0xa9e72  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa9e77  ldstr    aCleanupexpired// "CleanUpExpiredSubscriptions"
0xa9e7c  ldsfld   string [mscorlib]System.String::Empty
0xa9e81  ldstr    aDeletionservic_78// "DeletionService: SubscriptionId {0} ; E"...
0xa9e86  ldloc.s  6
0xa9e88  box      [mscorlib]System.Guid
0xa9e8d  ldloc.s  7
0xa9e8f  callvirt instance string [mscorlib]System.Object::ToString()
0xa9e94  call     string [mscorlib]System.String::Format(string, object, object)
0xa9e99  ldc.i4.0
0xa9e9a  ldc.i4.m1
0xa9e9b  call     string [mscorlib]System.Environment::get_StackTrace()
0xa9ea0  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0xa9ea5  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xa9eaa  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xa9eaf  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xa9eb4  ldc.i4.0
0xa9eb5  ldsfld   string [mscorlib]System.String::Empty
0xa9eba  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceError(valuetype [mscorlib]System.Guid organizationId, string moduleName, string crmTraceMessage, string errorMessage, int32 recordsDeleted, int32 durationInSecs, string stackTrace, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0xa9ebf  leave.s  loc_A9EC1
0xa9ec1  ldloca.s 5
0xa9ec3  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::MoveNext()
0xa9ec8  brtrue   loc_A9D5B
0xa9ecd  leave.s  loc_A9EDD
0xa9ecf  ldloca.s 5
0xa9ed1  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>
0xa9ed7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa9edc  endfinally
0xa9edd  ret
```
