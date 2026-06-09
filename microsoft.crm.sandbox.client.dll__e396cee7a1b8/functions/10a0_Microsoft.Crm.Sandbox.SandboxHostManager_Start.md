# Microsoft.Crm.Sandbox.SandboxHostManager::Start

- ea: `0x10a0`
- end: `0x112b`
- name: `Microsoft.Crm.Sandbox.SandboxHostManager::Start`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0xed0`

## string_xrefs

- `0x10b7`: `_clientConfiguration`
- `0x10f4`: `SandboxHostManager.Start: _pluginTraceLogTimer not null`
- `0x10fe`: `PluginTraceLogTimerIntervalInSeconds`

## pseudocode

```c

```

## disassembly

```asm
0x10a0  ldsfld   class [mscorlib]System.Threading.Timer Microsoft.Crm.Sandbox.SandboxHostManager::_pingTimer
0x10a5  ldnull
0x10a6  ceq
0x10a8  ldstr    aPingtimerNotNu// "_pingTimer not null"
0x10ad  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x10b2  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientConfiguration Microsoft.Crm.Sandbox.SandboxHostManager::_clientConfiguration
0x10b7  ldstr    aClientconfigur// "_clientConfiguration"
0x10bc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x10c1  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientConfiguration Microsoft.Crm.Sandbox.SandboxHostManager::_clientConfiguration
0x10c6  ldc.i4.0
0x10c7  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientProperty)
0x10cc  stloc.0
0x10cd  ldnull
0x10ce  ldftn    void Microsoft.Crm.Sandbox.SandboxHostManager::PingHosts(object stateObject)
0x10d4  newobj   instance void [mscorlib]System.Threading.TimerCallback::.ctor(object, native int)
0x10d9  ldnull
0x10da  ldc.i4.0
0x10db  ldloc.0
0x10dc  ldc.i4   0x3E8
0x10e1  mul
0x10e2  newobj   instance void [mscorlib]System.Threading.Timer::.ctor(class [mscorlib]System.Threading.TimerCallback, object, int32, int32)
0x10e7  stsfld   class [mscorlib]System.Threading.Timer Microsoft.Crm.Sandbox.SandboxHostManager::_pingTimer
0x10ec  ldsfld   class [mscorlib]System.Threading.Timer Microsoft.Crm.Sandbox.SandboxHostManager::_pluginTraceLogTimer
0x10f1  ldnull
0x10f2  ceq
0x10f4  ldstr    aSandboxhostman_29// "SandboxHostManager.Start: _pluginTraceL"...
0x10f9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x10fe  ldstr    aPlugintracelog// "PluginTraceLogTimerIntervalInSeconds"
0x1103  ldc.i4.s 0x1E
0x1105  call     T0x2B000002
0x110a  stloc.1
0x110b  ldnull
0x110c  ldftn    void Microsoft.Crm.Sandbox.SandboxHostManager::WritePluginTraceLog(object stateObject)
0x1112  newobj   instance void [mscorlib]System.Threading.TimerCallback::.ctor(object, native int)
0x1117  ldnull
0x1118  ldc.i4.0
0x1119  ldloc.1
0x111a  ldc.i4   0x3E8
0x111f  mul
0x1120  newobj   instance void [mscorlib]System.Threading.Timer::.ctor(class [mscorlib]System.Threading.TimerCallback, object, int32, int32)
0x1125  stsfld   class [mscorlib]System.Threading.Timer Microsoft.Crm.Sandbox.SandboxHostManager::_pluginTraceLogTimer
0x112a  ret
```
