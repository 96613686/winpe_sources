# UpdateStateAndStatusCommand::<InternalExecute>b__1_0

- ea: `0x16870`
- end: `0x168a5`
- name: `UpdateStateAndStatusCommand::<InternalExecute>b__1_0`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3960`
- `0x165c0`
- `0x166b0`
- `0x16870`

## pseudocode

```c

```

## disassembly

```asm
0x16870  ldarg.0
0x16871  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> UpdateStateAndStatusCommand::GetCustomProperties()
0x16876  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x1687b  ldarg.0
0x1687c  ldc.i4.0
0x1687d  call     instance bool UpdateStateAndStatusCommand::TryRemoveEvent(bool statusUpdated)
0x16882  brfalse.s loc_16885
0x16884  ret
0x16885  ldarg.0
0x16886  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess UpdateStateAndStatusCommand::_queueDataAccess
0x1688b  ldarg.0
0x1688c  ldfld    class Microsoft.Crm.Asynchronous.AsyncEventState UpdateStateAndStatusCommand::_newEventState
0x16891  ldarg.0
0x16892  ldfld    bool UpdateStateAndStatusCommand::_checkForCompletedJobs
0x16897  callvirt instance void Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::UpdateStateAndStatusInternal(class Microsoft.Crm.Asynchronous.AsyncEventState newEventState, [opt] bool checkForCompletedJob)
0x1689c  ldarg.0
0x1689d  ldc.i4.1
0x1689e  call     instance bool UpdateStateAndStatusCommand::TryRemoveEvent(bool statusUpdated)
0x168a3  pop
0x168a4  ret
```
