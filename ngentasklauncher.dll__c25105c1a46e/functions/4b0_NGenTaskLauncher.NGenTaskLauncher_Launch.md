# NGenTaskLauncher.NGenTaskLauncher::Launch

- ea: `0x4b0`
- end: `0x69b`
- name: `NGenTaskLauncher.NGenTaskLauncher::Launch`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e0`

## callees

- `0x4b0`
- `0x7b0`
- `0x890`
- `0x8c0`

## string_xrefs

- `0x536`: `NGenTask.exe`
- `0x5ca`: `Unable to create event object (error {0})`
- `0x610`: `Launching NGen Task, command line: "{0}" {1}`
- `0x650`: `Launched NGen Task, process ID {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4b0  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x4b5  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x4ba  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x4bf  stloc.0
0x4c0  ldloc.0
0x4c1  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x4c6  stloc.1
0x4c7  ldloc.0
0x4c8  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x4cd  stloc.2
0x4ce  ldloc.2
0x4cf  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x4d4  stloc.3
0x4d5  ldloc.3
0x4d6  ldstr    aFramework64// "Framework64"
0x4db  ldc.i4.5
0x4dc  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x4e1  brtrue.s loc_4FE
0x4e3  ldloc.3
0x4e4  ldstr    aFrameworkarm64// "FrameworkArm64"
0x4e9  ldc.i4.5
0x4ea  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x4ef  brtrue.s loc_4FE
0x4f1  ldarg.3
0x4f2  ldc.i4.2
0x4f3  beq.s    loc_4F9
0x4f5  ldarg.3
0x4f6  ldc.i4.1
0x4f7  bne.un.s loc_4FE
0x4f9  ldloc.0
0x4fa  stloc.s  4
0x4fc  br.s     loc_534
0x4fe  ldarg.3
0x4ff  ldc.i4.2
0x500  bne.un.s loc_50B
0x502  ldstr    aFrameworkarm64// "FrameworkArm64"
0x507  stloc.s  7
0x509  br.s     loc_51F
0x50b  ldarg.3
0x50c  ldc.i4.1
0x50d  bne.un.s loc_518
0x50f  ldstr    aFramework64// "Framework64"
0x514  stloc.s  7
0x516  br.s     loc_51F
0x518  ldstr    aFramework// "Framework"
0x51d  stloc.s  7
0x51f  ldloc.2
0x520  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x525  ldloc.s  7
0x527  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x52c  ldloc.1
0x52d  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x532  stloc.s  4
0x534  ldloc.s  4
0x536  ldstr    aNgentaskExe// "NGenTask.exe"
0x53b  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x540  stloc.s  5
0x542  ldarg.1
0x543  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x548  stloc.s  6
0x54a  ldarg.2
0x54b  brfalse.s loc_55A
0x54d  ldloc.s  6
0x54f  ldstr    aCritical_0// " /Critical"
0x554  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x559  pop
0x55a  ldarg.0
0x55b  ldfld    object NGenTaskLauncher.NGenTaskLauncher::m_stopLock
0x560  stloc.s  8
0x562  ldc.i4.0
0x563  stloc.s  9
0x565  ldloc.s  8
0x567  ldloca.s 9
0x569  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x56e  ldarg.0
0x56f  volatile.
0x571  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTaskLauncher.NGenTaskLauncher::m_stopRequested
0x576  brfalse.s loc_580
0x578  ldc.i4.0
0x579  stloc.s  0xC
0x57b  leave    loc_698
0x580  ldarg.0
0x581  ldc.i4.0
0x582  newobj   instance void [mscorlib]System.Threading.ManualResetEvent::.ctor(bool)
0x587  stfld    class [mscorlib]System.Threading.ManualResetEvent NGenTaskLauncher.NGenTaskLauncher::m_childStopEvent
0x58c  newobj   instance void SECURITY_ATTRIBUTES::.ctor()
0x591  stloc.s  0xA
0x593  ldloc.s  0xA
0x595  ldc.i4.1
0x596  stfld    int32 SECURITY_ATTRIBUTES::bInheritHandle
0x59b  ldarg.0
0x59c  ldfld    class [mscorlib]System.Threading.ManualResetEvent NGenTaskLauncher.NGenTaskLauncher::m_childStopEvent
0x5a1  ldloc.s  0xA
0x5a3  ldc.i4.1
0x5a4  ldc.i4.0
0x5a5  ldnull
0x5a6  call     class [mscorlib]Microsoft.Win32.SafeHandles.SafeWaitHandle NGenTaskLauncher.Win32Native::CreateEvent(class SECURITY_ATTRIBUTES lpSecurityAttributes, bool isManualReset, bool initialState, string name)
0x5ab  callvirt instance void [mscorlib]System.Threading.WaitHandle::set_SafeWaitHandle(class [mscorlib]Microsoft.Win32.SafeHandles.SafeWaitHandle)
0x5b0  ldarg.0
0x5b1  ldfld    class [mscorlib]System.Threading.ManualResetEvent NGenTaskLauncher.NGenTaskLauncher::m_childStopEvent
0x5b6  callvirt instance class [mscorlib]Microsoft.Win32.SafeHandles.SafeWaitHandle [mscorlib]System.Threading.WaitHandle::get_SafeWaitHandle()
0x5bb  callvirt instance bool [mscorlib]System.Runtime.InteropServices.SafeHandle::get_IsInvalid()
0x5c0  brfalse.s loc_5ED
0x5c2  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x5c7  stloc.s  0xD
0x5c9  ldc.i4.0
0x5ca  ldstr    aUnableToCreate// "Unable to create event object (error {0"...
0x5cf  ldc.i4.1
0x5d0  newarr   [mscorlib]System.Object
0x5d5  dup
0x5d6  ldc.i4.0
0x5d7  ldloc.s  0xD
0x5d9  box      [mscorlib]System.Int32
0x5de  stelem.ref
0x5df  call     void NGenTaskLauncher.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x5e4  ldloc.s  0xD
0x5e6  stloc.s  0xC
0x5e8  leave    loc_698
0x5ed  ldloc.s  6
0x5ef  ldstr    aStopevent0// " /StopEvent:{0}"
0x5f4  ldarg.0
0x5f5  ldfld    class [mscorlib]System.Threading.ManualResetEvent NGenTaskLauncher.NGenTaskLauncher::m_childStopEvent
0x5fa  callvirt instance class [mscorlib]Microsoft.Win32.SafeHandles.SafeWaitHandle [mscorlib]System.Threading.WaitHandle::get_SafeWaitHandle()
0x5ff  callvirt instance native int [mscorlib]System.Runtime.InteropServices.SafeHandle::DangerousGetHandle()
0x604  box      [mscorlib]System.IntPtr
0x609  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x60e  pop
0x60f  ldc.i4.2
0x610  ldstr    aLaunchingNgenT// "Launching NGen Task, command line: \"{0"...
0x615  ldc.i4.2
0x616  newarr   [mscorlib]System.Object
0x61b  dup
0x61c  ldc.i4.0
0x61d  ldloc.s  5
0x61f  stelem.ref
0x620  dup
0x621  ldc.i4.1
0x622  ldloc.s  6
0x624  stelem.ref
0x625  call     void NGenTaskLauncher.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x62a  ldloc.s  5
0x62c  ldloc.s  6
0x62e  callvirt instance string [mscorlib]System.Object::ToString()
0x633  newobj   instance void [System]System.Diagnostics.ProcessStartInfo::.ctor(string, string)
0x638  stloc.s  0xB
0x63a  ldloc.s  0xB
0x63c  ldc.i4.0
0x63d  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_UseShellExecute(bool)
0x642  ldarg.0
0x643  ldloc.s  0xB
0x645  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::Start(class [System]System.Diagnostics.ProcessStartInfo)
0x64a  stfld    class [System]System.Diagnostics.Process NGenTaskLauncher.NGenTaskLauncher::m_childProcess
0x64f  ldc.i4.3
0x650  ldstr    aLaunchedNgenTa// "Launched NGen Task, process ID {0}"
0x655  ldc.i4.1
0x656  newarr   [mscorlib]System.Object
0x65b  dup
0x65c  ldc.i4.0
0x65d  ldarg.0
0x65e  ldfld    class [System]System.Diagnostics.Process NGenTaskLauncher.NGenTaskLauncher::m_childProcess
0x663  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x668  box      [mscorlib]System.Int32
0x66d  stelem.ref
0x66e  call     void NGenTaskLauncher.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x673  leave.s  loc_681
0x675  ldloc.s  9
0x677  brfalse.s loc_680
0x679  ldloc.s  8
0x67b  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x680  endfinally
0x681  ldarg.0
0x682  ldfld    class [System]System.Diagnostics.Process NGenTaskLauncher.NGenTaskLauncher::m_childProcess
0x687  callvirt instance void [System]System.Diagnostics.Process::WaitForExit()
0x68c  ldarg.0
0x68d  ldfld    class [System]System.Diagnostics.Process NGenTaskLauncher.NGenTaskLauncher::m_childProcess
0x692  callvirt instance int32 [System]System.Diagnostics.Process::get_ExitCode()
0x697  ret
0x698  ldloc.s  0xC
0x69a  ret
```
