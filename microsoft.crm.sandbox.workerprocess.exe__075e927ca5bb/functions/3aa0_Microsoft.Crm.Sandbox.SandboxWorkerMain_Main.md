# Microsoft.Crm.Sandbox.SandboxWorkerMain::Main

- ea: `0x3aa0`
- end: `0x3e8c`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerMain::Main`
- size: `1004`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1a30`
- `0x28b0`
- `0x3820`
- `0x3aa0`
- `0x3e90`
- `0x3ea0`
- `0x3f90`
- `0x4350`
- `0x43f0`
- `0x4750`
- `0x4810`
- `0x4830`

## string_xrefs

- `0x3c54`: `SandboxWorkerMain.Main: Incorrect argument format for insideDrawBridge (argument #4): {0}`
- `0x3d69`: `Temp Listener`

## pseudocode

```c

```

## disassembly

```asm
0x3aa0  .entrypoint
0x3aa5  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x3aaa  ldc.i4.2
0x3aab  ceq
0x3aad  ldstr    aMdaaccount// "mdaAccount"
0x3ab2  ldstr    aMetricsnamespa// "metricsNamespace"
0x3ab7  newobj   instance void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryModule::.ctor(bool, string, string)
0x3abc  pop
0x3abd  call     void Microsoft.Crm.Sandbox.SandboxWorkerMain::InitializeDefaultValues()
0x3ac2  ldarg.0
0x3ac3  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerMain::InitializeTrace(string[] arguments)
0x3ac8  pop
0x3ac9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3ace  ldc.i4.s 0x21
0x3ad0  ldstr    aSandboxWorkerP// "Sandbox Worker: process START: "
0x3ad5  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessId()
0x3ada  call     string [mscorlib]System.String::Concat(string, string)
0x3adf  ldc.i4.0
0x3ae0  newarr   [mscorlib]System.Object
0x3ae5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3aea  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x3aef  ldnull
0x3af0  ldftn    void Microsoft.Crm.Sandbox.SandboxWorkerMain::UnhandledExceptionHandler(object sender, class [mscorlib]System.UnhandledExceptionEventArgs e)
0x3af6  newobj   instance void [mscorlib]System.UnhandledExceptionEventHandler::.ctor(object, native int)
0x3afb  callvirt instance void [mscorlib]System.AppDomain::add_UnhandledException(class [mscorlib]System.UnhandledExceptionEventHandler)
0x3b00  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x3b05  ldnull
0x3b06  ldftn    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxWorkerMain::AssemblyRedirects(object sender, class [mscorlib]System.ResolveEventArgs e)
0x3b0c  newobj   instance void [mscorlib]System.ResolveEventHandler::.ctor(object, native int)
0x3b11  callvirt instance void [mscorlib]System.AppDomain::add_AssemblyResolve(class [mscorlib]System.ResolveEventHandler)
0x3b16  ldnull
0x3b17  stloc.0
0x3b18  ldnull
0x3b19  stloc.1
0x3b1a  ldarg.0
0x3b1b  ldlen
0x3b1c  conv.i4
0x3b1d  ldc.i4.5
0x3b1e  beq.s    loc_3B62
0x3b20  ldnull
0x3b21  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3b26  ldc.i4.s 0x26
0x3b28  ldstr    aSandboxworkerm_1// "SandboxWorkerMain.Main: Incorrect numbe"...
0x3b2d  ldc.i4.1
0x3b2e  newarr   [mscorlib]System.Object
0x3b33  dup
0x3b34  ldc.i4.0
0x3b35  ldarg.0
0x3b36  ldlen
0x3b37  conv.i4
0x3b38  box      [mscorlib]System.Int32
0x3b3d  stelem.ref
0x3b3e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3b43  ldc.i4.1
0x3b44  ldarg.0
0x3b45  ldlen
0x3b46  conv.i4
0x3b47  stloc.s  0xA
0x3b49  ldloca.s 0xA
0x3b4b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3b50  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x3b55  ldnull
0x3b56  call     int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::LogExit(valuetype SandboxExitCode exitCode, string parameter1, string parameter2)
0x3b5b  stloc.s  0xA
0x3b5d  leave    loc_3E89
0x3b62  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3b67  ldc.i4.s 0x26
0x3b69  ldstr    aSandboxworkerm_2// "SandboxWorkerMain.Main: 1: worker guid:"...
0x3b6e  ldc.i4.1
0x3b6f  newarr   [mscorlib]System.Object
0x3b74  dup
0x3b75  ldc.i4.0
0x3b76  ldarg.0
0x3b77  ldc.i4.0
0x3b78  ldelem.ref
0x3b79  stelem.ref
0x3b7a  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3b7f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3b84  ldc.i4.s 0x26
0x3b86  ldstr    aSandboxworkerm_3// "SandboxWorkerMain.Main: 2: worker port:"...
0x3b8b  ldc.i4.1
0x3b8c  newarr   [mscorlib]System.Object
0x3b91  dup
0x3b92  ldc.i4.0
0x3b93  ldarg.0
0x3b94  ldc.i4.1
0x3b95  ldelem.ref
0x3b96  stelem.ref
0x3b97  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3b9c  ldarg.0
0x3b9d  ldc.i4.0
0x3b9e  ldelem.ref
0x3b9f  stloc.2
0x3ba0  ldarg.0
0x3ba1  ldc.i4.1
0x3ba2  ldelem.ref
0x3ba3  stloc.3
0x3ba4  ldarg.0
0x3ba5  ldc.i4.2
0x3ba6  ldelem.ref
0x3ba7  stloc.s  4
0x3ba9  ldarg.0
0x3baa  ldc.i4.3
0x3bab  ldelem.ref
0x3bac  stsfld   string Microsoft.Crm.Sandbox.SandboxWorkerMain::_sandboxFilesPath
0x3bb1  ldloc.2
0x3bb2  ldloca.s 5
0x3bb4  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x3bb9  brtrue.s loc_3BEC
0x3bbb  ldnull
0x3bbc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3bc1  ldc.i4.s 0x26
0x3bc3  ldstr    aSandboxworkerm_4// "SandboxWorkerMain.Main: Worker process "...
0x3bc8  ldc.i4.1
0x3bc9  newarr   [mscorlib]System.Object
0x3bce  dup
0x3bcf  ldc.i4.0
0x3bd0  ldloc.2
0x3bd1  stelem.ref
0x3bd2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3bd7  ldc.i4.6
0x3bd8  ldarg.0
0x3bd9  ldc.i4.1
0x3bda  ldelem.ref
0x3bdb  ldstr    aInvalidFormatF// "Invalid format for Guid"
0x3be0  call     int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::LogExit(valuetype SandboxExitCode exitCode, string parameter1, string parameter2)
0x3be5  stloc.s  0xA
0x3be7  leave    loc_3E89
0x3bec  ldloc.s  5
0x3bee  call     void Microsoft.Crm.Sandbox.SandboxWorkerMain::set_WorkerProcessGuid(valuetype [mscorlib]System.Guid value)
0x3bf3  ldloc.3
0x3bf4  ldsflda  int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::_workerProcessPort
0x3bf9  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x3bfe  brtrue.s loc_3C3A
0x3c00  ldnull
0x3c01  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3c06  ldc.i4.s 0x26
0x3c08  ldstr    aSandboxworkerm_5// "SandboxWorkerMain.Main: Incorrect argum"...
0x3c0d  ldc.i4.1
0x3c0e  newarr   [mscorlib]System.Object
0x3c13  dup
0x3c14  ldc.i4.0
0x3c15  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::_workerProcessPort
0x3c1a  box      [mscorlib]System.Int32
0x3c1f  stelem.ref
0x3c20  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3c25  ldc.i4.2
0x3c26  ldarg.0
0x3c27  ldc.i4.2
0x3c28  ldelem.ref
0x3c29  ldstr    aInvalidFormatF_0// "Invalid format for port number"
0x3c2e  call     int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::LogExit(valuetype SandboxExitCode exitCode, string parameter1, string parameter2)
0x3c33  stloc.s  0xA
0x3c35  leave    loc_3E89
0x3c3a  ldc.i4.0
0x3c3b  stloc.s  6
0x3c3d  ldloc.s  4
0x3c3f  brfalse.s loc_3C7E
0x3c41  ldloc.s  4
0x3c43  ldloca.s 6
0x3c45  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x3c4a  brtrue.s loc_3C7E
0x3c4c  ldnull
0x3c4d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3c52  ldc.i4.s 0x26
0x3c54  ldstr    aSandboxworkerm_6// "SandboxWorkerMain.Main: Incorrect argum"...
0x3c59  ldc.i4.1
0x3c5a  newarr   [mscorlib]System.Object
0x3c5f  dup
0x3c60  ldc.i4.0
0x3c61  ldloc.s  4
0x3c63  stelem.ref
0x3c64  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3c69  ldc.i4.2
0x3c6a  ldarg.0
0x3c6b  ldc.i4.2
0x3c6c  ldelem.ref
0x3c6d  ldstr    aInvalidFormatF_0// "Invalid format for port number"
0x3c72  call     int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::LogExit(valuetype SandboxExitCode exitCode, string parameter1, string parameter2)
0x3c77  stloc.s  0xA
0x3c79  leave    loc_3E89
0x3c7e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceProvider::Initialize()
0x3c83  call     void Microsoft.Crm.Sandbox.SandboxWorkerMain::SetThreadPoolLimits()
0x3c88  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c8d  ldstr    a01_0// "{0}{1}"
0x3c92  ldc.i4.2
0x3c93  newarr   [mscorlib]System.Object
0x3c98  dup
0x3c99  ldc.i4.0
0x3c9a  ldc.i4.3
0x3c9b  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x3ca0  stelem.ref
0x3ca1  dup
0x3ca2  ldc.i4.1
0x3ca3  ldstr    aStartlistenerb// "StartListenerBeforeWarmup"
0x3ca8  stelem.ref
0x3ca9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3cae  ldc.i4.0
0x3caf  box      [mscorlib]System.Int32
0x3cb4  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x3cb9  unbox.any [mscorlib]System.Int32
0x3cbe  ldc.i4.0
0x3cbf  cgt
0x3cc1  stloc.s  7
0x3cc3  ldloc.s  7
0x3cc5  brfalse.s loc_3D2E
0x3cc7  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::_workerProcessPort
0x3ccc  ldloc.s  6
0x3cce  call     void Microsoft.Crm.Sandbox.SandboxWorker::StartListening(int32 port, bool usingDrawbridge)
0x3cd3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3cd8  ldc.i4.s 0x26
0x3cda  ldstr    aSandboxworkerm_7// "SandboxWorkerMain.Main: Sandbox Worker:"...
0x3cdf  ldc.i4.0
0x3ce0  newarr   [mscorlib]System.Object
0x3ce5  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3cea  leave.s  loc_3D29
0x3cec  stloc.s  0xB
0x3cee  ldloc.s  0xB
0x3cf0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3cf5  ldc.i4.s 0x26
0x3cf7  ldloc.s  0xB
0x3cf9  callvirt instance string [mscorlib]System.Object::ToString()
0x3cfe  ldc.i4.0
0x3cff  newarr   [mscorlib]System.Object
0x3d04  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3d09  ldc.i4.4
0x3d0a  ldloc.s  0xB
0x3d0c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x3d11  callvirt instance string [mscorlib]System.Object::ToString()
0x3d16  ldloc.s  0xB
0x3d18  callvirt instance string [mscorlib]System.Object::ToString()
0x3d1d  call     int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::LogExit(valuetype SandboxExitCode exitCode, string parameter1, string parameter2)
0x3d22  stloc.s  0xA
0x3d24  leave    loc_3E89
0x3d29  call     void Microsoft.Crm.Sandbox.SandboxOrganizationService::Start()
0x3d2e  newobj   instance void [System]System.UriBuilder::.ctor()
0x3d33  stloc.s  8
0x3d35  ldloc.s  8
0x3d37  call     int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::get_Port()
0x3d3c  ldc.i4   0x1388
0x3d41  add
0x3d42  callvirt instance void [System]System.UriBuilder::set_Port(int32)
0x3d47  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxListener class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxListener`2<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener, class Microsoft.Crm.Sandbox.WarmUpMockListener>::NewListener()
0x3d4c  isinst   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxListener`2<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener, class Microsoft.Crm.Sandbox.WarmUpMockListener>
0x3d51  dup
0x3d52  stloc.s  9
0x3d54  stloc.s  0xC
0x3d56  ldloc.s  9
0x3d58  ldloc.s  8
0x3d5a  ldc.i4.0
0x3d5b  ldnull
0x3d5c  ldc.i4.5
0x3d5d  ldc.i4   0x40004F01
0x3d62  conv.i8
0x3d63  ldc.i4   0xC0004F11
0x3d68  conv.u8
0x3d69  ldstr    aTempListener// "Temp Listener"
0x3d6e  callvirt instance void class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxListener`2<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener, class Microsoft.Crm.Sandbox.WarmUpMockListener>::StartListening(class [System]System.UriBuilder, valuetype [System.ServiceModel]System.ServiceModel.TcpClientCredentialType, class [System.ServiceModel]System.ServiceModel.Description.ServiceCredentials, valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix, int64, int64, string)
0x3d73  call     void Microsoft.Crm.Sandbox.SandboxAppDomainManager::RecycleAppDomain()
0x3d78  leave.s  loc_3DA1
0x3d7a  stloc.s  0xD
0x3d7c  ldloc.s  0xD
0x3d7e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3d83  ldc.i4.s 0x26
0x3d85  ldstr    aUnhandledExcep// "Unhandled exception on warmup: {0}"
0x3d8a  ldc.i4.1
0x3d8b  newarr   [mscorlib]System.Object
0x3d90  dup
0x3d91  ldc.i4.0
0x3d92  ldloc.s  0xD
0x3d94  callvirt instance string [mscorlib]System.Object::ToString()
0x3d99  stelem.ref
0x3d9a  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3d9f  leave.s  loc_3DA1
0x3da1  ldloc.s  7
0x3da3  brtrue.s loc_3E0C
0x3da5  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::_workerProcessPort
0x3daa  ldloc.s  6
0x3dac  call     void Microsoft.Crm.Sandbox.SandboxWorker::StartListening(int32 port, bool usingDrawbridge)
0x3db1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3db6  ldc.i4.s 0x26
0x3db8  ldstr    aSandboxworkerm_7// "SandboxWorkerMain.Main: Sandbox Worker:"...
0x3dbd  ldc.i4.0
0x3dbe  newarr   [mscorlib]System.Object
0x3dc3  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3dc8  leave.s  loc_3E07
0x3dca  stloc.s  0xE
0x3dcc  ldloc.s  0xE
0x3dce  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3dd3  ldc.i4.s 0x26
0x3dd5  ldloc.s  0xE
0x3dd7  callvirt instance string [mscorlib]System.Object::ToString()
0x3ddc  ldc.i4.0
0x3ddd  newarr   [mscorlib]System.Object
0x3de2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3de7  ldc.i4.4
0x3de8  ldloc.s  0xE
0x3dea  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x3def  callvirt instance string [mscorlib]System.Object::ToString()
0x3df4  ldloc.s  0xE
  ... truncated ...
```
