# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::LogLongProcessingMailboxes

- ea: `0x82e0`
- end: `0x840b`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::LogLongProcessingMailboxes`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x81e0`

## callees

- `0x7ff0`
- `0x82e0`
- `0x9ec0`
- `0xb160`

## string_xrefs

- `0x8316`: `SELECT MailboxId , ProcessingLastAttemptedOn, IsServiceAccount\n												FROM MailboxBase WITH (NOLOCK) \n												WHERE\n													ProcessingStateCode = @lockedState\n													and HostId = @hostId`

## pseudocode

```c

```

## disassembly

```asm
0x82e0  newobj   instance void <>c__DisplayClass10_0::.ctor()
0x82e5  stloc.0
0x82e6  ldloc.0
0x82e7  ldarg.0
0x82e8  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess <>c__DisplayClass10_0::<>4__this
0x82ed  ldloc.0
0x82ee  ldc.i4.1
0x82ef  stfld    bool <>c__DisplayClass10_0::shouldUnlockAllLongProcessingMailboxes
0x82f4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x82f9  ldarg.0
0x82fa  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x82ff  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IMailboxQueueConfiguration Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::get_FullConfiguration()
0x8304  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IMailboxQueueConfiguration::get_MailboxReportEventInterval()
0x8309  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x830e  stloc.1
0x830f  ldloc.0
0x8310  ldc.i4.0
0x8311  stfld    int32 <>c__DisplayClass10_0::countOfMailboxesToUnlock
0x8316  ldstr    aSelectMailboxi// "SELECT MailboxId , ProcessingLastAttemp"...
0x831b  stloc.2
0x831c  ldloc.0
0x831d  ldloc.2
0x831e  ldc.i4.1
0x831f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x8324  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass10_0::selectLongRunningCommand
0x8329  ldloc.0
0x832a  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass10_0::selectLongRunningCommand
0x832f  ldstr    aLockedstate// "@lockedState"
0x8334  ldc.i4.1
0x8335  box      [mscorlib]System.Int32
0x833a  ldloca.s 3
0x833c  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x8342  ldloc.3
0x8343  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x8348  ldloc.0
0x8349  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass10_0::selectLongRunningCommand
0x834e  ldstr    aHostid// "@hostId"
0x8353  ldarg.0
0x8354  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x8359  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x835e  ldc.i4   0x100
0x8363  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x8368  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x836d  ldarg.0
0x836e  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_operationsFactory
0x8373  ldarg.0
0x8374  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x8379  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0x837e  ldstr    aReportevents_0// "_ReportEvents"
0x8383  call     string [mscorlib]System.String::Concat(string, string)
0x8388  ldarg.0
0x8389  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x838e  ldloc.0
0x838f  ldftn    instance void <>c__DisplayClass10_0::<LogLongProcessingMailboxes>b__0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x8395  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0x839a  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction)
0x839f  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x83a4  ldloc.0
0x83a5  ldfld    int32 <>c__DisplayClass10_0::countOfMailboxesToUnlock
0x83aa  ldc.i4.0
0x83ab  cgt
0x83ad  ldloc.0
0x83ae  ldfld    bool <>c__DisplayClass10_0::shouldUnlockAllLongProcessingMailboxes
0x83b3  and
0x83b4  brfalse.s loc_840A
0x83b6  ldarg.0
0x83b7  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x83bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x83c1  ldc.i4.s 0x15
0x83c3  ldstr    aForceUnlocking// "Force unlocking {0} mailboxes for organ"...
0x83c8  ldc.i4.2
0x83c9  newarr   [mscorlib]System.Object
0x83ce  dup
0x83cf  ldc.i4.0
0x83d0  ldloc.0
0x83d1  ldfld    int32 <>c__DisplayClass10_0::countOfMailboxesToUnlock
0x83d6  box      [mscorlib]System.Int32
0x83db  stelem.ref
0x83dc  dup
0x83dd  ldc.i4.1
0x83de  ldarg.0
0x83df  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x83e4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x83e9  stloc.s  4
0x83eb  ldloca.s 4
0x83ed  constrained. [mscorlib]System.Guid
0x83f3  callvirt instance string [mscorlib]System.Object::ToString()
0x83f8  stelem.ref
0x83f9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x83fe  ldarg.0
0x83ff  ldloc.1
0x8400  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x8405  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::TimeoutLocked([opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> unlockMailboxesStartedBefore)
0x840a  ret
```
