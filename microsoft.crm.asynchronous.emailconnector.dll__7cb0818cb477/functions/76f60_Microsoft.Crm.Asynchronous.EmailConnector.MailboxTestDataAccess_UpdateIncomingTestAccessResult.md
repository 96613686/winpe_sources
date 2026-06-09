# Microsoft.Crm.Asynchronous.EmailConnector.MailboxTestDataAccess::UpdateIncomingTestAccessResult

- ea: `0x76f60`
- end: `0x7755c`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxTestDataAccess::UpdateIncomingTestAccessResult`
- size: `1532`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x75500`

## callees

- `0x411e0`
- `0x413a0`
- `0x4dcf0`
- `0x71cf0`
- `0x71d00`
- `0x71e30`
- `0x71ea0`
- `0x71ec0`
- `0x73eb0`
- `0x76f60`
- `0x77930`
- `0x77970`
- `0x77a30`
- `0x78070`
- `0x83af0`
- `0x83b70`

## string_xrefs

- `0x77023`: `UPDATE MailboxBase SET`
- `0x7724e`: `OR TestEmailConfigurationRetryCount <= 1 `
- `0x77274`: `OR TestEmailConfigurationRetryCount <= 1 `
- `0x76f9a`: `postponetestemailconfigurationuntil`
- `0x7708a`: `TestMailboxAccessCompletedOn=@time,`
- `0x77097`: `PostponeTestEmailConfigurationUntil = \n					CASE WHEN PostponeTestEmailConfigurationUntil <= @dequeuedPostponeTestAccessUntil \n					THEN @postponeTestAccessUntil ELSE PostponeTestEmailConfigurationUntil END,`
- `0x770a4`: `TestEmailConfigurationScheduled = \n					CASE WHEN PostponeTestEmailConfigurationUntil <= @dequeuedPostponeTestAccessUntil AND \n						((OutgoingEmailStatus <> @failedStatus AND @status <> @failedStatus) OR \n							TestEmailConfigurationRetryCount <= 1) \n					THEN 0 ELSE TestEmailConfigurationScheduled END,`
- `0x770b1`: `TestEmailConfigurationRetryCount = \n					CASE WHEN PostponeTestEmailConfigurationUntil > @dequeuedPostponeTestAccessUntil THEN TestEmailConfigurationRetryCount\n						ELSE CASE WHEN ((OutgoingEmailStatus <> @failedStatus AND @status <> @failedStatus) OR \n							TestEmailConfigurationRetryCount <= 1) \n					THEN 0 ELSE TestEmailConfigurationRetryCount - 1 END END,`
- `0x770c1`: `MailboxProcessingContext = \n						CASE WHEN (OutgoingEmailStatus <> @failedStatus AND @status <> @failedStatus) OR \n							TestEmailConfigurationRetryCount <= 1 \n					THEN @normalContext ELSE MailboxProcessingContext END,`
- `0x770e1`: `IncomingEmailStatus=@status`
- `0x77105`: `@dequeuedPostponeTestAccessUntil`
- `0x77118`: `@postponeTestAccessUntil`
- `0x7717a`: `, EnabledForIncomingEmail = 1,`
- `0x771f7`: `, EnabledForIncomingEmail = 0,`
- `0x7723f`: `, EnabledForIncomingEmail = CASE WHEN TransientFailureCount & @transientErrorCountMask = @maxTransientFailureCount `
- `0x77253`: `THEN 0 ELSE EnabledForIncomingEmail END,`
- `0x77265`: `TransientFailureCount = CASE \n						WHEN TransientFailureCount & @transientErrorCountMask = @maxTransientFailureCount OR EnabledForIncomingEmail = 0 `
- `0x7730c`: `INSERTED.EnabledForIncomingEmail`
- `0x77319`: `,INSERTED.TestEmailConfigurationScheduled`
- `0x77326`: `,INSERTED.PostponeTestEmailConfigurationUntil`

## pseudocode

```c

```

## disassembly

```asm
0x76f60  newobj   instance void <>c__DisplayClass2_1::.ctor()
0x76f65  stloc.0
0x76f66  ldloc.0
0x76f67  ldarg.1
0x76f68  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass2_1::mailbox
0x76f6d  ldloc.0
0x76f6e  ldloc.0
0x76f6f  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass2_1::mailbox
0x76f74  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ProcessingResult()
0x76f79  stfld    valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult <>c__DisplayClass2_1::result
0x76f7e  ldloc.0
0x76f7f  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass2_1::mailbox
0x76f84  ldstr    aMailboxid// "mailboxid"
0x76f89  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x76f8e  unbox.any [mscorlib]System.Guid
0x76f93  stloc.1
0x76f94  ldloc.0
0x76f95  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass2_1::mailbox
0x76f9a  ldstr    aPostponetestem// "postponetestemailconfigurationuntil"
0x76f9f  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x76fa4  unbox.any [mscorlib]System.DateTime
0x76fa9  stloc.2
0x76faa  ldloc.0
0x76fab  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_Now()
0x76fb0  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0x76fb5  stloc.s  7
0x76fb7  ldloca.s 7
0x76fb9  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IEmailConfiguration Microsoft.Crm.Asynchronous.EmailConnector.EmailConfiguration::get_Instance()
0x76fbe  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IEmailConfiguration::get_TestEmailConfigurationRetryInterval()
0x76fc3  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0x76fc8  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass2_1::postponeTestAccessUntil
0x76fcd  ldloc.0
0x76fce  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass2_1::mailbox
0x76fd3  ldstr    aMailboxprocess_2// "mailboxprocessingcontext"
0x76fd8  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x76fdd  unbox.any [mscorlib]System.Int32
0x76fe2  ldc.i4.1
0x76fe3  ceq
0x76fe5  stloc.3
0x76fe6  ldloc.0
0x76fe7  ldfld    valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult <>c__DisplayClass2_1::result
0x76fec  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxAccessStatus Microsoft.Crm.Asynchronous.EmailConnector.MailboxTestDataAccess::GetStatus(valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult result)
0x76ff1  stloc.s  4
0x76ff3  ldnull
0x76ff4  stloc.s  5
0x76ff6  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x76ffb  stloc.s  8
0x76ffd  newobj   instance void <>c__DisplayClass2_0::.ctor()
0x77002  stloc.s  9
0x77004  ldloc.s  9
0x77006  ldloc.0
0x77007  stfld    class <>c__DisplayClass2_1 <>c__DisplayClass2_0::CS$<>8__locals1
0x7700c  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x77011  stloc.s  0xA
0x77013  ldloc.s  8
0x77015  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x7701a  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x7701f  stloc.s  0xB
0x77021  ldloc.s  0xA
0x77023  ldstr    aUpdateMailboxb_0// "UPDATE MailboxBase SET"
0x77028  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7702d  pop
0x7702e  ldarg.0
0x7702f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x77034  call     bool Microsoft.Crm.Asynchronous.EmailConnector.Utility::IsDbDeployedGreaterThanOrEqualToCarina(valuetype [mscorlib]System.Guid organizationId)
0x77039  brfalse.s loc_77088
0x7703b  ldloc.s  9
0x7703d  ldfld    class <>c__DisplayClass2_1 <>c__DisplayClass2_0::CS$<>8__locals1
0x77042  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass2_1::mailbox
0x77047  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x7704c  ldstr    aFolderhierarch// "folderhierarchy"
0x77051  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x77056  brfalse.s loc_77088
0x77058  ldloc.s  0xA
0x7705a  ldstr    aFolderhierarch_0// "FolderHierarchy=@folderHierarchy,"
0x7705f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x77064  pop
0x77065  ldloc.s  0xB
0x77067  ldstr    aFolderhierarch_1// "@folderHierarchy"
0x7706c  ldloc.s  9
0x7706e  ldfld    class <>c__DisplayClass2_1 <>c__DisplayClass2_0::CS$<>8__locals1
0x77073  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass2_1::mailbox
0x77078  ldstr    aFolderhierarch// "folderhierarchy"
0x7707d  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x77082  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x77087  pop
0x77088  ldloc.s  0xA
0x7708a  ldstr    aTestmailboxacc// "TestMailboxAccessCompletedOn=@time,"
0x7708f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x77094  pop
0x77095  ldloc.s  0xA
0x77097  ldstr    aPostponetestem_0// "PostponeTestEmailConfigurationUntil = "...
0x7709c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x770a1  pop
0x770a2  ldloc.s  0xA
0x770a4  ldstr    aTestemailconfi// "TestEmailConfigurationScheduled = \r\n"...
0x770a9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x770ae  pop
0x770af  ldloc.s  0xA
0x770b1  ldstr    aTestemailconfi_0// "TestEmailConfigurationRetryCount = \r\n"...
0x770b6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x770bb  pop
0x770bc  ldloc.3
0x770bd  brfalse.s loc_770DF
0x770bf  ldloc.s  0xA
0x770c1  ldstr    aMailboxprocess_3// "MailboxProcessingContext = \r\n\t\t\t\t"...
0x770c6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x770cb  pop
0x770cc  ldloc.s  0xB
0x770ce  ldstr    aNormalcontext// "@normalContext"
0x770d3  ldc.i4.0
0x770d4  box      [mscorlib]System.Int32
0x770d9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x770de  pop
0x770df  ldloc.s  0xA
0x770e1  ldstr    aIncomingemails_0// "IncomingEmailStatus=@status"
0x770e6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x770eb  pop
0x770ec  ldloc.s  0xB
0x770ee  ldstr    aTime// "@time"
0x770f3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x770f8  box      [mscorlib]System.DateTime
0x770fd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x77102  pop
0x77103  ldloc.s  0xB
0x77105  ldstr    aDequeuedpostpo// "@dequeuedPostponeTestAccessUntil"
0x7710a  ldloc.2
0x7710b  box      [mscorlib]System.DateTime
0x77110  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x77115  pop
0x77116  ldloc.s  0xB
0x77118  ldstr    aPostponetestac// "@postponeTestAccessUntil"
0x7711d  ldloc.s  9
0x7711f  ldfld    class <>c__DisplayClass2_1 <>c__DisplayClass2_0::CS$<>8__locals1
0x77124  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass2_1::postponeTestAccessUntil
0x77129  box      [mscorlib]System.DateTime
0x7712e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x77133  pop
0x77134  ldloc.s  0xB
0x77136  ldstr    aFailedstatus// "@failedStatus"
0x7713b  ldc.i4.2
0x7713c  box      [mscorlib]System.Int32
0x77141  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x77146  pop
0x77147  ldloc.s  0xB
0x77149  ldstr    aStatus_0// "@status"
0x7714e  ldloc.s  4
0x77150  box      [mscorlib]System.Int32
0x77155  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7715a  pop
0x7715b  ldloc.s  9
0x7715d  ldfld    class <>c__DisplayClass2_1 <>c__DisplayClass2_0::CS$<>8__locals1
0x77162  ldfld    valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult <>c__DisplayClass2_1::result
0x77167  brfalse.s loc_77178
0x77169  ldloc.s  9
0x7716b  ldfld    class <>c__DisplayClass2_1 <>c__DisplayClass2_0::CS$<>8__locals1
0x77170  ldfld    valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult <>c__DisplayClass2_1::result
0x77175  ldc.i4.3
0x77176  bne.un.s loc_771E6
0x77178  ldloc.s  0xA
0x7717a  ldstr    aEnabledforinco_1// ", EnabledForIncomingEmail = 1,"
0x7717f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x77184  pop
0x77185  ldloc.s  0xA
0x77187  ldstr    aTransientfailu_2// "TransientFailureCount = TransientFailur"...
0x7718c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x77191  pop
0x77192  ldloc.s  0xA
0x77194  ldstr    aLastactiveonDa// "LastActiveOn = @dateTimeNow"
0x77199  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7719e  pop
0x7719f  ldloc.s  0xB
0x771a1  ldstr    aTransienterror_1// "@transientErrorCountResetMask"
0x771a6  ldc.i4   0xFF0FFFFF
0x771ab  box      [mscorlib]System.Int32
0x771b0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x771b5  pop
0x771b6  ldloc.s  0xB
0x771b8  ldstr    aDatetimenow// "@dateTimeNow"
0x771bd  ldarg.0
0x771be  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x771c3  box      [mscorlib]System.DateTime
0x771c8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x771cd  pop
0x771ce  ldc.i4.s 0x29
0x771d0  ldloc.s  9
0x771d2  ldfld    class <>c__DisplayClass2_1 <>c__DisplayClass2_0::CS$<>8__locals1
0x771d7  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox <>c__DisplayClass2_1::mailbox
0x771dc  call     void Microsoft.Crm.Asynchronous.EmailConnector.MailboxTestAccessTraceLogger::LogInformationLevelTraceRecord(int32 traceCode, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox)
0x771e1  br       loc_772FD
0x771e6  ldloc.s  9
0x771e8  ldfld    class <>c__DisplayClass2_1 <>c__DisplayClass2_0::CS$<>8__locals1
0x771ed  ldfld    valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult <>c__DisplayClass2_1::result
0x771f2  ldc.i4.2
0x771f3  bne.un.s loc_7722B
0x771f5  ldloc.s  0xA
0x771f7  ldstr    aEnabledforinco_2// ", EnabledForIncomingEmail = 0,"
0x771fc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x77201  pop
0x77202  ldloc.s  0xA
0x77204  ldstr    aTransientfailu_5// "TransientFailureCount = TransientFailur"...
0x77209  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7720e  pop
0x7720f  ldloc.s  0xB
0x77211  ldstr    aTransienterror_1// "@transientErrorCountResetMask"
0x77216  ldc.i4   0xFF0FFFFF
0x7721b  box      [mscorlib]System.Int32
0x77220  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x77225  pop
0x77226  br       loc_772FD
0x7722b  ldloc.s  9
0x7722d  ldfld    class <>c__DisplayClass2_1 <>c__DisplayClass2_0::CS$<>8__locals1
0x77232  ldfld    valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult <>c__DisplayClass2_1::result
0x77237  ldc.i4.1
0x77238  bne.un   loc_772FD
0x7723d  ldloc.s  0xA
0x7723f  ldstr    aEnabledforinco_3// ", EnabledForIncomingEmail = CASE WHEN T"...
0x77244  ldloc.3
0x77245  brtrue.s loc_7724E
0x77247  ldstr    asc_8A7C2// ""
0x7724c  br.s     loc_77253
0x7724e  ldstr    aOrTestemailcon// "OR TestEmailConfigurationRetryCount <= "...
0x77253  ldstr    aThen0ElseEnabl_0// "THEN 0 ELSE EnabledForIncomingEmail END"...
0x77258  call     string [mscorlib]System.String::Concat(string, string, string)
0x7725d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x77262  pop
0x77263  ldloc.s  0xA
0x77265  ldstr    aTransientfailu_7// "TransientFailureCount = CASE \r\n\t\t\t"...
0x7726a  ldloc.3
0x7726b  brtrue.s loc_77274
0x7726d  ldstr    asc_8A7C2// ""
0x77272  br.s     loc_77279
0x77274  ldstr    aOrTestemailcon// "OR TestEmailConfigurationRetryCount <= "...
0x77279  ldstr    aThenTransientf// "THEN TransientFailureCount & @transient"...
0x7727e  call     string [mscorlib]System.String::Concat(string, string, string)
0x77283  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x77288  pop
0x77289  ldc.i4.1
0x7728a  newarr   [mscorlib]System.String
0x7728f  dup
0x77290  ldc.i4.0
0x77291  ldstr    aTransientfailu_8// "TransientFailureCount"
0x77296  stelem.ref
0x77297  stloc.s  5
0x77299  ldloc.s  0xB
0x7729b  ldstr    aMaxtransientfa// "@maxTransientFailureCount"
0x772a0  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IEmailConfiguration Microsoft.Crm.Asynchronous.EmailConnector.EmailConfiguration::get_Instance()
0x772a5  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IEmailConfiguration::get_MaximumMailboxTransientFailures()
0x772aa  ldc.i4.s 0x14
0x772ac  shl
0x772ad  box      [mscorlib]System.Int32
0x772b2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x772b7  pop
0x772b8  ldloc.s  0xB
0x772ba  ldstr    aTransienterror// "@transientErrorCountMask"
0x772bf  ldc.i4   0xF00000
0x772c4  box      [mscorlib]System.Int32
0x772c9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x772ce  pop
0x772cf  ldloc.s  0xB
0x772d1  ldstr    aTransienterror_1// "@transientErrorCountResetMask"
0x772d6  ldc.i4   0xFF0FFFFF
0x772db  box      [mscorlib]System.Int32
0x772e0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x772e5  pop
0x772e6  ldloc.s  0xB
0x772e8  ldstr    aTransienterror_0// "@transientErrorCountShift"
0x772ed  ldc.i4   0x100000
0x772f2  box      [mscorlib]System.Int32
0x772f7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x772fc  pop
0x772fd  ldloc.s  0xA
0x772ff  ldstr    aOutput// "OUTPUT "
0x77304  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x77309  pop
0x7730a  ldloc.s  0xA
0x7730c  ldstr    aInsertedEnable// "INSERTED.EnabledForIncomingEmail"
0x77311  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x77316  pop
0x77317  ldloc.s  0xA
0x77319  ldstr    aInsertedTestem// ",INSERTED.TestEmailConfigurationSchedul"...
0x7731e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x77323  pop
0x77324  ldloc.s  0xA
0x77326  ldstr    aInsertedPostpo// ",INSERTED.PostponeTestEmailConfiguratio"...
0x7732b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x77330  pop
0x77331  ldloc.s  5
0x77333  brfalse.s loc_77375
0x77335  ldloc.s  5
0x77337  stloc.s  0xC
0x77339  ldc.i4.0
0x7733a  stloc.s  0xD
0x7733c  br.s     loc_7736D
0x7733e  ldloc.s  0xC
0x77340  ldloc.s  0xD
0x77342  ldelem.ref
0x77343  stloc.s  0xE
0x77345  ldloc.s  0xA
0x77347  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
  ... truncated ...
```
