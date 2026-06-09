# Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::CallPackageDeploymentExecutor

- ea: `0x6e00`
- end: `0x6fc5`
- name: `Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::CallPackageDeploymentExecutor`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x64f0`

## callees

- `0x6e00`
- `0x7110`
- `0x195a0`

## string_xrefs

- `0x6f7a`: `PackageDeploymentExecutor failed to complete in {0} minutes.`

## pseudocode

```c

```

## disassembly

```asm
0x6e00  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x6e05  stloc.0
0x6e06  ldc.i4.0
0x6e07  stloc.1
0x6e08  ldloc.0
0x6e09  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6e0e  stfld    class [mscorlib]System.Collections.Generic.IList`1<string> <>c__DisplayClass1_0::pdLogs
0x6e13  newobj   instance void [System]System.Diagnostics.Process::.ctor()
0x6e18  stloc.2
0x6e19  ldloc.2
0x6e1a  ldloc.0
0x6e1b  ldftn    instance void <>c__DisplayClass1_0::<CallPackageDeploymentExecutor>b__0(object proc, class [System]System.Diagnostics.DataReceivedEventArgs output)
0x6e21  newobj   instance void [System]System.Diagnostics.DataReceivedEventHandler::.ctor(object, native int)
0x6e26  callvirt instance void [System]System.Diagnostics.Process::add_OutputDataReceived(class [System]System.Diagnostics.DataReceivedEventHandler)
0x6e2b  ldloc.2
0x6e2c  ldloc.0
0x6e2d  ldftn    instance void <>c__DisplayClass1_0::<CallPackageDeploymentExecutor>b__1(object proc, class [System]System.Diagnostics.DataReceivedEventArgs output)
0x6e33  newobj   instance void [System]System.Diagnostics.DataReceivedEventHandler::.ctor(object, native int)
0x6e38  callvirt instance void [System]System.Diagnostics.Process::add_ErrorDataReceived(class [System]System.Diagnostics.DataReceivedEventHandler)
0x6e3d  ldstr    aFile// "file:\\"
0x6e42  stloc.3
0x6e43  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x6e48  callvirt instance string [mscorlib]System.Reflection.Assembly::get_CodeBase()
0x6e4d  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x6e52  stloc.s  4
0x6e54  ldloc.s  4
0x6e56  ldloc.3
0x6e57  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x6e5c  brfalse.s loc_6E6D
0x6e5e  ldloc.s  4
0x6e60  ldloc.3
0x6e61  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6e66  callvirt instance string [mscorlib]System.String::Substring(int32)
0x6e6b  stloc.s  4
0x6e6d  ldloc.2
0x6e6e  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x6e73  ldloc.s  4
0x6e75  ldstr    aMicrosoftCrmPa// "Microsoft.Crm.PackageDeploymentExecutor"...
0x6e7a  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x6e7f  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_FileName(string)
0x6e84  ldloc.2
0x6e85  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x6e8a  ldstr    asc_20254// " "
0x6e8f  ldarg.0
0x6e90  call     string [mscorlib]System.String::Join(string, string[])
0x6e95  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_Arguments(string)
0x6e9a  ldloc.2
0x6e9b  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x6ea0  ldc.i4.0
0x6ea1  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_UseShellExecute(bool)
0x6ea6  ldloc.2
0x6ea7  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x6eac  ldc.i4.1
0x6ead  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_RedirectStandardError(bool)
0x6eb2  ldloc.2
0x6eb3  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x6eb8  ldc.i4.1
0x6eb9  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_RedirectStandardOutput(bool)
0x6ebe  ldloc.2
0x6ebf  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x6ec4  ldc.i4.1
0x6ec5  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_RedirectStandardInput(bool)
0x6eca  ldloc.2
0x6ecb  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x6ed0  ldc.i4.1
0x6ed1  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_CreateNoWindow(bool)
0x6ed6  ldstr    aLookingForMicr// "Looking for Microsoft.Crm.PackageDeploy"...
0x6edb  ldc.i4.1
0x6edc  newarr   [mscorlib]System.Object
0x6ee1  dup
0x6ee2  ldc.i4.0
0x6ee3  ldloc.2
0x6ee4  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x6ee9  callvirt instance string [System]System.Diagnostics.ProcessStartInfo::get_FileName()
0x6eee  stelem.ref
0x6eef  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x6ef4  ldloc.2
0x6ef5  callvirt instance bool [System]System.Diagnostics.Process::Start()
0x6efa  pop
0x6efb  ldloc.2
0x6efc  callvirt instance class [mscorlib]System.IO.StreamWriter [System]System.Diagnostics.Process::get_StandardInput()
0x6f01  stloc.s  5
0x6f03  ldloc.s  5
0x6f05  call     string [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::CaptureRoot()
0x6f0a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6f0f  leave.s  loc_6F1D
0x6f11  ldloc.s  5
0x6f13  brfalse.s loc_6F1C
0x6f15  ldloc.s  5
0x6f17  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6f1c  endfinally
0x6f1d  ldloc.2
0x6f1e  callvirt instance void [System]System.Diagnostics.Process::BeginOutputReadLine()
0x6f23  ldloc.2
0x6f24  callvirt instance void [System]System.Diagnostics.Process::BeginErrorReadLine()
0x6f29  ldloc.2
0x6f2a  call     void [Microsoft.Xrm.ProcessUtils]Microsoft.Xrm.ProcessUtils.ChildProcessTracker::AddProcess(class [System]System.Diagnostics.Process)
0x6f2f  ldloc.2
0x6f30  ldsfld   int32 Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::MaxPackageInstallTimeInMinutes
0x6f35  conv.r8
0x6f36  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x6f3b  stloc.s  6
0x6f3d  ldloca.s 6
0x6f3f  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x6f44  conv.i4
0x6f45  callvirt instance bool [System]System.Diagnostics.Process::WaitForExit(int32)
0x6f4a  brtrue.s loc_6F97
0x6f4c  ldloc.2
0x6f4d  callvirt instance bool [System]System.Diagnostics.Process::get_HasExited()
0x6f52  brtrue.s loc_6F5A
0x6f54  ldloc.2
0x6f55  callvirt instance void [System]System.Diagnostics.Process::Kill()
0x6f5a  leave.s  loc_6F7A
0x6f5c  stloc.s  7
0x6f5e  ldstr    aFailedToKillPa// "Failed to kill PackageDeploymentExecuto"...
0x6f63  ldc.i4.1
0x6f64  newarr   [mscorlib]System.Object
0x6f69  dup
0x6f6a  ldc.i4.0
0x6f6b  ldloc.s  7
0x6f6d  callvirt instance string [mscorlib]System.Object::ToString()
0x6f72  stelem.ref
0x6f73  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0x6f78  leave.s  loc_6F7A
0x6f7a  ldstr    aPackagedeploym// "PackageDeploymentExecutor failed to com"...
0x6f7f  ldc.i4.1
0x6f80  newarr   [mscorlib]System.Object
0x6f85  dup
0x6f86  ldc.i4.0
0x6f87  ldsfld   int32 Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::MaxPackageInstallTimeInMinutes
0x6f8c  box      [mscorlib]System.Int32
0x6f91  stelem.ref
0x6f92  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x6f97  ldloc.2
0x6f98  callvirt instance bool [System]System.Diagnostics.Process::get_HasExited()
0x6f9d  brfalse.s loc_6FAA
0x6f9f  ldloc.2
0x6fa0  callvirt instance int32 [System]System.Diagnostics.Process::get_ExitCode()
0x6fa5  ldc.i4.0
0x6fa6  ceq
0x6fa8  br.s     loc_6FAB
0x6faa  ldc.i4.0
0x6fab  stloc.1
0x6fac  leave.s  loc_6FB8
0x6fae  ldloc.2
0x6faf  brfalse.s loc_6FB7
0x6fb1  ldloc.2
0x6fb2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6fb7  endfinally
0x6fb8  ldloc.1
0x6fb9  ldloc.0
0x6fba  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> <>c__DisplayClass1_0::pdLogs
0x6fbf  newobj   instance void Microsoft.Crm.Tools.Admin.PackageDeployerResult::.ctor(bool isSuccess, class [mscorlib]System.Collections.Generic.IList`1<string> pdInfoLog)
0x6fc4  ret
```
