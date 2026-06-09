# Microsoft.Crm.Sandbox.SandboxWorkerNativeProcess::CreateProcess

- ea: `0x8e50`
- end: `0x9470`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerNativeProcess::CreateProcess`
- size: `1568`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x50f0`
- `0x5100`
- `0x5120`
- `0x5140`
- `0x5150`
- `0x5190`
- `0x51a0`
- `0x5310`
- `0x5340`
- `0x8e50`
- `0x9720`

## string_xrefs

- `0x8f0a`: `MSCRMSandboxService`
- `0x90f2`: `MSCRMSandboxService`
- `0x9180`: `MSCRMSandboxService`
- `0x922f`: `MSCRMSandboxService`
- `0x8e57`: `SandboxWorkerNativeProcess.CreateWorkerProcess`
- `0x8ed7`: `SandboxWorkerNativeProcess.CreateProcess: Unable to create the worker process because the argument length exceeded the maximum length of {0}. Arguments: {1}`
- `0x8f7c`: `SandboxWorkerNativeProcess.CreateWorkerProcess: {0}`
- `0x90c6`: `SandboxWorkerNativeProcess.CreateProcess: Error logging on user {0} - Exception : {1}`
- `0x910e`: `SandboxWorkerNativeProcess.CreateProcess: Unable to Log on to the local user due to exception: {0}`
- `0x9162`: `SandboxWorkerNativeProcess.CreateProcess: Error Duplicating the security token - Exception : {1}`
- `0x919c`: `SandboxWorkerNativeProcess.CreateProcess: Unable to duplicate the security token of the local user due to exception: {0}. Please make sure the account running the SandboxProcessingService has the necessary user rights.`
- `0x9203`: `SandboxWorkerNativeProcess.CreateProcess: Error launching workerProcess as user {0} : {1}`
- `0x924b`: `SandboxWorkerNativeProcess.CreateProcess: Unable to create the worker process as local user {0} due to exception: {1}. Please make sure the account running the SandboxProcessingService has the user right "Replace a process level token".`
- `0x92e1`: `SandboxWorkerNativeProcess.CreateProcess: Error launching workerProcess using native method : {0}`
- `0x93ac`: `CreateProcess() failed with Win32Exception: {0}. FilePath:{1} Argument:{2}`
- `0x93e1`: `SandboxWorkerNativeProcess.CreateProcess: CreateProcess() failed with ArgumentException: {0}. `
- `0x9432`: `SandboxWorkerNativeProcess:Thread[{0:d4}]: Spent {1} secs in in CreateWorkerProcess`

## pseudocode

```c

```

## disassembly

```asm
0x8e50  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8e55  ldc.i4.s 0x21
0x8e57  ldstr    aSandboxworkern// "SandboxWorkerNativeProcess.CreateWorker"...
0x8e5c  ldc.i4.0
0x8e5d  newarr   [mscorlib]System.Object
0x8e62  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8e67  ldarg.0
0x8e68  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::WorkerPort
0x8e6d  ldstr    aPort// "port"
0x8e72  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNotPositive(int32, string)
0x8e77  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x8e7c  stloc.0
0x8e7d  ldnull
0x8e7e  stloc.1
0x8e7f  ldstr    a01234// "{0} {1} {2} {3} {4}"
0x8e84  ldc.i4.5
0x8e85  newarr   [mscorlib]System.Object
0x8e8a  dup
0x8e8b  ldc.i4.0
0x8e8c  ldarg.0
0x8e8d  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerId()
0x8e92  box      [mscorlib]System.Guid
0x8e97  stelem.ref
0x8e98  dup
0x8e99  ldc.i4.1
0x8e9a  ldarg.0
0x8e9b  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::WorkerPort
0x8ea0  box      [mscorlib]System.Int32
0x8ea5  stelem.ref
0x8ea6  dup
0x8ea7  ldc.i4.2
0x8ea8  ldc.i4.0
0x8ea9  box      [mscorlib]System.Boolean
0x8eae  stelem.ref
0x8eaf  dup
0x8eb0  ldc.i4.3
0x8eb1  ldsfld   class [mscorlib]System.Lazy`1<string> Microsoft.Crm.Sandbox.SandboxWorkerProcess::SandboxFilesPath
0x8eb6  callvirt instance var<u1> class [mscorlib]System.Lazy`1<string>::get_Value()
0x8ebb  stelem.ref
0x8ebc  dup
0x8ebd  ldc.i4.4
0x8ebe  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_TraceCategories()
0x8ec3  stelem.ref
0x8ec4  call     string [mscorlib]System.String::Format(string, object[])
0x8ec9  stloc.2
0x8eca  ldloc.2
0x8ecb  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8ed0  ldc.i4   0x7FE
0x8ed5  blt.s    loc_8F3D
0x8ed7  ldstr    aSandboxworkern_0// "SandboxWorkerNativeProcess.CreateProces"...
0x8edc  ldc.i4   0x7FE
0x8ee1  box      [mscorlib]System.Int32
0x8ee6  ldloc.2
0x8ee7  call     string [mscorlib]System.String::Format(string, object, object)
0x8eec  stloc.3
0x8eed  ldnull
0x8eee  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8ef3  ldc.i4.s 0x26
0x8ef5  ldloc.3
0x8ef6  ldc.i4.0
0x8ef7  newarr   [mscorlib]System.Object
0x8efc  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8f01  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x8f06  stloc.s  4
0x8f08  ldloc.s  4
0x8f0a  ldstr    aMscrmsandboxse// "MSCRMSandboxService"
0x8f0f  ldc.i4.1
0x8f10  ldc.i4   0xC0004F11
0x8f15  conv.u8
0x8f16  ldc.i4.2
0x8f17  newarr   [mscorlib]System.Object
0x8f1c  dup
0x8f1d  ldc.i4.0
0x8f1e  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0x8f23  stelem.ref
0x8f24  dup
0x8f25  ldc.i4.1
0x8f26  ldloc.3
0x8f27  stelem.ref
0x8f28  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x8f2d  leave.s  loc_8F3B
0x8f2f  ldloc.s  4
0x8f31  brfalse.s loc_8F3A
0x8f33  ldloc.s  4
0x8f35  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8f3a  endfinally
0x8f3b  ldnull
0x8f3c  ret
0x8f3d  nop
0x8f3e  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x8f43  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x8f48  ldc.i4.2
0x8f49  bne.un.s loc_8F54
0x8f4b  ldarg.0
0x8f4c  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::DisableNativeMethodCreate
0x8f51  ldc.i4.0
0x8f52  bgt.s    loc_8F6F
0x8f54  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x8f59  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x8f5e  ldc.i4.1
0x8f5f  bne.un   loc_9015
0x8f64  ldarg.0
0x8f65  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerNativeProcess::enableWorkerProcessAccountIsolation
0x8f6a  brtrue   loc_9015
0x8f6f  newobj   instance void [System]System.Diagnostics.Process::.ctor()
0x8f74  stloc.1
0x8f75  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8f7a  ldc.i4.s 0x21
0x8f7c  ldstr    aSandboxworkern_1// "SandboxWorkerNativeProcess.CreateWorker"...
0x8f81  ldc.i4.1
0x8f82  newarr   [mscorlib]System.Object
0x8f87  dup
0x8f88  ldc.i4.0
0x8f89  ldarg.0
0x8f8a  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerNativeProcess::_filePath
0x8f8f  stelem.ref
0x8f90  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8f95  ldstr    aNativeprocessu// "NativeProcessUseShellExecute"
0x8f9a  ldc.i4.0
0x8f9b  box      [mscorlib]System.Int32
0x8fa0  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x8fa5  unbox.any [mscorlib]System.Int32
0x8faa  ldc.i4.0
0x8fab  cgt
0x8fad  stloc.s  5
0x8faf  ldloc.1
0x8fb0  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x8fb5  ldarg.0
0x8fb6  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerNativeProcess::_filePath
0x8fbb  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_FileName(string)
0x8fc0  ldloc.1
0x8fc1  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x8fc6  ldloc.2
0x8fc7  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_Arguments(string)
0x8fcc  ldloc.1
0x8fcd  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x8fd2  ldc.i4.1
0x8fd3  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_CreateNoWindow(bool)
0x8fd8  ldloc.1
0x8fd9  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x8fde  ldc.i4.0
0x8fdf  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_RedirectStandardError(bool)
0x8fe4  ldloc.1
0x8fe5  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x8fea  ldc.i4.0
0x8feb  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_RedirectStandardOutput(bool)
0x8ff0  ldloc.1
0x8ff1  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x8ff6  ldloc.s  5
0x8ff8  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_UseShellExecute(bool)
0x8ffd  ldloc.1
0x8ffe  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x9003  ldc.i4.2
0x9004  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_WindowStyle(valuetype [System]System.Diagnostics.ProcessWindowStyle)
0x9009  ldloc.1
0x900a  callvirt instance bool [System]System.Diagnostics.Process::Start()
0x900f  pop
0x9010  br       loc_939C
0x9015  ldstr    a0_0// "0 "
0x901a  ldloc.2
0x901b  call     string [mscorlib]System.String::Concat(string, string)
0x9020  stloc.2
0x9021  ldc.i4.0
0x9022  stloc.s  6
0x9024  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x9029  stloc.s  7
0x902b  ldloca.s 8
0x902d  initobj  Microsoft.Crm.Sandbox.STARTUPINFO
0x9033  ldloca.s 8
0x9035  ldstr    asc_F0E8// ""
0x903a  stfld    string Microsoft.Crm.Sandbox.STARTUPINFO::Desktop
0x903f  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x9044  stloc.s  9
0x9046  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x904b  stloc.s  0xA
0x904d  ldloca.s 0xB
0x904f  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x9054  stfld    native int Microsoft.Crm.Sandbox.PROCESS_INFORMATION::Process
0x9059  ldloca.s 0xB
0x905b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x9060  stfld    native int Microsoft.Crm.Sandbox.PROCESS_INFORMATION::Thread
0x9065  ldarg.0
0x9066  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerNativeProcess::enableWorkerProcessAccountIsolation
0x906b  ldc.i4.0
0x906c  ble      loc_92A6
0x9071  ldarg.0
0x9072  call     class Microsoft.Crm.Sandbox.SandboxWorkerAccount Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::GetUnusedAccount()
0x9077  stfld    class Microsoft.Crm.Sandbox.SandboxWorkerAccount Microsoft.Crm.Sandbox.SandboxWorkerNativeProcess::accountDetails
0x907c  ldarg.0
0x907d  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerAccount Microsoft.Crm.Sandbox.SandboxWorkerNativeProcess::accountDetails
0x9082  brtrue.s loc_908C
0x9084  ldloc.1
0x9085  stloc.s  0xD
0x9087  leave    loc_946D
0x908c  ldarg.0
0x908d  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerAccount Microsoft.Crm.Sandbox.SandboxWorkerNativeProcess::accountDetails
0x9092  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerAccount::get_UserName()
0x9097  ldnull
0x9098  ldarg.0
0x9099  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerAccount Microsoft.Crm.Sandbox.SandboxWorkerNativeProcess::accountDetails
0x909e  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerAccount::get_Password()
0x90a3  ldc.i4.3
0x90a4  ldc.i4.0
0x90a5  ldloca.s 9
0x90a7  call     bool Microsoft.Crm.Sandbox.NativeMethods::LogonUser(string lpszUsername, string lpszDomain, string lpszPassword, int32 dwLogonType, int32 dwLogonProvider, [out] native int& phToken)
0x90ac  brtrue   loc_9136
0x90b1  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x90b6  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x90bb  stloc.s  0xE
0x90bd  ldloc.s  0xE
0x90bf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x90c4  ldc.i4.s 0x21
0x90c6  ldstr    aSandboxworkern_2// "SandboxWorkerNativeProcess.CreateProces"...
0x90cb  ldc.i4.2
0x90cc  newarr   [mscorlib]System.Object
0x90d1  dup
0x90d2  ldc.i4.0
0x90d3  ldarg.0
0x90d4  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerAccount Microsoft.Crm.Sandbox.SandboxWorkerNativeProcess::accountDetails
0x90d9  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerAccount::get_UserName()
0x90de  stelem.ref
0x90df  dup
0x90e0  ldc.i4.1
0x90e1  ldloc.s  0xE
0x90e3  stelem.ref
0x90e4  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x90e9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x90ee  stloc.s  0xF
0x90f0  ldloc.s  0xF
0x90f2  ldstr    aMscrmsandboxse// "MSCRMSandboxService"
0x90f7  ldc.i4.1
0x90f8  ldc.i4   0xC0004F11
0x90fd  conv.u8
0x90fe  ldc.i4.2
0x90ff  newarr   [mscorlib]System.Object
0x9104  dup
0x9105  ldc.i4.0
0x9106  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0x910b  stelem.ref
0x910c  dup
0x910d  ldc.i4.1
0x910e  ldstr    aSandboxworkern_3// "SandboxWorkerNativeProcess.CreateProces"...
0x9113  ldloc.s  0xE
0x9115  call     string [mscorlib]System.String::Format(string, object)
0x911a  stelem.ref
0x911b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x9120  leave.s  loc_912E
0x9122  ldloc.s  0xF
0x9124  brfalse.s loc_912D
0x9126  ldloc.s  0xF
0x9128  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x912d  endfinally
0x912e  ldloc.1
0x912f  stloc.s  0xD
0x9131  leave    loc_946D
0x9136  ldloca.s 0xC
0x9138  initobj  Microsoft.Crm.Sandbox.SECURITY_ATTRIBUTES
0x913e  ldloc.s  9
0x9140  ldc.i4.0
0x9141  ldloca.s 0xC
0x9143  ldc.i4.2
0x9144  ldc.i4.1
0x9145  ldloca.s 0xA
0x9147  call     bool Microsoft.Crm.Sandbox.NativeMethods::DuplicateTokenEx(native int hExistingToken, unsigned int32 dwDesiredAccess, valuetype Microsoft.Crm.Sandbox.SECURITY_ATTRIBUTES& lpTokenAttributes, valuetype Microsoft.Crm.Sandbox.SECURITY_IMPERSONATION_LEVEL ImpersonationLevel, valuetype Microsoft.Crm.Sandbox.TOKEN_TYPE TokenType, [out] native int& phNewToken)
0x914c  brtrue.s loc_91C4
0x914e  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x9153  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x9158  stloc.s  0x10
0x915a  ldnull
0x915b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9160  ldc.i4.s 0x21
0x9162  ldstr    aSandboxworkern_4// "SandboxWorkerNativeProcess.CreateProces"...
0x9167  ldc.i4.1
0x9168  newarr   [mscorlib]System.Object
0x916d  dup
0x916e  ldc.i4.0
0x916f  ldloc.s  0x10
0x9171  stelem.ref
0x9172  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9177  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x917c  stloc.s  0x11
0x917e  ldloc.s  0x11
0x9180  ldstr    aMscrmsandboxse// "MSCRMSandboxService"
0x9185  ldc.i4.1
0x9186  ldc.i4   0xC0004F11
0x918b  conv.u8
0x918c  ldc.i4.2
0x918d  newarr   [mscorlib]System.Object
0x9192  dup
0x9193  ldc.i4.0
0x9194  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0x9199  stelem.ref
0x919a  dup
0x919b  ldc.i4.1
0x919c  ldstr    aSandboxworkern_5// "SandboxWorkerNativeProcess.CreateProces"...
0x91a1  ldloc.s  0x10
0x91a3  call     string [mscorlib]System.String::Format(string, object)
0x91a8  stelem.ref
0x91a9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x91ae  leave.s  loc_91BC
  ... truncated ...
```
