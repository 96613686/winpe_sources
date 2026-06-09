# Microsoft.Crm.Asynchronous.EmailConnector.MailboxTestDataAccess::UpdateOutgoingTestAccessResult

- ea: `0x76be0`
- end: `0x76f58`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxTestDataAccess::UpdateOutgoingTestAccessResult`
- size: `888`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x75790`

## callees

- `0x4dcf0`
- `0x71d00`
- `0x71e30`
- `0x71ea0`
- `0x71ec0`
- `0x76be0`
- `0x77970`
- `0x77a30`
- `0x78070`
- `0x83ab0`

## string_xrefs

- `0x76c2d`: `UPDATE MailboxBase SET`
- `0x76d60`: `OR TestEmailConfigurationRetryCount <= 1 `
- `0x76d87`: `OR TestEmailConfigurationRetryCount <= 1 `

## pseudocode

```c

```

## disassembly

```asm
0x76be0  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x76be5  stloc.0
0x76be6  ldloc.0
0x76be7  ldarg.1
0x76be8  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass1_0::mailbox
0x76bed  ldloc.0
0x76bee  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass1_0::mailbox
0x76bf3  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ProcessingResult()
0x76bf8  stloc.1
0x76bf9  ldloc.0
0x76bfa  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass1_0::mailbox
0x76bff  ldstr    aMailboxid// "mailboxid"
0x76c04  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x76c09  unbox.any [mscorlib]System.Guid
0x76c0e  stloc.2
0x76c0f  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x76c14  stloc.s  4
0x76c16  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x76c1b  stloc.s  5
0x76c1d  ldloc.s  4
0x76c1f  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x76c24  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x76c29  stloc.s  6
0x76c2b  ldloc.s  5
0x76c2d  ldstr    aUpdateMailboxb_0// "UPDATE MailboxBase SET"
0x76c32  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x76c37  pop
0x76c38  ldloc.0
0x76c39  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass1_0::mailbox
0x76c3e  ldstr    aMailboxprocess_2// "mailboxprocessingcontext"
0x76c43  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x76c48  unbox.any [mscorlib]System.Int32
0x76c4d  ldc.i4.1
0x76c4e  ceq
0x76c50  stloc.s  7
0x76c52  ldloc.1
0x76c53  brtrue   loc_76CE0
0x76c58  ldloc.s  5
0x76c5a  ldstr    aOutgoingemails_0// "OutgoingEmailStatus=@status,"
0x76c5f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x76c64  pop
0x76c65  ldloc.s  5
0x76c67  ldstr    aEnabledforoutg_1// "EnabledForOutgoingEmail = 1,"
0x76c6c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x76c71  pop
0x76c72  ldloc.s  5
0x76c74  ldstr    aTransientfailu_2// "TransientFailureCount = TransientFailur"...
0x76c79  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x76c7e  pop
0x76c7f  ldloc.s  5
0x76c81  ldstr    aPostponesendin_4// "PostponeSendingUntil = @postponeSending"...
0x76c86  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x76c8b  pop
0x76c8c  ldloc.s  6
0x76c8e  ldstr    aStatus_0// "@status"
0x76c93  ldc.i4.1
0x76c94  box      [mscorlib]System.Int32
0x76c99  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76c9e  pop
0x76c9f  ldloc.s  6
0x76ca1  ldstr    aTransienterror_1// "@transientErrorCountResetMask"
0x76ca6  ldc.i4   0xF0FFFFFF
0x76cab  box      [mscorlib]System.Int32
0x76cb0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76cb5  pop
0x76cb6  ldloc.s  6
0x76cb8  ldstr    aPostponesendin_1// "@postponeSendingUntil"
0x76cbd  ldarg.0
0x76cbe  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x76cc3  box      [mscorlib]System.DateTime
0x76cc8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76ccd  pop
0x76cce  ldc.i4.s 0x2A
0x76cd0  ldloc.0
0x76cd1  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass1_0::mailbox
0x76cd6  call     void Microsoft.Crm.Asynchronous.EmailConnector.MailboxTestAccessTraceLogger::LogInformationLevelTraceRecord(int32 traceCode, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox)
0x76cdb  br       loc_76E42
0x76ce0  ldloc.1
0x76ce1  ldc.i4.2
0x76ce2  bne.un.s loc_76D3A
0x76ce4  ldloc.s  5
0x76ce6  ldstr    aOutgoingemails_0// "OutgoingEmailStatus=@status,"
0x76ceb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x76cf0  pop
0x76cf1  ldloc.s  5
0x76cf3  ldstr    aEnabledforoutg_0// "EnabledForOutgoingEmail = 0,"
0x76cf8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x76cfd  pop
0x76cfe  ldloc.s  5
0x76d00  ldstr    aTransientfailu_5// "TransientFailureCount = TransientFailur"...
0x76d05  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x76d0a  pop
0x76d0b  ldloc.s  6
0x76d0d  ldstr    aStatus_0// "@status"
0x76d12  ldc.i4.2
0x76d13  box      [mscorlib]System.Int32
0x76d18  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76d1d  pop
0x76d1e  ldloc.s  6
0x76d20  ldstr    aTransienterror_1// "@transientErrorCountResetMask"
0x76d25  ldc.i4   0xF0FFFFFF
0x76d2a  box      [mscorlib]System.Int32
0x76d2f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76d34  pop
0x76d35  br       loc_76E42
0x76d3a  ldloc.1
0x76d3b  ldc.i4.1
0x76d3c  bne.un   loc_76E22
0x76d41  ldloc.s  5
0x76d43  ldstr    aOutgoingemails_0// "OutgoingEmailStatus=@status,"
0x76d48  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x76d4d  pop
0x76d4e  ldloc.s  5
0x76d50  ldstr    aEnabledforoutg_2// "EnabledForOutgoingEmail = CASE WHEN Tra"...
0x76d55  ldloc.s  7
0x76d57  brtrue.s loc_76D60
0x76d59  ldstr    asc_8A7C2// ""
0x76d5e  br.s     loc_76D65
0x76d60  ldstr    aOrTestemailcon// "OR TestEmailConfigurationRetryCount <= "...
0x76d65  ldstr    aThen0ElseEnabl// "THEN 0 ELSE EnabledForOutgoingEmail END"...
0x76d6a  call     string [mscorlib]System.String::Concat(string, string, string)
0x76d6f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x76d74  pop
0x76d75  ldloc.s  5
0x76d77  ldstr    aTransientfailu_6// "TransientFailureCount = CASE \r\n\t\t\t"...
0x76d7c  ldloc.s  7
0x76d7e  brtrue.s loc_76D87
0x76d80  ldstr    asc_8A7C2// ""
0x76d85  br.s     loc_76D8C
0x76d87  ldstr    aOrTestemailcon// "OR TestEmailConfigurationRetryCount <= "...
0x76d8c  ldstr    aThenTransientf// "THEN TransientFailureCount & @transient"...
0x76d91  call     string [mscorlib]System.String::Concat(string, string, string)
0x76d96  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x76d9b  pop
0x76d9c  ldloc.s  5
0x76d9e  ldstr    aOutputInserted// "OUTPUT INSERTED.TransientFailureCount"
0x76da3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x76da8  pop
0x76da9  ldloc.s  6
0x76dab  ldstr    aStatus_0// "@status"
0x76db0  ldc.i4.2
0x76db1  box      [mscorlib]System.Int32
0x76db6  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76dbb  pop
0x76dbc  ldloc.s  6
0x76dbe  ldstr    aMaxtransientfa// "@maxTransientFailureCount"
0x76dc3  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IEmailConfiguration Microsoft.Crm.Asynchronous.EmailConnector.EmailConfiguration::get_Instance()
0x76dc8  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IEmailConfiguration::get_MaximumMailboxTransientFailures()
0x76dcd  ldc.i4.s 0x18
0x76dcf  shl
0x76dd0  box      [mscorlib]System.Int32
0x76dd5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76dda  pop
0x76ddb  ldloc.s  6
0x76ddd  ldstr    aTransienterror// "@transientErrorCountMask"
0x76de2  ldc.i4   0xF000000
0x76de7  box      [mscorlib]System.Int32
0x76dec  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76df1  pop
0x76df2  ldloc.s  6
0x76df4  ldstr    aTransienterror_1// "@transientErrorCountResetMask"
0x76df9  ldc.i4   0xF0FFFFFF
0x76dfe  box      [mscorlib]System.Int32
0x76e03  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76e08  pop
0x76e09  ldloc.s  6
0x76e0b  ldstr    aTransienterror_0// "@transientErrorCountShift"
0x76e10  ldc.i4   0x1000000
0x76e15  box      [mscorlib]System.Int32
0x76e1a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76e1f  pop
0x76e20  br.s     loc_76E42
0x76e22  ldloc.s  5
0x76e24  ldstr    aOutgoingemails_1// "OutgoingEmailStatus=@status"
0x76e29  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x76e2e  pop
0x76e2f  ldloc.s  6
0x76e31  ldstr    aStatus_0// "@status"
0x76e36  ldc.i4.0
0x76e37  box      [mscorlib]System.Int32
0x76e3c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76e41  pop
0x76e42  ldloc.s  5
0x76e44  ldstr    aWhereMailboxid// "WHERE MailboxId=@mailboxId"
0x76e49  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x76e4e  pop
0x76e4f  ldloc.s  4
0x76e51  ldloc.s  5
0x76e53  callvirt instance string [mscorlib]System.Object::ToString()
0x76e58  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x76e5d  ldloc.s  6
0x76e5f  ldstr    aMailboxid_1// "@mailboxId"
0x76e64  ldloc.2
0x76e65  box      [mscorlib]System.Guid
0x76e6a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76e6f  pop
0x76e70  ldloc.1
0x76e71  ldc.i4.1
0x76e72  bne.un.s loc_76E8B
0x76e74  ldarg.0
0x76e75  ldloc.s  4
0x76e77  ldloc.0
0x76e78  ldftn    instance void <>c__DisplayClass1_0::<UpdateOutgoingTestAccessResult>b__0(object[] values)
0x76e7e  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x76e83  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x76e88  pop
0x76e89  leave.s  loc_76EA2
0x76e8b  ldarg.0
0x76e8c  ldloc.s  4
0x76e8e  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x76e93  pop
0x76e94  leave.s  loc_76EA2
0x76e96  ldloc.s  4
0x76e98  brfalse.s loc_76EA1
0x76e9a  ldloc.s  4
0x76e9c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x76ea1  endfinally
0x76ea2  ldloc.1
0x76ea3  ldc.i4.0
0x76ea4  ceq
0x76ea6  stloc.3
0x76ea7  call     class Microsoft.Crm.Asynchronous.EmailConnector.ServerSideSyncTelemetryEventSource Microsoft.Crm.Asynchronous.EmailConnector.ServerSideSyncTelemetryEventSource::get_Instance()
0x76eac  ldloc.0
0x76ead  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass1_0::mailbox
0x76eb2  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_LastSyncStartedOnForEC()
0x76eb7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x76ebc  ldloc.0
0x76ebd  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass1_0::mailbox
0x76ec2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x76ec7  ldloc.0
0x76ec8  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass1_0::mailbox
0x76ecd  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_LastSyncStartedOnForEC()
0x76ed2  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x76ed7  stloc.s  8
0x76ed9  ldloca.s 8
0x76edb  call     instance int32 [mscorlib]System.TimeSpan::get_Milliseconds()
0x76ee0  ldc.i4.0
0x76ee1  ldc.i4.0
0x76ee2  ldloc.3
0x76ee3  ldloc.1
0x76ee4  ldc.i4.0
0x76ee5  ceq
0x76ee7  ldloc.0
0x76ee8  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass1_0::mailbox
0x76eed  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x76ef2  ldstr    aLastsyncerror_0// "lastsyncerror"
0x76ef7  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x76efc  brtrue.s loc_76F05
0x76efe  ldsfld   string [mscorlib]System.String::Empty
0x76f03  br.s     loc_76F1A
0x76f05  ldloc.0
0x76f06  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass1_0::mailbox
0x76f0b  ldstr    aLastsyncerror_0// "lastsyncerror"
0x76f10  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x76f15  callvirt instance string [mscorlib]System.Object::ToString()
0x76f1a  ldloc.0
0x76f1b  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass1_0::mailbox
0x76f20  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x76f25  ldstr    aLastsyncerrorc// "lastsyncerrorcode"
0x76f2a  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x76f2f  brtrue.s loc_76F34
0x76f31  ldc.i4.0
0x76f32  br.s     loc_76F49
0x76f34  ldloc.0
0x76f35  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass1_0::mailbox
0x76f3a  ldstr    aLastsyncerrorc// "lastsyncerrorcode"
0x76f3f  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x76f44  unbox.any [mscorlib]System.Int32
0x76f49  ldc.i4.1
0x76f4a  ldc.i4.1
0x76f4b  ldc.i4.0
0x76f4c  ldarg.2
0x76f4d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x76f52  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ServerSideSyncTelemetryEventSource::GetMailboxSyncingInformation(valuetype [mscorlib]System.DateTime startTime, valuetype [mscorlib]System.DateTime completeTime, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailboxInfo, int32 testLatency, int32 numberOfItemsSynced, int32 numberOfItemsFailed, bool enabledStatus, bool processStatus, string lastSyncError, int32 lastSyncErrorCode, valuetype SyncingOperationType syncOperation, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType operationType, int32 mailboxHealthStatus, valuetype [mscorlib]System.Guid asyncEventId)
0x76f57  ret
```
