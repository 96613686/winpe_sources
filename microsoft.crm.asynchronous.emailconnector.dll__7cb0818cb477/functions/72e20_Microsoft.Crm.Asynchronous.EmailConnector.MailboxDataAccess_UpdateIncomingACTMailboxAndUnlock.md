# Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::UpdateIncomingACTMailboxAndUnlock

- ea: `0x72e20`
- end: `0x737c8`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::UpdateIncomingACTMailboxAndUnlock`
- size: `2472`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x759c0`

## callees

- `0x411e0`
- `0x413a0`
- `0x4ae90`
- `0x4d8c0`
- `0x4dcf0`
- `0x533e0`
- `0x71ea0`
- `0x71ec0`
- `0x71ee0`
- `0x72710`
- `0x72e20`
- `0x737d0`
- `0x739a0`
- `0x73d20`
- `0x745f0`
- `0x74620`
- `0x74640`
- `0x74ab0`
- `0x7a490`

## string_xrefs

- `0x73137`: `enabledforincomingemail`
- `0x73144`: `enabledforincomingemail`
- `0x72e79`: `Mailbox: {0} is already unlocked.`
- `0x73004`: `UPDATE MailboxBase SET`
- `0x730ad`: `EnabledForIncomingEmail = 0,`
- `0x730ba`: `IncomingEmailStatus = 2,`
- `0x73448`: `isexchangecontactsimportscheduled`
- `0x73458`: `isexchangecontactsimportscheduled`
- `0x7346e`: `IsExchangeContactsImportScheduled=@isExchangeContactsImportScheduled,`
- `0x73488`: `ExchangeContactsImportCompletedOn=@exchangeContactsImportCompleteOn,`
- `0x73495`: `@isExchangeContactsImportScheduled`
- `0x734d5`: `@exchangeContactsImportCompleteOn`
- `0x734db`: `exchangecontactsimportcompletedon`
- `0x734f4`: `exchangecontactsimportcompletedon`
- `0x7352a`: `LastSuccessfulSyncCompletedOn=@lastSuccessfulSyncCompletedOn,`
- `0x73537`: `@lastSuccessfulSyncCompletedOn`
- `0x735ed`: `ExchangeSyncStateXml = Null,`

## pseudocode

```c

```

## disassembly

```asm
0x72e20  ldc.i4.0
0x72e21  stloc.0
0x72e22  ldarg.2
0x72e23  ldc.i4.2
0x72e24  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::ContainsKey(var<u1>)
0x72e29  brtrue.s loc_72E45
0x72e2b  ldarg.2
0x72e2c  ldc.i4.0
0x72e2d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::ContainsKey(var<u1>)
0x72e32  brtrue.s loc_72E37
0x72e34  ldnull
0x72e35  br.s     loc_72E51
0x72e37  ldarg.2
0x72e38  ldc.i4.0
0x72e39  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::get_Item(void)
0x72e3e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x72e43  br.s     loc_72E51
0x72e45  ldarg.2
0x72e46  ldc.i4.2
0x72e47  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::get_Item(void)
0x72e4c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_InternalEntity()
0x72e51  stloc.1
0x72e52  ldloc.1
0x72e53  brtrue.s loc_72E56
0x72e55  ret
0x72e56  ldarg.0
0x72e57  ldloc.1
0x72e58  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::IsMailboxUnlocked(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity mailbox)
0x72e5d  brfalse.s loc_72E97
0x72e5f  ldarg.0
0x72e60  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x72e65  ldloc.1
0x72e66  ldarg.1
0x72e67  brtrue.s loc_72E70
0x72e69  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x72e6e  br.s     loc_72E76
0x72e70  ldarg.1
0x72e71  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x72e76  ldc.i4.s 0x3D
0x72e78  ldc.i4.3
0x72e79  ldstr    aMailbox0IsAlre// "Mailbox: {0} is already unlocked."
0x72e7e  ldc.i4.1
0x72e7f  newarr   [mscorlib]System.Object
0x72e84  dup
0x72e85  ldc.i4.0
0x72e86  ldloc.1
0x72e87  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x72e8c  box      [mscorlib]System.Guid
0x72e91  stelem.ref
0x72e92  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x72e97  ldc.i4.0
0x72e98  stloc.2
0x72e99  ldloc.1
0x72e9a  ldstr    aTransientfailu// "transientfailurecount"
0x72e9f  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x72ea4  brtrue.s loc_72EA9
0x72ea6  ldc.i4.0
0x72ea7  br.s     loc_72EB9
0x72ea9  ldloc.1
0x72eaa  ldstr    aTransientfailu// "transientfailurecount"
0x72eaf  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x72eb4  unbox.any [mscorlib]System.Int32
0x72eb9  stloc.3
0x72eba  ldarg.2
0x72ebb  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::GetEnumerator()
0x72ec0  stloc.s  7
0x72ec2  br       loc_72FBE
0x72ec7  ldloca.s 7
0x72ec9  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::get_Current()
0x72ece  stloc.s  8
0x72ed0  ldloc.2
0x72ed1  brtrue.s loc_72EED
0x72ed3  ldarg.0
0x72ed4  ldarg.1
0x72ed5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x72eda  ldloc.1
0x72edb  ldloca.s 8
0x72edd  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::get_Value()
0x72ee2  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Errors()
0x72ee7  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::CheckIfMailboxNeedsUserAttention(valuetype [mscorlib]System.Guid orgId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity internalMailboxEntity, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> mailboxErrors)
0x72eec  stloc.2
0x72eed  ldloca.s 8
0x72eef  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::get_Key()
0x72ef4  stloc.s  9
0x72ef6  ldloc.s  9
0x72ef8  brfalse.s loc_72F04
0x72efa  ldloc.s  9
0x72efc  ldc.i4.2
0x72efd  beq.s    loc_72F4E
0x72eff  br       loc_72F96
0x72f04  ldloca.s 8
0x72f06  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::get_Value()
0x72f0b  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ProcessingResult()
0x72f10  ldc.i4.1
0x72f11  bne.un.s loc_72F2B
0x72f13  ldloc.3
0x72f14  ldc.i4   0xF00000
0x72f19  and
0x72f1a  ldc.i4   0xF00000
0x72f1f  beq.s    loc_72F96
0x72f21  ldloc.3
0x72f22  ldc.i4   0x100000
0x72f27  add
0x72f28  stloc.3
0x72f29  br.s     loc_72F96
0x72f2b  ldloca.s 8
0x72f2d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::get_Value()
0x72f32  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ProcessingResult()
0x72f37  ldc.i4.2
0x72f38  bne.un.s loc_72F44
0x72f3a  ldloc.3
0x72f3b  ldc.i4   0xF00000
0x72f40  or
0x72f41  stloc.3
0x72f42  br.s     loc_72F96
0x72f44  ldloc.3
0x72f45  ldc.i4   0xFF0FFFFF
0x72f4a  and
0x72f4b  stloc.3
0x72f4c  br.s     loc_72F96
0x72f4e  ldloca.s 8
0x72f50  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::get_Value()
0x72f55  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ProcessingResult()
0x72f5a  ldc.i4.1
0x72f5b  bne.un.s loc_72F75
0x72f5d  ldloc.3
0x72f5e  ldc.i4   0xF0000
0x72f63  and
0x72f64  ldc.i4   0xF0000
0x72f69  beq.s    loc_72F96
0x72f6b  ldloc.3
0x72f6c  ldc.i4   0x10000
0x72f71  add
0x72f72  stloc.3
0x72f73  br.s     loc_72F96
0x72f75  ldloca.s 8
0x72f77  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::get_Value()
0x72f7c  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ProcessingResult()
0x72f81  ldc.i4.2
0x72f82  bne.un.s loc_72F8E
0x72f84  ldloc.3
0x72f85  ldc.i4   0xF0000
0x72f8a  or
0x72f8b  stloc.3
0x72f8c  br.s     loc_72F96
0x72f8e  ldloc.3
0x72f8f  ldc.i4   0xFFF0FFFF
0x72f94  and
0x72f95  stloc.3
0x72f96  ldloca.s 8
0x72f98  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::get_Value()
0x72f9d  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ProcessingResult()
0x72fa2  ldc.i4.2
0x72fa3  bne.un.s loc_72FA9
0x72fa5  ldc.i4.2
0x72fa6  stloc.0
0x72fa7  br.s     loc_72FBE
0x72fa9  ldloc.0
0x72faa  ldc.i4.2
0x72fab  beq.s    loc_72FBE
0x72fad  ldloca.s 8
0x72faf  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::get_Value()
0x72fb4  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ProcessingResult()
0x72fb9  ldc.i4.1
0x72fba  bne.un.s loc_72FBE
0x72fbc  ldc.i4.1
0x72fbd  stloc.0
0x72fbe  ldloca.s 7
0x72fc0  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::MoveNext()
0x72fc5  brtrue   loc_72EC7
0x72fca  leave.s  loc_72FDA
0x72fcc  ldloca.s 7
0x72fce  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>
0x72fd4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x72fd9  endfinally
0x72fda  ldc.i4.0
0x72fdb  stloc.s  4
0x72fdd  ldc.i4.0
0x72fde  stloc.s  5
0x72fe0  ldloc.s  4
0x72fe2  ldc.i4.1
0x72fe3  add
0x72fe4  stloc.s  4
0x72fe6  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x72feb  stloc.s  0xA
0x72fed  ldloc.s  0xA
0x72fef  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x72ff4  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x72ff9  stloc.s  0xB
0x72ffb  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x73000  stloc.s  0xC
0x73002  ldloc.s  0xC
0x73004  ldstr    aUpdateMailboxb_0// "UPDATE MailboxBase SET"
0x73009  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7300e  pop
0x7300f  ldarg.0
0x73010  ldarg.1
0x73011  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x73016  ldloc.s  0xC
0x73018  ldloc.s  0xB
0x7301a  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::AdjustVerboseTracingEnabled(valuetype [mscorlib]System.Guid orgId, class [mscorlib]System.Text.StringBuilder sb, class [System.Data]System.Data.SqlClient.SqlParameterCollection parameters)
0x7301f  ldloc.s  0xC
0x73021  ldstr    aHostidNull// "HostId = NULL,"
0x73026  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7302b  pop
0x7302c  ldloc.s  0xC
0x7302e  ldstr    aProcessingstat// "ProcessingStateCode = @waitingState,"
0x73033  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x73038  pop
0x73039  ldloc.s  0xC
0x7303b  ldstr    aPostponemailbo_0// "PostponeMailboxProcessingUntil = @postp"...
0x73040  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x73045  pop
0x73046  ldarg.0
0x73047  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.IMailboxStateEvaluator Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::mailboxStateEvaluator
0x7304c  ldarg.0
0x7304d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x73052  ldloc.1
0x73053  ldc.i4.0
0x73054  ldc.i4.0
0x73055  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperations.IMailboxStateEvaluator::IsMailboxActive(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity mailbox, bool isMaxPostponeTime, [opt] bool isOutgoingMailbox)
0x7305a  ldc.i4.0
0x7305b  ceq
0x7305d  stloc.s  5
0x7305f  ldloc.s  5
0x73061  ldloc.2
0x73062  or
0x73063  brfalse  loc_73131
0x73068  ldloc.s  0xB
0x7306a  ldstr    aPostponemailbo_1// "@postponeMailboxProcessingUntil"
0x7306f  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x73074  box      [mscorlib]System.DateTime
0x73079  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7307e  pop
0x7307f  ldarg.2
0x73080  ldc.i4.2
0x73081  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::ContainsKey(var<u1>)
0x73086  brfalse.s loc_730A2
0x73088  ldloc.s  0xC
0x7308a  ldstr    aEnabledforact0// "EnabledForACT = 0,"
0x7308f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x73094  pop
0x73095  ldloc.s  0xC
0x73097  ldstr    aActstatus2// "ACTStatus = 2,"
0x7309c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x730a1  pop
0x730a2  ldarg.2
0x730a3  ldc.i4.0
0x730a4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox>::ContainsKey(var<u1>)
0x730a9  brfalse.s loc_730C5
0x730ab  ldloc.s  0xC
0x730ad  ldstr    aEnabledforinco_0// "EnabledForIncomingEmail = 0,"
0x730b2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x730b7  pop
0x730b8  ldloc.s  0xC
0x730ba  ldstr    aIncomingemails// "IncomingEmailStatus = 2,"
0x730bf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x730c4  pop
0x730c5  ldloc.s  5
0x730c7  brtrue.s loc_730D0
0x730c9  ldstr    aMailbox0NeedsU_0// "Mailbox: {0} needs user attention and n"...
0x730ce  br.s     loc_730D5
0x730d0  ldstr    aMailbox0IsAnIn_3// "Mailbox : {0} is an inactive mailbox, w"...
0x730d5  stloc.s  0xD
0x730d7  ldarg.0
0x730d8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x730dd  ldloc.1
0x730de  ldarg.1
0x730df  brtrue.s loc_730E8
0x730e1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x730e6  br.s     loc_730EE
0x730e8  ldarg.1
0x730e9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x730ee  ldc.i4.s 0x3D
0x730f0  ldc.i4.1
0x730f1  ldloc.s  0xD
0x730f3  ldc.i4.2
0x730f4  newarr   [mscorlib]System.Object
0x730f9  dup
0x730fa  ldc.i4.0
0x730fb  ldloc.1
0x730fc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x73101  box      [mscorlib]System.Guid
0x73106  stelem.ref
0x73107  dup
0x73108  ldc.i4.1
0x73109  ldloc.1
0x7310a  ldstr    aLastsyncerrorc// "lastsyncerrorcode"
0x7310f  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x73114  brtrue.s loc_7311E
0x73116  ldc.i4.0
0x73117  box      [mscorlib]System.Int32
0x7311c  br.s     loc_73129
0x7311e  ldloc.1
0x7311f  ldstr    aLastsyncerrorc// "lastsyncerrorcode"
0x73124  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x73129  stelem.ref
0x7312a  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x7312f  br.s     loc_731AB
0x73131  ldloc.1
  ... truncated ...
```
