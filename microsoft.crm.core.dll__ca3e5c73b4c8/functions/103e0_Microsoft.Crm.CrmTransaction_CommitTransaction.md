# Microsoft.Crm.CrmTransaction::CommitTransaction

- ea: `0x103e0`
- end: `0x10505`
- name: `Microsoft.Crm.CrmTransaction::CommitTransaction`
- size: `293`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x11c80`
- `0x11fe0`

## callees

- `0xd150`
- `0xd380`
- `0xd8e0`
- `0x103e0`
- `0x10d90`
- `0x10e30`
- `0x10f80`
- `0x1a880`
- `0x1b8d0`
- `0x1c220`
- `0x1c350`
- `0x1eaa0`
- `0x1f4b0`
- `0x54770`
- `0x54840`
- `0x55cc0`
- `0x55d00`
- `0x55d20`

## string_xrefs

- `0x103ed`: `CommitTransaction - Encountered disposed Transaction when it should not be disposed`
- `0x10401`: `There is no active transaction. This error is usually caused by custom plug-ins that ignore errors from service calls and continue processing.`
- `0x10471`: `TransactionCommitted`
- `0x104af`: `Commit failed -- clearing connection pool`

## pseudocode

```c

```

## disassembly

```asm
0x103e0  ldarg.0
0x103e1  ldfld    bool Microsoft.Crm.CrmTransaction::disposed
0x103e6  brfalse.s loc_103F8
0x103e8  ldstr    aCrmtransaction// "CrmTransaction"
0x103ed  ldstr    aCommittransact// "CommitTransaction - Encountered dispose"...
0x103f2  newobj   instance void Microsoft.Crm.CrmObjectDisposedException::.ctor(string objectName, string message)
0x103f7  throw
0x103f8  ldarg.0
0x103f9  ldfld    int32 Microsoft.Crm.CrmTransaction::startCount
0x103fe  ldc.i4.0
0x103ff  bgt.s    loc_10411
0x10401  ldstr    aThereIsNoActiv// "There is no active transaction. This er"...
0x10406  ldc.i4   0x80040251
0x1040b  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message, int32 errorCode)
0x10410  throw
0x10411  ldarg.0
0x10412  ldfld    int32 Microsoft.Crm.CrmTransaction::startCount
0x10417  ldc.i4.1
0x10418  ble.s    loc_10429
0x1041a  ldarg.0
0x1041b  ldarg.0
0x1041c  ldfld    int32 Microsoft.Crm.CrmTransaction::startCount
0x10421  ldc.i4.1
0x10422  sub
0x10423  stfld    int32 Microsoft.Crm.CrmTransaction::startCount
0x10428  ret
0x10429  nop
0x1042a  ldarg.0
0x1042b  ldfld    class Microsoft.Crm.CrmTransactionEventManager Microsoft.Crm.CrmTransaction::eventManager
0x10430  callvirt instance void Microsoft.Crm.CrmTransactionEventManager::InvokePreCommitTransactionEvents()
0x10435  newobj   instance void Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x1043a  stloc.0
0x1043b  ldarg.0
0x1043c  ldfld    class [System.Data]System.Data.IDbTransaction Microsoft.Crm.CrmTransaction::transaction
0x10441  callvirt instance void [System.Data]System.Data.IDbTransaction::Commit()
0x10446  ldarg.0
0x10447  ldarg.0
0x10448  ldfld    int32 Microsoft.Crm.CrmTransaction::startCount
0x1044d  ldc.i4.1
0x1044e  sub
0x1044f  stfld    int32 Microsoft.Crm.CrmTransaction::startCount
0x10454  call     class Microsoft.Crm.MetricsReporting Microsoft.Crm.MetricsReporting::get_Instance()
0x10459  ldstr    aSqlexecutions// "SqlExecutions"
0x1045e  ldloc.0
0x1045f  callvirt instance int64 Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x10464  conv.r8
0x10465  ldnull
0x10466  callvirt instance class Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric Microsoft.Crm.MetricsReporting::AddCounterMetric(string name, float64 value, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x1046b  pop
0x1046c  call     class Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents::get_Instance()
0x10471  ldstr    aTransactioncom// "TransactionCommitted"
0x10476  ldarg.0
0x10477  ldfld    class Microsoft.Crm.CrmDbConnection Microsoft.Crm.CrmTransaction::connection
0x1047c  ldarg.0
0x1047d  ldfld    class [System.Data]System.Data.IDbTransaction Microsoft.Crm.CrmTransaction::transaction
0x10482  ldloc.0
0x10483  callvirt instance class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x10488  callvirt instance void Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents::TransactionExecuted(string eventName, class [System.Data]System.Data.IDbConnection connection, class [System.Data]System.Data.IDbTransaction transaction, class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x1048d  ldarg.0
0x1048e  ldfld    class Microsoft.Crm.CrmTransactionEventManager Microsoft.Crm.CrmTransaction::eventManager
0x10493  callvirt instance void Microsoft.Crm.CrmTransactionEventManager::InvokePostCommitTransactionEvents()
0x10498  leave.s  loc_10504
0x1049a  pop
0x1049b  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x104a0  ldc.i4.s 0x1D
0x104a2  ldstr    a0// "{0}"
0x104a7  ldc.i4.1
0x104a8  newarr   [mscorlib]System.Object
0x104ad  dup
0x104ae  ldc.i4.0
0x104af  ldstr    aCommitFailedCl// "Commit failed -- clearing connection po"...
0x104b4  stelem.ref
0x104b5  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x104ba  rethrow
0x104bc  ldarg.0
0x104bd  ldfld    int32 Microsoft.Crm.CrmTransaction::startCount
0x104c2  brtrue.s loc_10503
0x104c4  ldarg.0
0x104c5  ldnull
0x104c6  stfld    class [System.Data]System.Data.IDbTransaction Microsoft.Crm.CrmTransaction::transaction
0x104cb  ldarg.0
0x104cc  ldfld    class Microsoft.Crm.CrmDbConnection Microsoft.Crm.CrmTransaction::connection
0x104d1  callvirt instance valuetype [System.Data]System.Data.IsolationLevel Microsoft.Crm.CrmDbConnection::get_IsolationLevel()
0x104d6  ldc.i4   0x1000
0x104db  beq.s    loc_104ED
0x104dd  ldarg.0
0x104de  ldfld    class Microsoft.Crm.CrmDbConnection Microsoft.Crm.CrmTransaction::connection
0x104e3  ldc.i4   0x1000
0x104e8  callvirt instance void Microsoft.Crm.CrmDbConnection::SetTransactionIsolationLevel(valuetype [System.Data]System.Data.IsolationLevel il)
0x104ed  ldarg.0
0x104ee  ldfld    class Microsoft.Crm.CrmDbConnection Microsoft.Crm.CrmTransaction::connection
0x104f3  callvirt instance void Microsoft.Crm.CrmDbConnection::Close()
0x104f8  ldarg.0
0x104f9  ldfld    class Microsoft.Crm.CrmTransactionEventManager Microsoft.Crm.CrmTransaction::eventManager
0x104fe  callvirt instance void Microsoft.Crm.CrmTransactionEventManager::UnregisterAllEvents()
0x10503  endfinally
0x10504  ret
```
