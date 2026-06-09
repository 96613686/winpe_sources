# Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::UpdateOutgoingMailbox

- ea: `0x72750`
- end: `0x72e14`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::UpdateOutgoingMailbox`
- size: `1732`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `installer_update, broker_com_uri`

## callers

- `0x47380`

## callees

- `0x4d8c0`
- `0x71c20`
- `0x71c40`
- `0x71d00`
- `0x71d60`
- `0x71d80`
- `0x71da0`
- `0x71de0`
- `0x71df0`
- `0x71ea0`
- `0x71ec0`
- `0x71ee0`
- `0x71ef0`
- `0x72710`
- `0x72750`
- `0x737d0`
- `0x739a0`
- `0x73d20`
- `0x742f0`
- `0x74640`
- `0x746a0`
- `0x77a30`
- `0x78070`
- `0x7a490`
- `0x835f0`

## string_xrefs

- `0x727c4`: `UPDATE MailboxBase SET`

## pseudocode

```c

```

## disassembly

```asm
0x72750  ldarg.1
0x72751  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ProcessingResult()
0x72756  stloc.0
0x72757  ldarg.1
0x72758  ldarg.1
0x72759  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::GetMailboxData()
0x7275e  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_PostponeSendingUntil()
0x72763  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::set_OutgoingEmailProcessScheduledOn(valuetype [mscorlib]System.DateTime value)
0x72768  ldarg.0
0x72769  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.IMailboxStateEvaluator Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::mailboxStateEvaluator
0x7276e  ldarg.0
0x7276f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x72774  ldarg.1
0x72775  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x7277a  ldarg.1
0x7277b  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OutgoingEmailProcessScheduledOn()
0x72780  stloc.2
0x72781  ldloca.s 2
0x72783  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x72788  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x7278d  stloc.2
0x7278e  ldloca.s 2
0x72790  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x72795  ceq
0x72797  ldc.i4.1
0x72798  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.IMailboxStateEvaluator::IsMailboxActive(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity mailbox, bool isMaxPostponeTime, [opt] bool isOutgoingMailbox)
0x7279d  ldc.i4.0
0x7279e  ceq
0x727a0  stloc.1
0x727a1  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x727a6  stloc.3
0x727a7  newobj   instance void <>c__DisplayClass9_0::.ctor()
0x727ac  stloc.s  4
0x727ae  ldloc.3
0x727af  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x727b4  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x727b9  stloc.s  5
0x727bb  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x727c0  stloc.s  6
0x727c2  ldloc.s  6
0x727c4  ldstr    aUpdateMailboxb_0// "UPDATE MailboxBase SET"
0x727c9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x727ce  pop
0x727cf  ldarg.0
0x727d0  ldarg.2
0x727d1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x727d6  ldloc.s  6
0x727d8  ldloc.s  5
0x727da  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::AdjustVerboseTracingEnabled(valuetype [mscorlib]System.Guid orgId, class [mscorlib]System.Text.StringBuilder sb, class [System.Data]System.Data.SqlClient.SqlParameterCollection parameters)
0x727df  ldc.i4.0
0x727e0  stloc.s  7
0x727e2  ldloc.s  4
0x727e4  ldc.i4.0
0x727e5  stfld    int32 <>c__DisplayClass9_0::transientFailureCount
0x727ea  ldarg.1
0x727eb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x727f0  ldstr    aTransientfailu// "transientfailurecount"
0x727f5  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x727fa  brtrue.s loc_727FF
0x727fc  ldc.i4.0
0x727fd  br.s     loc_7280F
0x727ff  ldarg.1
0x72800  ldstr    aTransientfailu// "transientfailurecount"
0x72805  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x7280a  unbox.any [mscorlib]System.Int32
0x7280f  stloc.s  8
0x72811  ldarg.0
0x72812  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x72817  stloc.s  9
0x72819  ldsfld   string [mscorlib]System.String::Empty
0x7281e  stloc.s  0xA
0x72820  ldloc.0
0x72821  switch   loc_72AE6, loc_72843, loc_7294D, loc_72BC0, loc_72BC0, loc_72B5E
0x7283e  br       loc_72BC0
0x72843  ldloc.s  6
0x72845  ldstr    aTransientfailu_0// "TransientFailureCount = CASE \r\n\t\t\t"...
0x7284a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7284f  pop
0x72850  ldloc.s  6
0x72852  ldstr    aPostponesendin_0// "PostponeSendingUntil = \r\n\t\t\t\t\t\t"...
0x72857  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7285c  pop
0x7285d  ldloc.s  5
0x7285f  ldstr    aTransienterror// "@transientErrorCountMask"
0x72864  ldc.i4   0xF000000
0x72869  box      [mscorlib]System.Int32
0x7286e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x72873  pop
0x72874  ldloc.s  5
0x72876  ldstr    aTransienterror_0// "@transientErrorCountShift"
0x7287b  ldc.i4   0x1000000
0x72880  box      [mscorlib]System.Int32
0x72885  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7288a  pop
0x7288b  ldloc.s  5
0x7288d  ldstr    aPostponesendin_1// "@postponeSendingUntil"
0x72892  ldloc.s  9
0x72894  ldarg.1
0x72895  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_BackOffDuration()
0x7289a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x7289f  box      [mscorlib]System.DateTime
0x728a4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x728a9  pop
0x728aa  ldloc.s  5
0x728ac  ldstr    aDatetimenow// "@dateTimeNow"
0x728b1  ldloc.s  9
0x728b3  box      [mscorlib]System.DateTime
0x728b8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x728bd  pop
0x728be  ldloc.s  5
0x728c0  ldstr    aDatetimemax// "@dateTimeMax"
0x728c5  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x728ca  box      [mscorlib]System.DateTime
0x728cf  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x728d4  pop
0x728d5  ldloc.s  5
0x728d7  ldstr    aIsmailboxinact// "@isMailboxInactive"
0x728dc  ldloc.1
0x728dd  box      [mscorlib]System.Boolean
0x728e2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x728e7  pop
0x728e8  ldloc.s  8
0x728ea  ldc.i4   0xF000000
0x728ef  and
0x728f0  ldc.i4   0xF000000
0x728f5  bne.un.s loc_72905
0x728f7  ldloc.s  4
0x728f9  ldc.i4   0xF000000
0x728fe  stfld    int32 <>c__DisplayClass9_0::transientFailureCount
0x72903  br.s     loc_7292B
0x72905  ldarg.1
0x72906  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OutgoingEmailProcessScheduledOn()
0x7290b  ldloc.s  9
0x7290d  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x72912  brfalse.s loc_7291F
0x72914  ldloc.s  4
0x72916  ldloc.s  8
0x72918  stfld    int32 <>c__DisplayClass9_0::transientFailureCount
0x7291d  br.s     loc_7292B
0x7291f  ldloc.s  4
0x72921  ldc.i4   0x1000000
0x72926  stfld    int32 <>c__DisplayClass9_0::transientFailureCount
0x7292b  ldloc.1
0x7292c  brfalse.s loc_72935
0x7292e  ldstr    aMailbox0IsAnIn// "Mailbox: {0} is an inactive mailbox, so"...
0x72933  stloc.s  0xA
0x72935  ldarg.0
0x72936  ldarg.2
0x72937  ldc.i4.1
0x72938  ldloc.0
0x72939  ldarg.1
0x7293a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x7293f  ldloc.s  6
0x72941  ldloc.s  5
0x72943  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::UpdateLastSyncErrorDetails(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType operationType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult status, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity internalMailboxEntity, class [mscorlib]System.Text.StringBuilder columns, class [System.Data]System.Data.SqlClient.SqlParameterCollection parameters)
0x72948  br       loc_72BC5
0x7294d  ldarg.0
0x7294e  ldarg.1
0x7294f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x72954  ldarg.1
0x72955  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x7295a  ldarg.1
0x7295b  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Errors()
0x72960  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::CheckIfMailboxNeedsUserAttention(valuetype [mscorlib]System.Guid orgId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity internalMailboxEntity, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> mailboxErrors)
0x72965  stloc.s  0xB
0x72967  ldloc.s  6
0x72969  ldstr    aTransientfailu_1// "TransientFailureCount = @transientError"...
0x7296e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x72973  pop
0x72974  ldloc.1
0x72975  ldloc.s  0xB
0x72977  or
0x72978  brfalse.s loc_729B4
0x7297a  ldloc.s  6
0x7297c  ldstr    aPostponesendin_2// "PostponeSendingUntil = @dateTimeMax,"
0x72981  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x72986  pop
0x72987  ldloc.s  5
0x72989  ldstr    aDatetimemax// "@dateTimeMax"
0x7298e  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x72993  box      [mscorlib]System.DateTime
0x72998  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7299d  pop
0x7299e  ldloc.1
0x7299f  brtrue.s loc_729A8
0x729a1  ldstr    aMailbox0NeedsU// "Mailbox: {0} needs user attention and n"...
0x729a6  br.s     loc_729AD
0x729a8  ldstr    aMailbox0IsAnIn_0// "Mailbox : {0} is an inactive mailbox, s"...
0x729ad  stloc.s  0xA
0x729af  br       loc_72AAB
0x729b4  ldarg.0
0x729b5  ldarg.1
0x729b6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x729bb  ldarg.1
0x729bc  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Errors()
0x729c1  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::HasPermanentError(valuetype [mscorlib]System.Guid orgId, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> mailboxErrors)
0x729c6  brfalse  loc_72AAB
0x729cb  ldloc.s  6
0x729cd  ldstr    aPostponesendin_3// "PostponeSendingUntil = @postponeSending"...
0x729d2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x729d7  pop
0x729d8  ldloc.s  5
0x729da  ldstr    aPostponesendin_1// "@postponeSendingUntil"
0x729df  ldloca.s 9
0x729e1  ldc.r8   30.0
0x729ea  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x729ef  box      [mscorlib]System.DateTime
0x729f4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x729f9  pop
0x729fa  ldarg.2
0x729fb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x72a00  ldarg.1
0x72a01  ldarg.2
0x72a02  brtrue.s loc_72A0B
0x72a04  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x72a09  br.s     loc_72A11
0x72a0b  ldarg.2
0x72a0c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x72a11  ldc.i4.s 0x3D
0x72a13  ldc.i4.1
0x72a14  ldstr    aSettingPostpon_0// "Setting PostponeSendingUntil to 30 minu"...
0x72a19  ldc.i4.4
0x72a1a  newarr   [mscorlib]System.Object
0x72a1f  dup
0x72a20  ldc.i4.0
0x72a21  ldloc.s  9
0x72a23  box      [mscorlib]System.DateTime
0x72a28  stelem.ref
0x72a29  dup
0x72a2a  ldc.i4.1
0x72a2b  ldarg.1
0x72a2c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x72a31  brfalse.s loc_72A45
0x72a33  ldarg.1
0x72a34  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x72a39  ldstr    aLastsyncerrorc// "lastsyncerrorcode"
0x72a3e  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x72a43  brtrue.s loc_72A48
0x72a45  ldc.i4.0
0x72a46  br.s     loc_72A58
0x72a48  ldarg.1
0x72a49  ldstr    aLastsyncerrorc// "lastsyncerrorcode"
0x72a4e  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x72a53  unbox.any [mscorlib]System.Int32
0x72a58  box      [mscorlib]System.Int32
0x72a5d  stelem.ref
0x72a5e  dup
0x72a5f  ldc.i4.2
0x72a60  ldarg.1
0x72a61  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x72a66  brfalse.s loc_72A7A
0x72a68  ldarg.1
0x72a69  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x72a6e  ldstr    aLastsyncerrorc_0// "lastsyncerrorcount"
0x72a73  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x72a78  brtrue.s loc_72A7D
0x72a7a  ldc.i4.0
0x72a7b  br.s     loc_72A8D
0x72a7d  ldarg.1
0x72a7e  ldstr    aLastsyncerrorc_0// "lastsyncerrorcount"
0x72a83  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x72a88  unbox.any [mscorlib]System.Int32
0x72a8d  box      [mscorlib]System.Int32
0x72a92  stelem.ref
0x72a93  dup
0x72a94  ldc.i4.3
0x72a95  ldarg.1
0x72a96  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::GetMailboxData()
0x72a9b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x72aa0  box      [mscorlib]System.Guid
0x72aa5  stelem.ref
0x72aa6  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x72aab  ldloc.s  5
0x72aad  ldstr    aTransienterror// "@transientErrorCountMask"
0x72ab2  ldc.i4   0xF000000
0x72ab7  box      [mscorlib]System.Int32
0x72abc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x72ac1  pop
0x72ac2  ldloc.s  4
0x72ac4  ldc.i4   0xF000000
0x72ac9  stfld    int32 <>c__DisplayClass9_0::transientFailureCount
0x72ace  ldarg.0
0x72acf  ldarg.2
0x72ad0  ldc.i4.1
0x72ad1  ldloc.0
0x72ad2  ldarg.1
0x72ad3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x72ad8  ldloc.s  6
0x72ada  ldloc.s  5
0x72adc  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::UpdateLastSyncErrorDetails(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType operationType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult status, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity internalMailboxEntity, class [mscorlib]System.Text.StringBuilder columns, class [System.Data]System.Data.SqlClient.SqlParameterCollection parameters)
0x72ae1  br       loc_72BC5
0x72ae6  ldc.i4.1
0x72ae7  stloc.s  7
0x72ae9  ldloc.s  6
0x72aeb  ldstr    aTransientfailu_2// "TransientFailureCount = TransientFailur"...
0x72af0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x72af5  pop
0x72af6  ldloc.1
0x72af7  brfalse.s loc_72B26
0x72af9  ldloc.s  6
  ... truncated ...
```
