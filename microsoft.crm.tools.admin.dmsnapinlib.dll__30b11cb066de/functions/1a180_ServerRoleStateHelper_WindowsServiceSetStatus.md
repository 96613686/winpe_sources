# ServerRoleStateHelper::WindowsServiceSetStatus

- ea: `0x1a180`
- end: `0x1a242`
- name: `ServerRoleStateHelper::WindowsServiceSetStatus`
- size: `194`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1a080`
- `0x1a0b0`
- `0x1a0e0`
- `0x1a130`

## callees

- `0x1a180`

## string_xrefs

- `0x1a214`: `Service ({0}) from machine ({1}) got an error and cannot be {3}. Exception: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x1a180  ldloca.s 0
0x1a182  ldc.i4.0
0x1a183  ldc.i4.2
0x1a184  ldc.i4.0
0x1a185  call     instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x1a18a  ldarg.1
0x1a18b  ldarg.0
0x1a18c  newobj   instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::.ctor(string, string)
0x1a191  stloc.1
0x1a192  ldarg.2
0x1a193  ldc.i4.1
0x1a194  bne.un.s loc_1A1AB
0x1a196  ldloc.1
0x1a197  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0x1a19c  stloc.3
0x1a19d  ldc.i4.4
0x1a19e  ldloc.3
0x1a19f  beq.s    loc_1A1AB
0x1a1a1  ldc.i4.2
0x1a1a2  ldloc.3
0x1a1a3  beq.s    loc_1A1AB
0x1a1a5  ldloc.1
0x1a1a6  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::Start()
0x1a1ab  ldarg.2
0x1a1ac  brtrue.s loc_1A1C6
0x1a1ae  ldloc.1
0x1a1af  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0x1a1b4  stloc.s  4
0x1a1b6  ldc.i4.1
0x1a1b7  ldloc.s  4
0x1a1b9  beq.s    loc_1A1C6
0x1a1bb  ldc.i4.3
0x1a1bc  ldloc.s  4
0x1a1be  beq.s    loc_1A1C6
0x1a1c0  ldloc.1
0x1a1c1  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::Stop()
0x1a1c6  ldc.i4.1
0x1a1c7  ldarg.2
0x1a1c8  beq.s    loc_1A1CD
0x1a1ca  ldc.i4.1
0x1a1cb  br.s     loc_1A1CE
0x1a1cd  ldc.i4.4
0x1a1ce  stloc.2
0x1a1cf  ldloc.1
0x1a1d0  ldloc.2
0x1a1d1  ldloc.0
0x1a1d2  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0x1a1d7  leave.s  loc_1A1E3
0x1a1d9  ldloc.1
0x1a1da  brfalse.s loc_1A1E2
0x1a1dc  ldloc.1
0x1a1dd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a1e2  endfinally
0x1a1e3  leave.s  loc_1A23D
0x1a1e5  stloc.s  5
0x1a1e7  ldloc.s  5
0x1a1e9  isinst   [Microsoft.Crm.Core]Microsoft.Crm.TimeoutException
0x1a1ee  brtrue.s loc_1A202
0x1a1f0  ldloc.s  5
0x1a1f2  isinst   [System]System.ComponentModel.Win32Exception
0x1a1f7  brtrue.s loc_1A202
0x1a1f9  ldloc.s  5
0x1a1fb  isinst   [mscorlib]System.InvalidOperationException
0x1a200  brfalse.s loc_1A23B
0x1a202  ldc.i4.1
0x1a203  ldarg.2
0x1a204  beq.s    loc_1A20D
0x1a206  ldstr    aStopped// "stopped"
0x1a20b  br.s     loc_1A212
0x1a20d  ldstr    aStarted// "started"
0x1a212  stloc.s  6
0x1a214  ldstr    aService0FromMa// "Service ({0}) from machine ({1}) got an"...
0x1a219  ldc.i4.4
0x1a21a  newarr   [mscorlib]System.Object
0x1a21f  dup
0x1a220  ldc.i4.0
0x1a221  ldarg.1
0x1a222  stelem.ref
0x1a223  dup
0x1a224  ldc.i4.1
0x1a225  ldarg.0
0x1a226  stelem.ref
0x1a227  dup
0x1a228  ldc.i4.2
0x1a229  ldloc.s  5
0x1a22b  stelem.ref
0x1a22c  dup
0x1a22d  ldc.i4.3
0x1a22e  ldloc.s  6
0x1a230  stelem.ref
0x1a231  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x1a236  ldc.i4.0
0x1a237  stloc.s  7
0x1a239  leave.s  loc_1A23F
0x1a23b  rethrow
0x1a23d  ldc.i4.1
0x1a23e  ret
0x1a23f  ldloc.s  7
0x1a241  ret
```
