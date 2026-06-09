# Microsoft.Crm.Sandbox.SandboxWorker::UpdateStartTimes

- ea: `0x35f0`
- end: `0x3627`
- name: `Microsoft.Crm.Sandbox.SandboxWorker::UpdateStartTimes`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3470`

## callees

- `0x35f0`

## pseudocode

```c

```

## disassembly

```asm
0x35f0  ldsfld   bool Microsoft.Crm.Sandbox.SandboxAppDomainManager::WarmUpInProgress
0x35f5  brtrue.s loc_3626
0x35f7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x35fc  stsfld   valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxWorker::_lastExecuteTime
0x3601  ldsfld   valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxWorker::_executeStartTime
0x3606  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x360b  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3610  brfalse.s loc_3626
0x3612  ldsfld   valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxWorker::_lastExecuteTime
0x3617  stsfld   valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxWorker::_executeStartTime
0x361c  ldsfld   valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxWorker::_lastExecuteTime
0x3621  stsfld   valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxWorker::_appDomainExecuteStartTime
0x3626  ret
```
