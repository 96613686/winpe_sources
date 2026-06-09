# Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::CreateProcess

- ea: `0x5c60`
- end: `0x621f`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::CreateProcess`
- size: `1471`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x48e0`
- `0x5140`
- `0x5150`
- `0x5a60`
- `0x5c60`
- `0x6220`
- `0x6250`
- `0x62a0`
- `0x9720`

## string_xrefs

- `0x5f5e`: `MSCRMSandboxService`
- `0x5cc2`: `AssemblyCache`
- `0x5c67`: `SandboxWorkerDrawbridgeProcess.CreateWorkerProcess`
- `0x5f28`: `SandboxWorkerDrawbridgeProcess.CreateProcess: Unable to create the worker process because the argument length exceeded the maximum length of {0}. Arguments: {1}`
- `0x5fad`: `SandboxWorkerDrawbridgeProcess.CreateProcess: _filePath {0}`
- `0x60d4`: `SandboxWorkerDrawbridgeProcess.CreateProcess: Error launching workerProcess using native method : {0}`
- `0x6153`: `SandboxWorkerDrawbridgeProcess.CreateProcess: failed with Win32Exception: {0}. FilePath:{1} Argument:{2}`
- `0x6188`: `SandboxWorkerDrawbridgeProcess.CreateProcess: failed with ArgumentException: {0}. `
- `0x61b2`: `SandboxWorkerDrawbridgeProcess.CreateProcess: failed with {0}`
- `0x61df`: `SandboxWorkerDrawbridgeProcess.CreateProcess:Thread[{0:d4}]: Spent {1} secs in in CreateWorkerProcess`

## pseudocode

```c

```

## disassembly

```asm
0x5c60  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5c65  ldc.i4.s 0x21
0x5c67  ldstr    aSandboxworkerd_3// "SandboxWorkerDrawbridgeProcess.CreateWo"...
0x5c6c  ldc.i4.0
0x5c6d  newarr   [mscorlib]System.Object
0x5c72  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5c77  ldarg.0
0x5c78  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::WorkerPort
0x5c7d  ldstr    aPort// "port"
0x5c82  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNotPositive(int32, string)
0x5c87  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::BasePackagePath()
0x5c8c  stloc.0
0x5c8d  ldloc.0
0x5c8e  ldarg.0
0x5c8f  call     instance string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::get_WorkerPath()
0x5c94  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5c99  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x5c9e  pop
0x5c9f  ldloc.0
0x5ca0  ldarg.0
0x5ca1  call     instance string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::get_WorkerPath()
0x5ca6  ldstr    aMscrmRo// "MSCRM_RO"
0x5cab  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x5cb0  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x5cb5  pop
0x5cb6  ldloc.0
0x5cb7  ldarg.0
0x5cb8  call     instance string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::get_WorkerPath()
0x5cbd  ldstr    aMscrmRo// "MSCRM_RO"
0x5cc2  ldstr    aAssemblycache// "AssemblyCache"
0x5cc7  call     string [mscorlib]System.IO.Path::Combine(string, string, string, string)
0x5ccc  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x5cd1  pop
0x5cd2  ldloc.0
0x5cd3  ldarg.0
0x5cd4  call     instance string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::get_WorkerPath()
0x5cd9  ldstr    aMscrmRw// "MSCRM_RW"
0x5cde  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x5ce3  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x5ce8  pop
0x5ce9  ldloc.0
0x5cea  ldarg.0
0x5ceb  call     instance string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::get_WorkerPath()
0x5cf0  ldstr    aWpProfile// "wp.profile"
0x5cf5  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x5cfa  stloc.1
0x5cfb  ldarg.0
0x5cfc  call     instance class [System]System.Net.IPAddress Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::GetCurrentIpAddress()
0x5d01  stloc.2
0x5d02  leave.s  loc_5D2C
0x5d04  stloc.s  8
0x5d06  ldloc.s  8
0x5d08  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5d0d  ldc.i4.s 0x21
0x5d0f  ldstr    aGetcurrentipad// "GetCurrentIpAddress() failed with Excep"...
0x5d14  ldc.i4.1
0x5d15  newarr   [mscorlib]System.Object
0x5d1a  dup
0x5d1b  ldc.i4.0
0x5d1c  ldloc.s  8
0x5d1e  stelem.ref
0x5d1f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5d24  ldnull
0x5d25  stloc.s  9
0x5d27  leave    loc_621C
0x5d2c  ldloc.2
0x5d2d  ldstr    aAddress// "address"
0x5d32  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5d37  call     int32 [mscorlib]System.Environment::get_ProcessorCount()
0x5d3c  ldc.i4.0
0x5d3d  bgt.s    loc_5D4D
0x5d3f  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0x5d44  ldc.i4.s 0x10
0x5d46  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0x5d4b  br.s     loc_5D5F
0x5d4d  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0x5d52  ldc.i4.s 0xF
0x5d54  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0x5d59  call     int32 [mscorlib]System.Environment::get_ProcessorCount()
0x5d5e  div
0x5d5f  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0x5d64  ldc.i4.s 0x10
0x5d66  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0x5d6b  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x5d70  stloc.3
0x5d71  ldloc.3
0x5d72  ldc.i4.s 0x64
0x5d74  ble.s    loc_5D79
0x5d76  ldc.i4.s 0x64
0x5d78  stloc.3
0x5d79  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_IsApiOrAsyncAndSandbox()
0x5d7e  brtrue.s loc_5D87
0x5d80  ldsfld   string [mscorlib]System.String::Empty
0x5d85  br.s     loc_5D97
0x5d87  ldstr    aTcpClient0808T// "tcp.client://{0}:808=tcp.client://{0}:8"...
0x5d8c  ldloc.2
0x5d8d  callvirt instance string [mscorlib]System.Object::ToString()
0x5d92  call     string [mscorlib]System.String::Format(string, object)
0x5d97  stloc.s  4
0x5d99  ldloc.1
0x5d9a  ldarg.0
0x5d9b  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::_profileTemplate
0x5da0  ldc.i4.s 0xC
0x5da2  newarr   [mscorlib]System.Object
0x5da7  dup
0x5da8  ldc.i4.0
0x5da9  ldloc.0
0x5daa  stelem.ref
0x5dab  dup
0x5dac  ldc.i4.1
0x5dad  ldarg.0
0x5dae  call     instance string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::get_WorkerPath()
0x5db3  stelem.ref
0x5db4  dup
0x5db5  ldc.i4.2
0x5db6  ldnull
0x5db7  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::SandboxWorkerCertificatePath(string)
0x5dbc  stelem.ref
0x5dbd  dup
0x5dbe  ldc.i4.3
0x5dbf  ldloc.s  4
0x5dc1  stelem.ref
0x5dc2  dup
0x5dc3  ldc.i4.4
0x5dc4  ldloc.2
0x5dc5  callvirt instance string [mscorlib]System.Object::ToString()
0x5dca  stelem.ref
0x5dcb  dup
0x5dcc  ldc.i4.5
0x5dcd  ldarg.0
0x5dce  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::WorkerPort
0x5dd3  box      [mscorlib]System.Int32
0x5dd8  stelem.ref
0x5dd9  dup
0x5dda  ldc.i4.6
0x5ddb  call     string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::GetDynamicEventsRootFolder()
0x5de0  stelem.ref
0x5de1  dup
0x5de2  ldc.i4.7
0x5de3  ldloc.3
0x5de4  box      [mscorlib]System.Int32
0x5de9  stelem.ref
0x5dea  dup
0x5deb  ldc.i4.8
0x5dec  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0x5df1  ldc.i4.s 0xE
0x5df3  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0x5df8  box      [mscorlib]System.Int32
0x5dfd  stelem.ref
0x5dfe  dup
0x5dff  ldc.i4.s 9
0x5e01  ldstr    aMscrmsandboxse_0// "mscrmsandboxsequentialguid"
0x5e06  stelem.ref
0x5e07  dup
0x5e08  ldc.i4.s 0xA
0x5e0a  ldarg.0
0x5e0b  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::WorkerPort
0x5e10  ldc.i4   0x1388
0x5e15  add
0x5e16  box      [mscorlib]System.Int32
0x5e1b  stelem.ref
0x5e1c  dup
0x5e1d  ldc.i4.s 0xB
0x5e1f  ldarg.0
0x5e20  call     instance bool Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::IsSqlPal()
0x5e25  brtrue.s loc_5E2E
0x5e27  ldstr    aS// "S"
0x5e2c  br.s     loc_5E33
0x5e2e  ldstr    aSh// "SH"
0x5e33  stelem.ref
0x5e34  call     string [mscorlib]System.String::Format(string, object[])
0x5e39  call     void [mscorlib]System.IO.File::WriteAllText(string, string)
0x5e3e  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x5e43  stloc.s  5
0x5e45  ldnull
0x5e46  stloc.s  6
0x5e48  ldarg.0
0x5e49  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::_drawbridgeCrashFolder
0x5e4e  brfalse.s loc_5E5D
0x5e50  ldarg.0
0x5e51  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::_drawbridgeCrashFolder
0x5e56  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x5e5b  brtrue.s loc_5EB8
0x5e5d  ldstr    aProfile0123456// "-profile {0} {1} {2} {3} {4} {5} {6}"
0x5e62  ldc.i4.7
0x5e63  newarr   [mscorlib]System.Object
0x5e68  dup
0x5e69  ldc.i4.0
0x5e6a  ldloc.1
0x5e6b  stelem.ref
0x5e6c  dup
0x5e6d  ldc.i4.1
0x5e6e  ldarg.0
0x5e6f  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::_packageName
0x5e74  stelem.ref
0x5e75  dup
0x5e76  ldc.i4.2
0x5e77  ldarg.0
0x5e78  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerId()
0x5e7d  box      [mscorlib]System.Guid
0x5e82  stelem.ref
0x5e83  dup
0x5e84  ldc.i4.3
0x5e85  ldarg.0
0x5e86  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::WorkerPort
0x5e8b  box      [mscorlib]System.Int32
0x5e90  stelem.ref
0x5e91  dup
0x5e92  ldc.i4.4
0x5e93  ldc.i4.1
0x5e94  box      [mscorlib]System.Boolean
0x5e99  stelem.ref
0x5e9a  dup
0x5e9b  ldc.i4.5
0x5e9c  ldsfld   class [mscorlib]System.Lazy`1<string> Microsoft.Crm.Sandbox.SandboxWorkerProcess::SandboxFilesPath
0x5ea1  callvirt instance var<u1> class [mscorlib]System.Lazy`1<string>::get_Value()
0x5ea6  stelem.ref
0x5ea7  dup
0x5ea8  ldc.i4.6
0x5ea9  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_TraceCategories()
0x5eae  stelem.ref
0x5eaf  call     string [mscorlib]System.String::Format(string, object[])
0x5eb4  stloc.s  7
0x5eb6  br.s     loc_5F1A
0x5eb8  ldstr    aCrashdumps7Pro// "-CrashDumps {7} -profile {0} {1} {2} {3"...
0x5ebd  ldc.i4.8
0x5ebe  newarr   [mscorlib]System.Object
0x5ec3  dup
0x5ec4  ldc.i4.0
0x5ec5  ldloc.1
0x5ec6  stelem.ref
0x5ec7  dup
0x5ec8  ldc.i4.1
0x5ec9  ldarg.0
0x5eca  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::_packageName
0x5ecf  stelem.ref
0x5ed0  dup
0x5ed1  ldc.i4.2
0x5ed2  ldarg.0
0x5ed3  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerId()
0x5ed8  box      [mscorlib]System.Guid
0x5edd  stelem.ref
0x5ede  dup
0x5edf  ldc.i4.3
0x5ee0  ldarg.0
0x5ee1  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::WorkerPort
0x5ee6  box      [mscorlib]System.Int32
0x5eeb  stelem.ref
0x5eec  dup
0x5eed  ldc.i4.4
0x5eee  ldc.i4.1
0x5eef  box      [mscorlib]System.Boolean
0x5ef4  stelem.ref
0x5ef5  dup
0x5ef6  ldc.i4.5
0x5ef7  ldsfld   class [mscorlib]System.Lazy`1<string> Microsoft.Crm.Sandbox.SandboxWorkerProcess::SandboxFilesPath
0x5efc  callvirt instance var<u1> class [mscorlib]System.Lazy`1<string>::get_Value()
0x5f01  stelem.ref
0x5f02  dup
0x5f03  ldc.i4.6
0x5f04  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_TraceCategories()
0x5f09  stelem.ref
0x5f0a  dup
0x5f0b  ldc.i4.7
0x5f0c  ldarg.0
0x5f0d  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::_drawbridgeCrashFolder
0x5f12  stelem.ref
0x5f13  call     string [mscorlib]System.String::Format(string, object[])
0x5f18  stloc.s  7
0x5f1a  ldloc.s  7
0x5f1c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5f21  ldc.i4   0x7FE
0x5f26  ble.s    loc_5F92
0x5f28  ldstr    aSandboxworkerd_4// "SandboxWorkerDrawbridgeProcess.CreatePr"...
0x5f2d  ldc.i4   0x7FE
0x5f32  box      [mscorlib]System.Int32
0x5f37  ldloc.s  7
0x5f39  call     string [mscorlib]System.String::Format(string, object, object)
0x5f3e  stloc.s  0xA
0x5f40  ldnull
0x5f41  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5f46  ldc.i4.s 0x26
0x5f48  ldloc.s  0xA
0x5f4a  ldc.i4.0
0x5f4b  newarr   [mscorlib]System.Object
0x5f50  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5f55  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x5f5a  stloc.s  0xB
0x5f5c  ldloc.s  0xB
0x5f5e  ldstr    aMscrmsandboxse// "MSCRMSandboxService"
0x5f63  ldc.i4.1
0x5f64  ldc.i4   0xC0004F11
0x5f69  conv.u8
0x5f6a  ldc.i4.2
0x5f6b  newarr   [mscorlib]System.Object
0x5f70  dup
0x5f71  ldc.i4.0
0x5f72  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0x5f77  stelem.ref
0x5f78  dup
  ... truncated ...
```
