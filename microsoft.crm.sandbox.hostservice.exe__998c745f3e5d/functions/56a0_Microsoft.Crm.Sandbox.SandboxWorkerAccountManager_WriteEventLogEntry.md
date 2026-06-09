# Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::WriteEventLogEntry

- ea: `0x56a0`
- end: `0x56d7`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::WriteEventLogEntry`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x51e0`
- `0x5280`
- `0x5470`

## callees

- `0x56a0`

## string_xrefs

- `0x56a7`: `MSCRMSandboxService`

## pseudocode

```c

```

## disassembly

```asm
0x56a0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x56a5  stloc.0
0x56a6  ldloc.0
0x56a7  ldstr    aMscrmsandboxse// "MSCRMSandboxService"
0x56ac  ldc.i4.1
0x56ad  ldc.i4   0xC0004F11
0x56b2  conv.u8
0x56b3  ldc.i4.2
0x56b4  newarr   [mscorlib]System.Object
0x56b9  dup
0x56ba  ldc.i4.0
0x56bb  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0x56c0  stelem.ref
0x56c1  dup
0x56c2  ldc.i4.1
0x56c3  ldarg.0
0x56c4  stelem.ref
0x56c5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x56ca  leave.s  loc_56D6
0x56cc  ldloc.0
0x56cd  brfalse.s loc_56D5
0x56cf  ldloc.0
0x56d0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x56d5  endfinally
0x56d6  ret
```
