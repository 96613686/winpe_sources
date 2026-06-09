# Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::CalculateRetryOrFailure

- ea: `0x4710`
- end: `0x48e9`
- name: `Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::CalculateRetryOrFailure`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x45d0`

## callees

- `0x2650`
- `0x4570`
- `0x45b0`
- `0x4710`
- `0x48f0`
- `0x4bd0`
- `0x59c0`
- `0x59d0`

## string_xrefs

- `0x48a8`: `Using RetryWithBackOff option. Command has been attempted {0} times, will retry again in {1} seconds.`

## pseudocode

```c

```

## disassembly

```asm
0x4710  ldc.i4.2
0x4711  stloc.0
0x4712  ldarg.0
0x4713  ldfld    int32 Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::_attemptCount
0x4718  ldarg.1
0x4719  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::get_FullConfiguration()
0x471e  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration::get_StateStatusUpdateMaxRetryCount()
0x4723  bgt.s    loc_478A
0x4725  ldarg.0
0x4726  ldfld    int32 Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::_attemptCount
0x472b  ldc.i4.1
0x472c  bne.un.s loc_4783
0x472e  ldarg.1
0x472f  ldc.i4.1
0x4730  ldc.i4   0x80004404
0x4735  conv.u8
0x4736  ldc.i4.4
0x4737  newarr   [mscorlib]System.Object
0x473c  dup
0x473d  ldc.i4.0
0x473e  call     string [mscorlib]System.Environment::get_MachineName()
0x4743  stelem.ref
0x4744  dup
0x4745  ldc.i4.1
0x4746  ldarg.0
0x4747  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::get_Configuration()
0x474c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x4751  box      [mscorlib]System.Guid
0x4756  stelem.ref
0x4757  dup
0x4758  ldc.i4.2
0x4759  ldarg.1
0x475a  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::get_FullConfiguration()
0x475f  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration::get_StateStatusUpdateMaxRetryCount()
0x4764  box      [mscorlib]System.Int32
0x4769  stelem.ref
0x476a  dup
0x476b  ldc.i4.3
0x476c  ldarg.2
0x476d  callvirt instance string [mscorlib]System.Object::ToString()
0x4772  stelem.ref
0x4773  callvirt instance void Microsoft.Crm.Asynchronous.AsyncManagerBase::LogEvent(valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventId, object[] parameters)
0x4778  ldarg.0
0x4779  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x477e  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::_retryStartTime
0x4783  ldc.i4.2
0x4784  stloc.0
0x4785  br       loc_48E7
0x478a  ldarg.1
0x478b  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::get_FullConfiguration()
0x4790  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration::get_StateStatusUpdateInterval()
0x4795  stloc.3
0x4796  ldloca.s 3
0x4798  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x479d  stloc.1
0x479e  ldc.i4.s 0x18
0x47a0  ldc.i4.0
0x47a1  ldc.i4.0
0x47a2  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x47a7  stloc.3
0x47a8  ldloca.s 3
0x47aa  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x47af  stloc.2
0x47b0  ldarg.0
0x47b1  call     instance bool Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::get_RetryWithBackOff()
0x47b6  brfalse.s loc_47D8
0x47b8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x47bd  ldarg.0
0x47be  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::_retryStartTime
0x47c3  ldc.r8   3.0
0x47cc  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x47d1  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x47d6  brfalse.s loc_4816
0x47d8  ldarg.1
0x47d9  ldc.i4.1
0x47da  ldc.i4   0xC0004406
0x47df  conv.u8
0x47e0  ldc.i4.3
0x47e1  newarr   [mscorlib]System.Object
0x47e6  dup
0x47e7  ldc.i4.0
0x47e8  call     string [mscorlib]System.Environment::get_MachineName()
0x47ed  stelem.ref
0x47ee  dup
0x47ef  ldc.i4.1
0x47f0  ldarg.0
0x47f1  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::get_Configuration()
0x47f6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x47fb  box      [mscorlib]System.Guid
0x4800  stelem.ref
0x4801  dup
0x4802  ldc.i4.2
0x4803  ldarg.2
0x4804  callvirt instance string [mscorlib]System.Object::ToString()
0x4809  stelem.ref
0x480a  callvirt instance void Microsoft.Crm.Asynchronous.AsyncManagerBase::LogEvent(valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventId, object[] parameters)
0x480f  ldc.i4.1
0x4810  stloc.0
0x4811  br       loc_48E7
0x4816  ldarg.0
0x4817  ldarg.1
0x4818  call     instance valuetype CommandResult Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::CalculateRetryOrFailureForOrganization(class Microsoft.Crm.Asynchronous.QueueManager queueManager)
0x481d  stloc.0
0x481e  ldc.i4.2
0x481f  ldloc.0
0x4820  bne.un   loc_48E7
0x4825  ldarg.0
0x4826  ldc.r8   4.0
0x482f  ldarg.0
0x4830  ldfld    int32 Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::_attemptCount
0x4835  ldarg.1
0x4836  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::get_FullConfiguration()
0x483b  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration::get_StateStatusUpdateMaxRetryCount()
0x4840  sub
0x4841  conv.r8
0x4842  call     float64 [mscorlib]System.Math::Pow(float64, float64)
0x4847  conv.i4
0x4848  ldc.i4.1
0x4849  sub
0x484a  stfld    int32 Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::_retrySkipCount
0x484f  ldarg.0
0x4850  ldfld    int32 Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::_retrySkipCount
0x4855  conv.r8
0x4856  ldloc.1
0x4857  mul
0x4858  ldloc.2
0x4859  ble.un.s loc_4865
0x485b  ldarg.0
0x485c  ldloc.2
0x485d  ldloc.1
0x485e  div
0x485f  conv.i4
0x4860  stfld    int32 Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::_retrySkipCount
0x4865  ldarg.1
0x4866  ldc.i4.1
0x4867  ldc.i4   0x80004404
0x486c  conv.u8
0x486d  ldc.i4.4
0x486e  newarr   [mscorlib]System.Object
0x4873  dup
0x4874  ldc.i4.0
0x4875  call     string [mscorlib]System.Environment::get_MachineName()
0x487a  stelem.ref
0x487b  dup
0x487c  ldc.i4.1
0x487d  ldarg.0
0x487e  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::get_Configuration()
0x4883  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x4888  box      [mscorlib]System.Guid
0x488d  stelem.ref
0x488e  dup
0x488f  ldc.i4.2
0x4890  ldarg.1
0x4891  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::get_FullConfiguration()
0x4896  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration::get_StateStatusUpdateMaxRetryCount()
0x489b  box      [mscorlib]System.Int32
0x48a0  stelem.ref
0x48a1  dup
0x48a2  ldc.i4.3
0x48a3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x48a8  ldstr    aUsingRetrywith// "Using RetryWithBackOff option. Command "...
0x48ad  ldc.i4.2
0x48ae  newarr   [mscorlib]System.Object
0x48b3  dup
0x48b4  ldc.i4.0
0x48b5  ldarg.0
0x48b6  ldfld    int32 Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::_attemptCount
0x48bb  box      [mscorlib]System.Int32
0x48c0  stelem.ref
0x48c1  dup
0x48c2  ldc.i4.1
0x48c3  ldarg.0
0x48c4  ldfld    int32 Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::_retrySkipCount
0x48c9  conv.r8
0x48ca  ldloc.1
0x48cb  mul
0x48cc  ldc.r8   1000.0
0x48d5  div
0x48d6  box      [mscorlib]System.Double
0x48db  stelem.ref
0x48dc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x48e1  stelem.ref
0x48e2  callvirt instance void Microsoft.Crm.Asynchronous.AsyncManagerBase::LogEvent(valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventId, object[] parameters)
0x48e7  ldloc.0
0x48e8  ret
```
