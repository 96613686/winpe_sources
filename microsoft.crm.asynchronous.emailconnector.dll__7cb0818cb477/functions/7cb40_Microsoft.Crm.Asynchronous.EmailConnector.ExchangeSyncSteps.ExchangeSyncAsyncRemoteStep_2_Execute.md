# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2::Execute

- ea: `0x7cb40`
- end: `0x7cf32`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2::Execute`
- size: `1010`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x7d10`
- `0x7d20`
- `0xa3f0`
- `0xba70`
- `0x417a0`
- `0x42280`
- `0x4da80`
- `0x52650`
- `0x5a700`
- `0x5a930`
- `0x5a940`
- `0x6ae70`
- `0x7cb40`
- `0x82a00`

## string_xrefs

- `0x7cc02`: `ServicePoint Details : Connection Limit = '{0}' , Current Connections = '{1}', Connection Lease Timeout = '{2}', Protocol Version = '{3}'`
- `0x7cc47`: `The attempt to close the connection group '{0}' from the ServicePoint with URL '{1}' because it was resumed prematurely returned {2}.`
- `0x7ce37`: `Service Response Exception occurred when invoking EWS for mailbox {0}, organization {1}, async event id {2} : exception: {3}`
- `0x7cecd`: `Cancelling async event id '{0}' for mailbox id '{1}' because of Service Response Exception.`

## pseudocode

```c

```

## disassembly

```asm
0x7cb40  ldarg.0
0x7cb41  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::get_ACTContext()
0x7cb46  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x7cb4b  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventExecutionStatus [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_Status()
0x7cb50  ldc.i4.3
0x7cb51  bne.un   loc_7CC85
0x7cb56  ldarg.0
0x7cb57  ldc.i4.1
0x7cb58  ldstr    aCancellingAsyn// "Cancelling async event id '{0}' for mai"...
0x7cb5d  ldc.i4.2
0x7cb5e  newarr   [mscorlib]System.Object
0x7cb63  dup
0x7cb64  ldc.i4.0
0x7cb65  ldarg.0
0x7cb66  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::get_ACTContext()
0x7cb6b  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x7cb70  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x7cb75  box      [mscorlib]System.Guid
0x7cb7a  stelem.ref
0x7cb7b  dup
0x7cb7c  ldc.i4.1
0x7cb7d  ldarg.0
0x7cb7e  call     instance string class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::get_MailboxId()
0x7cb83  stelem.ref
0x7cb84  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7cb89  ldarg.0
0x7cb8a  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::get_StepContext()
0x7cb8f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_ExchangeDataProvider()
0x7cb94  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeServiceProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeProvider::get_ExchangeServiceProvider()
0x7cb99  ldarg.0
0x7cb9a  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::get_ACTContext()
0x7cb9f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x7cba4  ldarg.0
0x7cba5  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::get_ACTContext()
0x7cbaa  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x7cbaf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Profile()
0x7cbb4  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CredentialRetrievalMethod [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile::get_IncomingCredentialRetrievalMethod()
0x7cbb9  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IExchangeServiceProvider::GetConnectionGroupName(class Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration mailboxAccessConfiguration, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CredentialRetrievalMethod credentialRetrievalMethod)
0x7cbbe  stloc.0
0x7cbbf  ldloc.0
0x7cbc0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7cbc5  brtrue   loc_7CC77
0x7cbca  ldarg.0
0x7cbcb  ldc.i4.3
0x7cbcc  ldstr    aTryingToCloseT// "Trying to close the connection group wi"...
0x7cbd1  ldc.i4.1
0x7cbd2  newarr   [mscorlib]System.Object
0x7cbd7  dup
0x7cbd8  ldc.i4.0
0x7cbd9  ldloc.0
0x7cbda  stelem.ref
0x7cbdb  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7cbe0  ldc.i4.0
0x7cbe1  stloc.1
0x7cbe2  ldarg.0
0x7cbe3  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::get_ACTContext()
0x7cbe8  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x7cbed  callvirt instance class [System]System.Uri Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_ServerUrl()
0x7cbf2  call     class [System]System.Net.ServicePoint [System]System.Net.ServicePointManager::FindServicePoint(class [System]System.Uri)
0x7cbf7  stloc.2
0x7cbf8  ldloc.2
0x7cbf9  ldloc.0
0x7cbfa  callvirt instance bool [System]System.Net.ServicePoint::CloseConnectionGroup(string)
0x7cbff  stloc.1
0x7cc00  ldarg.0
0x7cc01  ldc.i4.3
0x7cc02  ldstr    aServicepointDe// "ServicePoint Details : Connection Limit"...
0x7cc07  ldc.i4.4
0x7cc08  newarr   [mscorlib]System.Object
0x7cc0d  dup
0x7cc0e  ldc.i4.0
0x7cc0f  ldloc.2
0x7cc10  callvirt instance int32 [System]System.Net.ServicePoint::get_ConnectionLimit()
0x7cc15  box      [mscorlib]System.Int32
0x7cc1a  stelem.ref
0x7cc1b  dup
0x7cc1c  ldc.i4.1
0x7cc1d  ldloc.2
0x7cc1e  callvirt instance int32 [System]System.Net.ServicePoint::get_CurrentConnections()
0x7cc23  box      [mscorlib]System.Int32
0x7cc28  stelem.ref
0x7cc29  dup
0x7cc2a  ldc.i4.2
0x7cc2b  ldloc.2
0x7cc2c  callvirt instance int32 [System]System.Net.ServicePoint::get_ConnectionLeaseTimeout()
0x7cc31  box      [mscorlib]System.Int32
0x7cc36  stelem.ref
0x7cc37  dup
0x7cc38  ldc.i4.3
0x7cc39  ldloc.2
0x7cc3a  callvirt instance class [mscorlib]System.Version [System]System.Net.ServicePoint::get_ProtocolVersion()
0x7cc3f  stelem.ref
0x7cc40  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7cc45  ldarg.0
0x7cc46  ldc.i4.2
0x7cc47  ldstr    aTheAttemptToCl// "The attempt to close the connection gro"...
0x7cc4c  ldc.i4.3
0x7cc4d  newarr   [mscorlib]System.Object
0x7cc52  dup
0x7cc53  ldc.i4.0
0x7cc54  ldloc.0
0x7cc55  stelem.ref
0x7cc56  dup
0x7cc57  ldc.i4.1
0x7cc58  ldarg.0
0x7cc59  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::get_ACTContext()
0x7cc5e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x7cc63  callvirt instance class [System]System.Uri Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_ServerUrl()
0x7cc68  stelem.ref
0x7cc69  dup
0x7cc6a  ldc.i4.2
0x7cc6b  ldloc.1
0x7cc6c  box      [mscorlib]System.Boolean
0x7cc71  stelem.ref
0x7cc72  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7cc77  ldarg.0
0x7cc78  ldc.i4.3
0x7cc79  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::set_Status(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult)
0x7cc7e  ldarg.0
0x7cc7f  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::get_Status()
0x7cc84  ret
0x7cc85  ldarg.0
0x7cc86  ldfld    bool class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::_initialized
0x7cc8b  brtrue.s loc_7CC9A
0x7cc8d  ldarg.0
0x7cc8e  callvirt instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::Initialize()
0x7cc93  ldarg.0
0x7cc94  ldc.i4.1
0x7cc95  stfld    bool class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::_initialized
0x7cc9a  ldarg.0
0x7cc9b  ldfld    var<u1>[] class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::_items
0x7cca0  brtrue.s loc_7CCB3
0x7cca2  ldarg.0
0x7cca3  ldarg.0
0x7cca4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>> class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::GetIterator()
0x7cca9  call     T0x2B0000CF
0x7ccae  stfld    var<u1>[] class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::_items
0x7ccb3  ldarg.0
0x7ccb4  ldfld    bool class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::_hasStarted
0x7ccb9  brfalse.s loc_7CCD3
0x7ccbb  ldarg.0
0x7ccbc  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::get_Status()
0x7ccc1  ldc.i4.1
0x7ccc2  bne.un.s loc_7CCD3
0x7ccc4  ldarg.0
0x7ccc5  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::get_Current()
0x7ccca  box      var<u1>
0x7cccf  brtrue.s loc_7CCD3
0x7ccd1  ldc.i4.1
0x7ccd2  ret
0x7ccd3  ldarg.0
0x7ccd4  ldc.i4.1
0x7ccd5  stfld    bool class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::_hasStarted
0x7ccda  ldarg.0
0x7ccdb  call     instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::GetEnumerator()
0x7cce0  stloc.3
0x7cce1  br       loc_7CF0B
0x7cce6  ldloc.3
0x7cce7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>>::get_Current()
0x7ccec  pop
0x7cced  ldarg.0
0x7ccee  ldfld    bool class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::_itemsPreProcessed
0x7ccf3  brtrue.s loc_7CD02
0x7ccf5  ldarg.0
0x7ccf6  callvirt instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::PreProcessItems()
0x7ccfb  ldarg.0
0x7ccfc  ldc.i4.1
0x7ccfd  stfld    bool class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::_itemsPreProcessed
0x7cd02  ldarg.0
0x7cd03  ldfld    bool class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::_currIteratorStarted
0x7cd08  brtrue   loc_7CDFD
0x7cd0d  ldarg.0
0x7cd0e  ldc.i4.1
0x7cd0f  stfld    bool class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::_currIteratorStarted
0x7cd14  ldarg.0
0x7cd15  ldc.i4.3
0x7cd16  ldstr    aInvokingBeginr// "Invoking 'BeginRequest' for '{0}', mail"...
0x7cd1b  ldc.i4.2
0x7cd1c  newarr   [mscorlib]System.Object
0x7cd21  dup
0x7cd22  ldc.i4.0
0x7cd23  ldarg.0
0x7cd24  callvirt instance string [mscorlib]System.Object::ToString()
0x7cd29  stelem.ref
0x7cd2a  dup
0x7cd2b  ldc.i4.1
0x7cd2c  ldarg.0
0x7cd2d  call     instance string class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::get_MailboxId()
0x7cd32  stelem.ref
0x7cd33  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7cd38  ldarg.0
0x7cd39  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::BeforeCall()
0x7cd3e  ldarg.0
0x7cd3f  brfalse  loc_7CDE7
0x7cd44  ldarg.0
0x7cd45  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::get_StepContext()
0x7cd4a  brfalse  loc_7CDE7
0x7cd4f  ldarg.0
0x7cd50  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::get_StepContext()
0x7cd55  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x7cd5a  brfalse  loc_7CDE7
0x7cd5f  ldarg.0
0x7cd60  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::get_StepContext()
0x7cd65  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x7cd6a  callvirt instance class ACTState Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Mailbox()
0x7cd6f  brfalse.s loc_7CDE7
0x7cd71  ldarg.0
0x7cd72  ldfld    class [mscorlib]System.IAsyncResult class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::_result
0x7cd77  brtrue.s loc_7CDE7
0x7cd79  ldarg.0
0x7cd7a  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::get_StepContext()
0x7cd7f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_Worker()
0x7cd84  callvirt instance class ACTState Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Mailbox()
0x7cd89  callvirt instance bool ACTState::get_IsSynchronousEwsFcbEnabled()
0x7cd8e  brfalse.s loc_7CDE7
0x7cd90  ldarg.0
0x7cd91  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::get_Status()
0x7cd96  ldc.i4.2
0x7cd97  beq.s    loc_7CDE7
0x7cd99  ldarg.0
0x7cd9a  ldc.i4.3
0x7cd9b  ldstr    aInvokingProces// "Invoking 'ProcessResponse' for '{0}', m"...
0x7cda0  ldc.i4.2
0x7cda1  newarr   [mscorlib]System.Object
0x7cda6  dup
0x7cda7  ldc.i4.0
0x7cda8  ldarg.0
0x7cda9  callvirt instance string [mscorlib]System.Object::ToString()
0x7cdae  stelem.ref
0x7cdaf  dup
0x7cdb0  ldc.i4.1
0x7cdb1  ldarg.0
0x7cdb2  call     instance string class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::get_MailboxId()
0x7cdb7  stelem.ref
0x7cdb8  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7cdbd  ldarg.0
0x7cdbe  ldarg.0
0x7cdbf  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::ProcessResponse()
0x7cdc4  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::set_Status(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult)
0x7cdc9  ldarg.0
0x7cdca  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::get_Status()
0x7cdcf  ldc.i4.1
0x7cdd0  bne.un.s loc_7CDE7
0x7cdd2  ldarg.0
0x7cdd3  ldc.i4.1
0x7cdd4  stfld    bool class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::_canMoveNext
0x7cdd9  ldarg.0
0x7cdda  ldc.i4.0
0x7cddb  stfld    bool class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::_itemsPreProcessed
0x7cde0  ldarg.0
0x7cde1  ldc.i4.0
0x7cde2  stfld    bool class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::_currIteratorStarted
0x7cde7  ldarg.0
0x7cde8  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::get_Status()
0x7cded  ldc.i4.1
0x7cdee  beq.s    loc_7CE2E
0x7cdf0  ldarg.0
0x7cdf1  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::get_Status()
0x7cdf6  stloc.s  4
0x7cdf8  leave    loc_7CF2F
0x7cdfd  ldarg.0
0x7cdfe  ldc.i4.3
0x7cdff  ldstr    aInvokingEndreq// "Invoking 'EndRequest' for '{0}', mailbo"...
0x7ce04  ldc.i4.2
0x7ce05  newarr   [mscorlib]System.Object
0x7ce0a  dup
0x7ce0b  ldc.i4.0
0x7ce0c  ldarg.0
0x7ce0d  callvirt instance string [mscorlib]System.Object::ToString()
0x7ce12  stelem.ref
0x7ce13  dup
0x7ce14  ldc.i4.1
0x7ce15  ldarg.0
0x7ce16  call     instance string class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::get_MailboxId()
0x7ce1b  stelem.ref
0x7ce1c  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7ce21  ldarg.0
0x7ce22  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::AfterCall()
0x7ce27  ldarg.0
0x7ce28  ldc.i4.0
0x7ce29  stfld    bool class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::_currIteratorStarted
0x7ce2e  leave    loc_7CF0B
0x7ce33  stloc.s  5
0x7ce35  ldarg.0
0x7ce36  ldc.i4.1
0x7ce37  ldstr    aServiceRespons// "Service Response Exception occurred whe"...
0x7ce3c  ldc.i4.4
0x7ce3d  newarr   [mscorlib]System.Object
0x7ce42  dup
0x7ce43  ldc.i4.0
0x7ce44  ldarg.0
0x7ce45  call     instance string class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<var<u1>, !!T0>::get_MailboxId()
0x7ce4a  stelem.ref
0x7ce4b  dup
0x7ce4c  ldc.i4.1
0x7ce4d  ldarg.0
0x7ce4e  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<var<u1>>::get_ACTContext()
0x7ce53  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x7ce58  box      [mscorlib]System.Guid
0x7ce5d  stelem.ref
  ... truncated ...
```
