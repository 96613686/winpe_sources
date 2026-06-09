# Microsoft.Crm.ClientSqlUtility::StartSqlService

- ea: `0x1d040`
- end: `0x1d117`
- name: `Microsoft.Crm.ClientSqlUtility::StartSqlService`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1cf00`
- `0x1cf60`
- `0x1d040`

## string_xrefs

- `0x1d065`: `Failed to acquire shared filelock while starting Sql service: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1d040  ldsfld   class Microsoft.Crm.ServiceLock Microsoft.Crm.ClientSqlUtility::_sqlLock
0x1d045  brtrue.s loc_1D05B
0x1d047  newobj   instance void Microsoft.Crm.ServiceLock::.ctor()
0x1d04c  stsfld   class Microsoft.Crm.ServiceLock Microsoft.Crm.ClientSqlUtility::_sqlLock
0x1d051  ldsfld   class Microsoft.Crm.ServiceLock Microsoft.Crm.ClientSqlUtility::_sqlLock
0x1d056  callvirt instance void Microsoft.Crm.ServiceLock::Lock()
0x1d05b  leave.s  loc_1D07B
0x1d05d  stloc.0
0x1d05e  ldloc.0
0x1d05f  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::ClientContextOrganizationId
0x1d064  ldc.i4.1
0x1d065  ldstr    aFailedToAcquir// "Failed to acquire shared filelock while"...
0x1d06a  ldc.i4.1
0x1d06b  newarr   [mscorlib]System.Object
0x1d070  dup
0x1d071  ldc.i4.0
0x1d072  ldloc.0
0x1d073  stelem.ref
0x1d074  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1d079  leave.s  loc_1D07B
0x1d07b  ldarg.1
0x1d07c  newobj   instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::.ctor(string)
0x1d081  stloc.1
0x1d082  ldloc.1
0x1d083  ldarg.2
0x1d084  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::set_MachineName(string)
0x1d089  ldc.i4.4
0x1d08a  ldloc.1
0x1d08b  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0x1d090  beq.s    loc_1D10A
0x1d092  ldarg.1
0x1d093  newobj   instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::.ctor(string)
0x1d098  stloc.2
0x1d099  ldc.i4.3
0x1d09a  ldloc.2
0x1d09b  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0x1d0a0  bne.un.s loc_1D0AA
0x1d0a2  ldloc.2
0x1d0a3  ldc.i4.1
0x1d0a4  ldarg.0
0x1d0a5  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0x1d0aa  leave.s  loc_1D0B6
0x1d0ac  ldloc.2
0x1d0ad  brfalse.s loc_1D0B5
0x1d0af  ldloc.2
0x1d0b0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d0b5  endfinally
0x1d0b6  ldarg.1
0x1d0b7  newobj   instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::.ctor(string)
0x1d0bc  stloc.3
0x1d0bd  ldc.i4.2
0x1d0be  ldloc.3
0x1d0bf  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0x1d0c4  bne.un.s loc_1D0CE
0x1d0c6  ldloc.3
0x1d0c7  ldc.i4.4
0x1d0c8  ldarg.0
0x1d0c9  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0x1d0ce  leave.s  loc_1D0DA
0x1d0d0  ldloc.3
0x1d0d1  brfalse.s loc_1D0D9
0x1d0d3  ldloc.3
0x1d0d4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d0d9  endfinally
0x1d0da  ldarg.1
0x1d0db  newobj   instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::.ctor(string)
0x1d0e0  stloc.s  4
0x1d0e2  ldc.i4.4
0x1d0e3  ldloc.s  4
0x1d0e5  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0x1d0ea  beq.s    loc_1D0FC
0x1d0ec  ldloc.s  4
0x1d0ee  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::Start()
0x1d0f3  ldloc.s  4
0x1d0f5  ldc.i4.4
0x1d0f6  ldarg.0
0x1d0f7  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0x1d0fc  leave.s  loc_1D116
0x1d0fe  ldloc.s  4
0x1d100  brfalse.s loc_1D109
0x1d102  ldloc.s  4
0x1d104  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d109  endfinally
0x1d10a  leave.s  loc_1D116
0x1d10c  ldloc.1
0x1d10d  brfalse.s loc_1D115
0x1d10f  ldloc.1
0x1d110  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d115  endfinally
0x1d116  ret
```
