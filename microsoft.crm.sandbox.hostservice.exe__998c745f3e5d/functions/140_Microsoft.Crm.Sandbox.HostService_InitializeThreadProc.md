# Microsoft.Crm.Sandbox.HostService::InitializeThreadProc

- ea: `0x140`
- end: `0x2f5`
- name: `Microsoft.Crm.Sandbox.HostService::InitializeThreadProc`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x30`

## callees

- `0x140`
- `0x300`
- `0x520`
- `0x590`
- `0x2d90`
- `0x3030`
- `0x48a0`
- `0x48c0`
- `0x48e0`
- `0x4940`
- `0x51e0`
- `0x5590`
- `0x6350`
- `0xb870`

## string_xrefs

- `0x140`: `HostService.InitializeThreadProc`
- `0x152`: `HostService.InitializeThreadProc: ENTER`
- `0x18c`: `HostService.InitializeThreadProc: Removed temp folder {0}`
- `0x1a9`: `HostService.InitializeThreadProc: Temp folder {0} did not exist, no need to cleanup.`
- `0x1de`: `SYSTEM\CurrentControlSet\Services\{0}`
- `0x1eb`: `MSCRMSandboxService`
- `0x1fd`: `PrivilegeUserGroupId`
- `0x22c`: `SQLAccessGroupId`
- `0x2d8`: `HostService.InitializeThreadProc: EXIT`

## pseudocode

```c

```

## disassembly

```asm
0x140  ldstr    aHostserviceIni// "HostService.InitializeThreadProc"
0x145  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(string)
0x14a  stloc.0
0x14b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x150  ldc.i4.s 0x26
0x152  ldstr    aHostserviceIni_0// "HostService.InitializeThreadProc: ENTER"
0x157  ldc.i4.0
0x158  newarr   [mscorlib]System.Object
0x15d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x162  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0x167  ldc.i4.s 0x1A
0x169  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0x16e  ldc.i4.0
0x16f  ble.s    loc_1BD
0x171  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::BasePackagePath()
0x176  stloc.1
0x177  ldloc.1
0x178  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x17d  brfalse.s loc_1A2
0x17f  ldloc.1
0x180  call     void Microsoft.Crm.Sandbox.Win32FileUtility::DeleteFolder(string basePath)
0x185  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x18a  ldc.i4.s 0x21
0x18c  ldstr    aHostserviceIni_1// "HostService.InitializeThreadProc: Remov"...
0x191  ldc.i4.1
0x192  newarr   [mscorlib]System.Object
0x197  dup
0x198  ldc.i4.0
0x199  ldloc.1
0x19a  stelem.ref
0x19b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a0  br.s     loc_1BD
0x1a2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a7  ldc.i4.s 0x21
0x1a9  ldstr    aHostserviceIni_2// "HostService.InitializeThreadProc: Temp "...
0x1ae  ldc.i4.1
0x1af  newarr   [mscorlib]System.Object
0x1b4  dup
0x1b5  ldc.i4.0
0x1b6  ldloc.1
0x1b7  stelem.ref
0x1b8  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1bd  call     void Microsoft.Crm.Sandbox.HostService::KillRemainingWorkerProcesses()
0x1c2  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x1c7  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x1cc  ldc.i4.1
0x1cd  bne.un.s loc_1D4
0x1cf  call     void Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::RemoveAllExistingAccountsInWorkerGroup()
0x1d4  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x1d9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1de  ldstr    aSystemCurrentc// "SYSTEM\\CurrentControlSet\\Services\\{0"...
0x1e3  ldc.i4.1
0x1e4  newarr   [mscorlib]System.Object
0x1e9  dup
0x1ea  ldc.i4.0
0x1eb  ldstr    aMscrmsandboxse// "MSCRMSandboxService"
0x1f0  stelem.ref
0x1f1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1f6  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x1fb  stloc.2
0x1fc  ldloc.2
0x1fd  ldstr    aPrivilegeuserg// "PrivilegeUserGroupId"
0x202  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x207  stloc.s  5
0x209  ldloca.s 5
0x20b  ldstr    aB// "B"
0x210  call     instance string [mscorlib]System.Guid::ToString(string)
0x215  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x21a  castclass [mscorlib]System.String
0x21f  stloc.3
0x220  ldloc.3
0x221  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x226  call     void Microsoft.Crm.Sandbox.SandboxHost::SetPrivilegeUserGroupId(valuetype [mscorlib]System.Guid privilegeUserGroupId)
0x22b  ldloc.2
0x22c  ldstr    aSqlaccessgroup// "SQLAccessGroupId"
0x231  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x236  stloc.s  5
0x238  ldloca.s 5
0x23a  ldstr    aB// "B"
0x23f  call     instance string [mscorlib]System.Guid::ToString(string)
0x244  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x249  castclass [mscorlib]System.String
0x24e  stloc.s  4
0x250  ldloc.s  4
0x252  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x257  call     void Microsoft.Crm.Sandbox.SandboxHost::SetSqlAccessGroupId(valuetype [mscorlib]System.Guid sqlAccessGroupId)
0x25c  leave.s  loc_268
0x25e  ldloc.2
0x25f  brfalse.s loc_267
0x261  ldloc.2
0x262  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x267  endfinally
0x268  ldc.i4.s 0x16
0x26a  ldc.i4.0
0x26b  call     T0x2B000001
0x270  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceProvider::Initialize()
0x275  call     void Microsoft.Crm.Sandbox.HostService::SetThreadPoolLimits()
0x27a  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceCounter::InitializeCounters()
0x27f  call     void Microsoft.Crm.Sandbox.SandboxAssemblyManager::Start()
0x284  ldc.i4.0
0x285  ble.s    loc_299
0x287  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x28c  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x291  ldc.i4.1
0x292  bne.un.s loc_299
0x294  call     void Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::Start()
0x299  call     void Microsoft.Crm.Sandbox.SandboxCertificateManager::Start()
0x29e  call     void Microsoft.Crm.Sandbox.SandboxHost::StartListening()
0x2a3  call     bool Microsoft.Crm.Sandbox.SandboxWorkerManager::Start()
0x2a8  call     void Microsoft.Crm.Sandbox.HostService::LogErrorIfSandboxWorkerManagerDidNotStart(bool started)
0x2ad  leave.s  loc_2D1
0x2af  stloc.s  6
0x2b1  ldloc.s  6
0x2b3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2b8  ldc.i4.s 0x26
0x2ba  ldstr    a0// "{0}"
0x2bf  ldc.i4.1
0x2c0  newarr   [mscorlib]System.Object
0x2c5  dup
0x2c6  ldc.i4.0
0x2c7  ldloc.s  6
0x2c9  stelem.ref
0x2ca  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2cf  rethrow
0x2d1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2d6  ldc.i4.s 0x26
0x2d8  ldstr    aHostserviceIni_3// "HostService.InitializeThreadProc: EXIT"
0x2dd  ldc.i4.0
0x2de  newarr   [mscorlib]System.Object
0x2e3  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2e8  leave.s  loc_2F4
0x2ea  ldloc.0
0x2eb  brfalse.s loc_2F3
0x2ed  ldloc.0
0x2ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f3  endfinally
0x2f4  ret
```
