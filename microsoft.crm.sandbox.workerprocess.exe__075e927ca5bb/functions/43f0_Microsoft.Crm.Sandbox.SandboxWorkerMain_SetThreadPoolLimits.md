# Microsoft.Crm.Sandbox.SandboxWorkerMain::SetThreadPoolLimits

- ea: `0x43f0`
- end: `0x45ea`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerMain::SetThreadPoolLimits`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3aa0`

## callees

- `0x43f0`

## string_xrefs

- `0x450f`: `SandboxWorkerMain.SetThreadPoolLimits: Changed MinIOThreads for worker from {0} to {1} and MinWorkerThreads from {2} to {3}`
- `0x4550`: `SandboxWorkerMain.SetThreadPoolLimits: Could not change MinIOThreads/MinWorkerThreads for worker.`
- `0x4599`: `SandboxWorkerMain.SetThreadPoolLimits: Changed MaxIOThreads for worker from {0} to {1} and MaxWorkerThreads from {2} to {3}`
- `0x45d9`: `SandboxWorkerMain.SetThreadPoolLimits: Could not change MaxIOThreads/MaxWorkerThreads for worker.`

## pseudocode

```c

```

## disassembly

```asm
0x43f0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x43f5  ldstr    a01_0// "{0}{1}"
0x43fa  ldc.i4.2
0x43fb  newarr   [mscorlib]System.Object
0x4400  dup
0x4401  ldc.i4.0
0x4402  ldc.i4.3
0x4403  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x4408  stelem.ref
0x4409  dup
0x440a  ldc.i4.1
0x440b  ldc.i4.s 0xA
0x440d  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerProperty
0x4412  stelem.ref
0x4413  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4418  ldc.i4.s 0x65
0x441a  box      [mscorlib]System.Int32
0x441f  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x4424  unbox.any [mscorlib]System.Int32
0x4429  stloc.0
0x442a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x442f  ldstr    a01_0// "{0}{1}"
0x4434  ldc.i4.2
0x4435  newarr   [mscorlib]System.Object
0x443a  dup
0x443b  ldc.i4.0
0x443c  ldc.i4.3
0x443d  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x4442  stelem.ref
0x4443  dup
0x4444  ldc.i4.1
0x4445  ldc.i4.s 0xB
0x4447  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerProperty
0x444c  stelem.ref
0x444d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4452  ldc.i4.0
0x4453  box      [mscorlib]System.Int32
0x4458  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x445d  unbox.any [mscorlib]System.Int32
0x4462  stloc.1
0x4463  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4468  ldstr    a01_0// "{0}{1}"
0x446d  ldc.i4.2
0x446e  newarr   [mscorlib]System.Object
0x4473  dup
0x4474  ldc.i4.0
0x4475  ldc.i4.3
0x4476  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x447b  stelem.ref
0x447c  dup
0x447d  ldc.i4.1
0x447e  ldc.i4.s 0xC
0x4480  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerProperty
0x4485  stelem.ref
0x4486  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x448b  ldc.i4.s 0x65
0x448d  box      [mscorlib]System.Int32
0x4492  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x4497  unbox.any [mscorlib]System.Int32
0x449c  stloc.2
0x449d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x44a2  ldstr    a01_0// "{0}{1}"
0x44a7  ldc.i4.2
0x44a8  newarr   [mscorlib]System.Object
0x44ad  dup
0x44ae  ldc.i4.0
0x44af  ldc.i4.3
0x44b0  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x44b5  stelem.ref
0x44b6  dup
0x44b7  ldc.i4.1
0x44b8  ldc.i4.s 0xD
0x44ba  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerProperty
0x44bf  stelem.ref
0x44c0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x44c5  ldc.i4.0
0x44c6  box      [mscorlib]System.Int32
0x44cb  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x44d0  unbox.any [mscorlib]System.Int32
0x44d5  stloc.3
0x44d6  ldloca.s 4
0x44d8  ldloca.s 5
0x44da  call     void [mscorlib]System.Threading.ThreadPool::GetMinThreads(int32&, int32&)
0x44df  ldloc.s  5
0x44e1  stloc.s  6
0x44e3  ldloc.s  4
0x44e5  stloc.s  7
0x44e7  ldloc.0
0x44e8  ldc.i4.0
0x44e9  ble.s    loc_44EE
0x44eb  ldloc.0
0x44ec  stloc.s  6
0x44ee  ldloc.2
0x44ef  ldc.i4.0
0x44f0  ble.s    loc_44F5
0x44f2  ldloc.2
0x44f3  stloc.s  7
0x44f5  ldloc.0
0x44f6  ldc.i4.0
0x44f7  bgt.s    loc_44FD
0x44f9  ldloc.2
0x44fa  ldc.i4.0
0x44fb  ble.s    loc_4560
0x44fd  ldloc.s  7
0x44ff  ldloc.s  6
0x4501  call     bool [mscorlib]System.Threading.ThreadPool::SetMinThreads(int32, int32)
0x4506  brfalse.s loc_4549
0x4508  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x450d  ldc.i4.s 0x21
0x450f  ldstr    aSandboxworkerm_20// "SandboxWorkerMain.SetThreadPoolLimits: "...
0x4514  ldc.i4.4
0x4515  newarr   [mscorlib]System.Object
0x451a  dup
0x451b  ldc.i4.0
0x451c  ldloc.s  5
0x451e  box      [mscorlib]System.Int32
0x4523  stelem.ref
0x4524  dup
0x4525  ldc.i4.1
0x4526  ldloc.s  6
0x4528  box      [mscorlib]System.Int32
0x452d  stelem.ref
0x452e  dup
0x452f  ldc.i4.2
0x4530  ldloc.s  4
0x4532  box      [mscorlib]System.Int32
0x4537  stelem.ref
0x4538  dup
0x4539  ldc.i4.3
0x453a  ldloc.s  7
0x453c  box      [mscorlib]System.Int32
0x4541  stelem.ref
0x4542  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4547  br.s     loc_4560
0x4549  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x454e  ldc.i4.s 0x21
0x4550  ldstr    aSandboxworkerm_21// "SandboxWorkerMain.SetThreadPoolLimits: "...
0x4555  ldc.i4.0
0x4556  newarr   [mscorlib]System.Object
0x455b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4560  ldloca.s 8
0x4562  ldloca.s 9
0x4564  call     void [mscorlib]System.Threading.ThreadPool::GetMaxThreads(int32&, int32&)
0x4569  ldloc.s  9
0x456b  stloc.s  0xA
0x456d  ldloc.s  8
0x456f  stloc.s  0xB
0x4571  ldloc.1
0x4572  ldc.i4.0
0x4573  ble.s    loc_4578
0x4575  ldloc.1
0x4576  stloc.s  0xA
0x4578  ldloc.3
0x4579  ldc.i4.0
0x457a  ble.s    loc_457F
0x457c  ldloc.3
0x457d  stloc.s  0xB
0x457f  ldloc.1
0x4580  ldc.i4.0
0x4581  bgt.s    loc_4587
0x4583  ldloc.3
0x4584  ldc.i4.0
0x4585  ble.s    loc_45E9
0x4587  ldloc.s  0xB
0x4589  ldloc.s  0xA
0x458b  call     bool [mscorlib]System.Threading.ThreadPool::SetMaxThreads(int32, int32)
0x4590  brfalse.s loc_45D2
0x4592  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4597  ldc.i4.s 0x21
0x4599  ldstr    aSandboxworkerm_22// "SandboxWorkerMain.SetThreadPoolLimits: "...
0x459e  ldc.i4.4
0x459f  newarr   [mscorlib]System.Object
0x45a4  dup
0x45a5  ldc.i4.0
0x45a6  ldloc.s  5
0x45a8  box      [mscorlib]System.Int32
0x45ad  stelem.ref
0x45ae  dup
0x45af  ldc.i4.1
0x45b0  ldloc.s  0xA
0x45b2  box      [mscorlib]System.Int32
0x45b7  stelem.ref
0x45b8  dup
0x45b9  ldc.i4.2
0x45ba  ldloc.s  9
0x45bc  box      [mscorlib]System.Int32
0x45c1  stelem.ref
0x45c2  dup
0x45c3  ldc.i4.3
0x45c4  ldloc.s  0xA
0x45c6  box      [mscorlib]System.Int32
0x45cb  stelem.ref
0x45cc  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x45d1  ret
0x45d2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x45d7  ldc.i4.s 0x21
0x45d9  ldstr    aSandboxworkerm_23// "SandboxWorkerMain.SetThreadPoolLimits: "...
0x45de  ldc.i4.0
0x45df  newarr   [mscorlib]System.Object
0x45e4  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x45e9  ret
```
