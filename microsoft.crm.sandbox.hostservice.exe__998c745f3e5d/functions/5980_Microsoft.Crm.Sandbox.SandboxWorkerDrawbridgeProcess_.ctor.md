# Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::.ctor

- ea: `0x5980`
- end: `0x5a52`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::.ctor`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7e30`

## callees

- `0x5980`
- `0x9640`

## string_xrefs

- `0x5997`: `\n[Profile]\nProfileVersion=2\n\n[FileSystem.ReadOnly]\n\MSCRM_RO={0}\{1}\MSCRM_RO\n\MSCRM_CERT={2}\n\n[Windows.Startup]\nScratchDir={0}\{1}\ScratchDir\n\n[FileSystem.Writable]\n\CrmTrace={6}\n\={0}\{1}\MSCRM_RW\n\n[Resources.Writable]\ntcp.client://127.0.0.1:{10}=tcp.client://127.0.0.1:{10}\ntcp.client://127.0.0.1:=NOWHERE:\ntcp.client://169.254.169.254:=NOWHERE:\ntcp.client://168.63.129.16:=NOWHERE:\n{3}\ntcp.client://{4}:=NOWHERE:\ntcp.client:=tcp.client:\ntcp.server://`
- `0x5a06`: `Drawbridge is not installed on the server.`

## pseudocode

```c

```

## disassembly

```asm
0x5980  ldarg.0
0x5981  ldstr    aSoftwareMicros// "Software\\Microsoft\\Drawbridge"
0x5986  stfld    string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::_drawBridgeKeyPath
0x598b  ldarg.0
0x598c  ldstr    aCrmsandbox// "crmsandbox"
0x5991  stfld    string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::_packageName
0x5996  ldarg.0
0x5997  ldstr    aProfileProfile// "\r\n[Profile]\r\nProfileVersion=2\r\n\r"...
0x599c  stfld    string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::_profileTemplate
0x59a1  ldarg.0
0x59a2  ldarg.1
0x59a3  ldarg.2
0x59a4  call     instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::.ctor(int32 port, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<int32> portsQueue)
0x59a9  ldsfld   string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::_filePath
0x59ae  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x59b3  brfalse.s loc_5A11
0x59b5  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x59ba  ldarg.0
0x59bb  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::_drawBridgeKeyPath
0x59c0  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x59c5  stloc.0
0x59c6  ldloc.0
0x59c7  brfalse.s loc_5A06
0x59c9  ldloc.0
0x59ca  ldstr    aMonitorcore// "MonitorCore"
0x59cf  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x59d4  castclass [mscorlib]System.String
0x59d9  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x59de  brtrue.s loc_5A06
0x59e0  ldloc.0
0x59e1  ldstr    aMonitorcore// "MonitorCore"
0x59e6  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x59eb  castclass [mscorlib]System.String
0x59f0  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x59f5  ldstr    aDkmonExe// "DkMon.exe"
0x59fa  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x59ff  stsfld   string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::_filePath
0x5a04  br.s     loc_5A11
0x5a06  ldstr    aDrawbridgeIsNo// "Drawbridge is not installed on the serv"...
0x5a0b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x5a10  throw
0x5a11  ldarg.0
0x5a12  ldc.i4.1
0x5a13  stfld    bool Microsoft.Crm.Sandbox.SandboxWorkerProcess::IsDrawbridgeProcess
0x5a18  ldarg.0
0x5a19  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5a1e  ldstr    a01// "{0}{1}"
0x5a23  ldc.i4.2
0x5a24  newarr   [mscorlib]System.Object
0x5a29  dup
0x5a2a  ldc.i4.0
0x5a2b  ldc.i4.2
0x5a2c  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x5a31  stelem.ref
0x5a32  dup
0x5a33  ldc.i4.1
0x5a34  ldc.i4.s 0x20
0x5a36  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxProperty
0x5a3b  stelem.ref
0x5a3c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5a41  ldnull
0x5a42  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x5a47  castclass [mscorlib]System.String
0x5a4c  stfld    string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::_drawbridgeCrashFolder
0x5a51  ret
```
