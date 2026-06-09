# Microsoft.Crm.Sandbox.HostService::SetThreadPoolLimits

- ea: `0x300`
- end: `0x500`
- name: `Microsoft.Crm.Sandbox.HostService::SetThreadPoolLimits`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140`

## callees

- `0x300`

## string_xrefs

- `0x425`: `HostService.SetThreadPoolLimits: Changed MinIOThreads for host from {0} to {1} and MinWorkerThreads from {2} to {3}`
- `0x466`: `HostService.SetThreadPoolLimits: Could not change MinIOThreads/MinWorkerThreads for host`
- `0x4af`: `HostService.SetThreadPoolLimits: Changed MaxIOThreads for host from {0} to {1} and MaxWorkerThreads from {2} to {3}`
- `0x4ef`: `HostService.SetThreadPoolLimits: Could not change MaxIOThreads/MaxWorkerThreads for host.`

## pseudocode

```c

```

## disassembly

```asm
0x300  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x305  ldstr    a01// "{0}{1}"
0x30a  ldc.i4.2
0x30b  newarr   [mscorlib]System.Object
0x310  dup
0x311  ldc.i4.0
0x312  ldc.i4.2
0x313  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x318  stelem.ref
0x319  dup
0x31a  ldc.i4.1
0x31b  ldc.i4.s 0x21
0x31d  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty
0x322  stelem.ref
0x323  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x328  ldc.i4   0x100
0x32d  box      [mscorlib]System.Int32
0x332  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x337  unbox.any [mscorlib]System.Int32
0x33c  stloc.0
0x33d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x342  ldstr    a01// "{0}{1}"
0x347  ldc.i4.2
0x348  newarr   [mscorlib]System.Object
0x34d  dup
0x34e  ldc.i4.0
0x34f  ldc.i4.2
0x350  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x355  stelem.ref
0x356  dup
0x357  ldc.i4.1
0x358  ldc.i4.s 0x22
0x35a  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty
0x35f  stelem.ref
0x360  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x365  ldc.i4.0
0x366  box      [mscorlib]System.Int32
0x36b  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x370  unbox.any [mscorlib]System.Int32
0x375  stloc.1
0x376  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x37b  ldstr    a01// "{0}{1}"
0x380  ldc.i4.2
0x381  newarr   [mscorlib]System.Object
0x386  dup
0x387  ldc.i4.0
0x388  ldc.i4.2
0x389  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x38e  stelem.ref
0x38f  dup
0x390  ldc.i4.1
0x391  ldc.i4.s 0x23
0x393  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty
0x398  stelem.ref
0x399  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x39e  ldc.i4   0xFA0
0x3a3  box      [mscorlib]System.Int32
0x3a8  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x3ad  unbox.any [mscorlib]System.Int32
0x3b2  stloc.2
0x3b3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3b8  ldstr    a01// "{0}{1}"
0x3bd  ldc.i4.2
0x3be  newarr   [mscorlib]System.Object
0x3c3  dup
0x3c4  ldc.i4.0
0x3c5  ldc.i4.2
0x3c6  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x3cb  stelem.ref
0x3cc  dup
0x3cd  ldc.i4.1
0x3ce  ldc.i4.s 0x24
0x3d0  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty
0x3d5  stelem.ref
0x3d6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3db  ldc.i4.0
0x3dc  box      [mscorlib]System.Int32
0x3e1  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x3e6  unbox.any [mscorlib]System.Int32
0x3eb  stloc.3
0x3ec  ldloca.s 4
0x3ee  ldloca.s 5
0x3f0  call     void [mscorlib]System.Threading.ThreadPool::GetMinThreads(int32&, int32&)
0x3f5  ldloc.s  5
0x3f7  stloc.s  6
0x3f9  ldloc.s  4
0x3fb  stloc.s  7
0x3fd  ldloc.0
0x3fe  ldc.i4.0
0x3ff  ble.s    loc_404
0x401  ldloc.0
0x402  stloc.s  6
0x404  ldloc.2
0x405  ldc.i4.0
0x406  ble.s    loc_40B
0x408  ldloc.2
0x409  stloc.s  7
0x40b  ldloc.0
0x40c  ldc.i4.0
0x40d  bgt.s    loc_413
0x40f  ldloc.2
0x410  ldc.i4.0
0x411  ble.s    loc_476
0x413  ldloc.s  7
0x415  ldloc.s  6
0x417  call     bool [mscorlib]System.Threading.ThreadPool::SetMinThreads(int32, int32)
0x41c  brfalse.s loc_45F
0x41e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x423  ldc.i4.s 0x21
0x425  ldstr    aHostserviceSet// "HostService.SetThreadPoolLimits: Change"...
0x42a  ldc.i4.4
0x42b  newarr   [mscorlib]System.Object
0x430  dup
0x431  ldc.i4.0
0x432  ldloc.s  5
0x434  box      [mscorlib]System.Int32
0x439  stelem.ref
0x43a  dup
0x43b  ldc.i4.1
0x43c  ldloc.s  6
0x43e  box      [mscorlib]System.Int32
0x443  stelem.ref
0x444  dup
0x445  ldc.i4.2
0x446  ldloc.s  4
0x448  box      [mscorlib]System.Int32
0x44d  stelem.ref
0x44e  dup
0x44f  ldc.i4.3
0x450  ldloc.s  7
0x452  box      [mscorlib]System.Int32
0x457  stelem.ref
0x458  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x45d  br.s     loc_476
0x45f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x464  ldc.i4.s 0x21
0x466  ldstr    aHostserviceSet_0// "HostService.SetThreadPoolLimits: Could "...
0x46b  ldc.i4.0
0x46c  newarr   [mscorlib]System.Object
0x471  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x476  ldloca.s 8
0x478  ldloca.s 9
0x47a  call     void [mscorlib]System.Threading.ThreadPool::GetMaxThreads(int32&, int32&)
0x47f  ldloc.s  9
0x481  stloc.s  0xA
0x483  ldloc.s  8
0x485  stloc.s  0xB
0x487  ldloc.1
0x488  ldc.i4.0
0x489  ble.s    loc_48E
0x48b  ldloc.1
0x48c  stloc.s  0xA
0x48e  ldloc.3
0x48f  ldc.i4.0
0x490  ble.s    loc_495
0x492  ldloc.3
0x493  stloc.s  0xB
0x495  ldloc.1
0x496  ldc.i4.0
0x497  bgt.s    loc_49D
0x499  ldloc.3
0x49a  ldc.i4.0
0x49b  ble.s    loc_4FF
0x49d  ldloc.s  0xB
0x49f  ldloc.s  0xA
0x4a1  call     bool [mscorlib]System.Threading.ThreadPool::SetMaxThreads(int32, int32)
0x4a6  brfalse.s loc_4E8
0x4a8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4ad  ldc.i4.s 0x21
0x4af  ldstr    aHostserviceSet_1// "HostService.SetThreadPoolLimits: Change"...
0x4b4  ldc.i4.4
0x4b5  newarr   [mscorlib]System.Object
0x4ba  dup
0x4bb  ldc.i4.0
0x4bc  ldloc.s  9
0x4be  box      [mscorlib]System.Int32
0x4c3  stelem.ref
0x4c4  dup
0x4c5  ldc.i4.1
0x4c6  ldloc.s  0xA
0x4c8  box      [mscorlib]System.Int32
0x4cd  stelem.ref
0x4ce  dup
0x4cf  ldc.i4.2
0x4d0  ldloc.s  9
0x4d2  box      [mscorlib]System.Int32
0x4d7  stelem.ref
0x4d8  dup
0x4d9  ldc.i4.3
0x4da  ldloc.s  0xA
0x4dc  box      [mscorlib]System.Int32
0x4e1  stelem.ref
0x4e2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4e7  ret
0x4e8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4ed  ldc.i4.s 0x21
0x4ef  ldstr    aHostserviceSet_2// "HostService.SetThreadPoolLimits: Could "...
0x4f4  ldc.i4.0
0x4f5  newarr   [mscorlib]System.Object
0x4fa  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4ff  ret
```
