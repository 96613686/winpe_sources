# Microsoft.Crm.Sandbox.SandboxAssemblyManager::UpdateTimer

- ea: `0x3210`
- end: `0x32ca`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyManager::UpdateTimer`
- size: `186`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3030`
- `0x3e00`

## callees

- `0x3210`
- `0x48e0`

## string_xrefs

- `0x3229`: `SandboxAssemblyManager.UpdateTimer: AssemblyCacheMonitorIntervalInMin invalid, using default: {0}`
- `0x3272`: `SandboxAssemblyManager.UpdateTimer: timer create: interval (mins): {0}`
- `0x32aa`: `SandboxAssemblyManager.UpdateTimer: timer change: interval (mins): {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3210  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0x3215  ldc.i4.s 9
0x3217  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0x321c  stloc.0
0x321d  ldloc.0
0x321e  ldc.i4.0
0x321f  bgt.s    loc_3245
0x3221  ldnull
0x3222  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3227  ldc.i4.s 0x22
0x3229  ldstr    aSandboxassembl_37// "SandboxAssemblyManager.UpdateTimer: Ass"...
0x322e  ldc.i4.1
0x322f  newarr   [mscorlib]System.Object
0x3234  dup
0x3235  ldc.i4.0
0x3236  ldloc.0
0x3237  box      [mscorlib]System.Int32
0x323c  stelem.ref
0x323d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3242  ldc.i4.s 0x3C
0x3244  stloc.0
0x3245  ldloc.0
0x3246  ldc.i4.s 0x3C
0x3248  mul
0x3249  ldc.i4   0x3E8
0x324e  mul
0x324f  conv.i8
0x3250  stloc.1
0x3251  ldsfld   class [mscorlib]System.Threading.Timer Microsoft.Crm.Sandbox.SandboxAssemblyManager::_monitorTimer
0x3256  brtrue.s loc_328D
0x3258  ldsfld   class [mscorlib]System.Threading.TimerCallback Microsoft.Crm.Sandbox.SandboxAssemblyManager::timerDelegate
0x325d  ldnull
0x325e  ldc.i4.0
0x325f  conv.i8
0x3260  ldloc.1
0x3261  newobj   instance void [mscorlib]System.Threading.Timer::.ctor(class [mscorlib]System.Threading.TimerCallback, object, int64, int64)
0x3266  stsfld   class [mscorlib]System.Threading.Timer Microsoft.Crm.Sandbox.SandboxAssemblyManager::_monitorTimer
0x326b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3270  ldc.i4.s 0x22
0x3272  ldstr    aSandboxassembl_38// "SandboxAssemblyManager.UpdateTimer: tim"...
0x3277  ldc.i4.1
0x3278  newarr   [mscorlib]System.Object
0x327d  dup
0x327e  ldc.i4.0
0x327f  ldloc.0
0x3280  box      [mscorlib]System.Int32
0x3285  stelem.ref
0x3286  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x328b  br.s     loc_32C3
0x328d  ldloc.0
0x328e  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxAssemblyManager::_assemblyCacheMonitorIntervalInMin
0x3293  beq.s    loc_32C3
0x3295  ldsfld   class [mscorlib]System.Threading.Timer Microsoft.Crm.Sandbox.SandboxAssemblyManager::_monitorTimer
0x329a  ldc.i4.0
0x329b  conv.i8
0x329c  ldloc.1
0x329d  callvirt instance bool [mscorlib]System.Threading.Timer::Change(int64, int64)
0x32a2  pop
0x32a3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x32a8  ldc.i4.s 0x22
0x32aa  ldstr    aSandboxassembl_39// "SandboxAssemblyManager.UpdateTimer: tim"...
0x32af  ldc.i4.1
0x32b0  newarr   [mscorlib]System.Object
0x32b5  dup
0x32b6  ldc.i4.0
0x32b7  ldloc.0
0x32b8  box      [mscorlib]System.Int32
0x32bd  stelem.ref
0x32be  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x32c3  ldloc.0
0x32c4  stsfld   int32 Microsoft.Crm.Sandbox.SandboxAssemblyManager::_assemblyCacheMonitorIntervalInMin
0x32c9  ret
```
