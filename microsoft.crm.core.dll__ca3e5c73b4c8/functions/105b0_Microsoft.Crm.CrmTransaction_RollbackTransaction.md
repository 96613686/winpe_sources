# Microsoft.Crm.CrmTransaction::RollbackTransaction

- ea: `0x105b0`
- end: `0x106a0`
- name: `Microsoft.Crm.CrmTransaction::RollbackTransaction`
- size: `240`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x11d00`
- `0x12000`

## callees

- `0xd140`
- `0xd150`
- `0xd380`
- `0xd8e0`
- `0x105b0`
- `0x106a0`
- `0x10d90`
- `0x11120`
- `0x1b8d0`
- `0x1bb60`
- `0x1d020`
- `0x1eaa0`
- `0x1f510`
- `0x51500`
- `0x51530`
- `0x55d00`
- `0x56ad0`
- `0x56d90`

## string_xrefs

- `0x105bd`: `RollbackTransaction - Encountered disposed Transaction when it should not be disposed`
- `0x105fa`: `InvokeRollbackEvents Failed in transaction.rollback(). Rollback will continue: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x105b0  ldarg.0
0x105b1  ldfld    bool Microsoft.Crm.CrmTransaction::disposed
0x105b6  brfalse.s loc_105C8
0x105b8  ldstr    aCrmtransaction// "CrmTransaction"
0x105bd  ldstr    aRollbacktransa// "RollbackTransaction - Encountered dispo"...
0x105c2  newobj   instance void Microsoft.Crm.CrmObjectDisposedException::.ctor(string objectName, string message)
0x105c7  throw
0x105c8  ldarg.0
0x105c9  ldfld    int32 Microsoft.Crm.CrmTransaction::startCount
0x105ce  brtrue.s loc_105D1
0x105d0  ret
0x105d1  nop
0x105d2  ldarg.0
0x105d3  ldfld    class Microsoft.Crm.CrmTransactionEventManager Microsoft.Crm.CrmTransaction::eventManager
0x105d8  callvirt instance void Microsoft.Crm.CrmTransactionEventManager::InvokeRollbackTransactionEvents()
0x105dd  leave.s  loc_1061B
0x105df  stloc.0
0x105e0  ldloc.0
0x105e1  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x105e6  ldc.i4.s 0x1D
0x105e8  ldstr    a0// "{0}"
0x105ed  ldc.i4.1
0x105ee  newarr   [mscorlib]System.Object
0x105f3  dup
0x105f4  ldc.i4.0
0x105f5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x105fa  ldstr    aInvokerollback// "InvokeRollbackEvents Failed in transact"...
0x105ff  ldc.i4.1
0x10600  newarr   [mscorlib]System.Object
0x10605  dup
0x10606  ldc.i4.0
0x10607  ldloc.0
0x10608  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1060d  stelem.ref
0x1060e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10613  stelem.ref
0x10614  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x10619  leave.s  loc_1061B
0x1061b  newobj   instance void Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x10620  pop
0x10621  ldarg.0
0x10622  call     instance void Microsoft.Crm.CrmTransaction::TryRollbackTransaction()
0x10627  call     class Microsoft.Crm.Core.Diagnostics.EventSources.CoreDiagnosticsEventSource Microsoft.Crm.Core.Diagnostics.EventSources.CoreDiagnosticsEventSource::get_Instance()
0x1062c  ldarg.0
0x1062d  ldfld    class Microsoft.Crm.CrmDbConnection Microsoft.Crm.CrmTransaction::connection
0x10632  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0x10637  call     string Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0x1063c  call     string Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x10641  call     string [mscorlib]System.Environment::get_StackTrace()
0x10646  call     string Microsoft.Crm.MetricsReporting::get_CurrentRequestId()
0x1064b  callvirt instance void Microsoft.Crm.Core.Diagnostics.EventSources.CoreDiagnosticsEventSource::DBTransactionRollbackDiagnostics(valuetype [mscorlib]System.Guid organizationId, string userPuid, string applicationVersion, string environmentStackTrace, string reqId)
0x10650  ldarg.0
0x10651  ldfld    class Microsoft.Crm.CrmTransactionEventManager Microsoft.Crm.CrmTransaction::eventManager
0x10656  callvirt instance void Microsoft.Crm.CrmTransactionEventManager::UnregisterAllEvents()
0x1065b  ldarg.0
0x1065c  ldnull
0x1065d  stfld    class [System.Data]System.Data.IDbTransaction Microsoft.Crm.CrmTransaction::transaction
0x10662  ldarg.0
0x10663  ldc.i4.0
0x10664  stfld    int32 Microsoft.Crm.CrmTransaction::startCount
0x10669  ldarg.0
0x1066a  ldfld    class Microsoft.Crm.CrmDbConnection Microsoft.Crm.CrmTransaction::connection
0x1066f  callvirt instance valuetype [System.Data]System.Data.IsolationLevel Microsoft.Crm.CrmDbConnection::get_IsolationLevel()
0x10674  ldc.i4   0x1000
0x10679  beq.s    loc_1068B
0x1067b  ldarg.0
0x1067c  ldfld    class Microsoft.Crm.CrmDbConnection Microsoft.Crm.CrmTransaction::connection
0x10681  ldc.i4   0x1000
0x10686  callvirt instance void Microsoft.Crm.CrmDbConnection::SetTransactionIsolationLevel(valuetype [System.Data]System.Data.IsolationLevel il)
0x1068b  ldarg.0
0x1068c  ldfld    class Microsoft.Crm.CrmDbConnection Microsoft.Crm.CrmTransaction::connection
0x10691  callvirt instance void Microsoft.Crm.CrmDbConnection::Close()
0x10696  ldarg.1
0x10697  brfalse.s loc_1069F
0x10699  newobj   instance void Microsoft.Crm.CrmTransactionAbortedException::.ctor()
0x1069e  throw
0x1069f  ret
```
