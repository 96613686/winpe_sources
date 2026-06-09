# Microsoft.Crm.Sandbox.SandboxCounter::RemovedFromAssemblyCache

- ea: `0x48f0`
- end: `0x4921`
- name: `Microsoft.Crm.Sandbox.SandboxCounter::RemovedFromAssemblyCache`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x48f0`

## pseudocode

```c

```

## disassembly

```asm
0x48f0  ldarg.0
0x48f1  ldc.i4.0
0x48f2  stfld    bool Microsoft.Crm.Sandbox.SandboxCounter::_inAssemblyCache
0x48f7  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxCounter::_countersLock
0x48fc  ldc.i4.2
0x48fd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x4902  stloc.0
0x4903  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxCounter> Microsoft.Crm.Sandbox.SandboxCounter::_counters
0x4908  ldarg.0
0x4909  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxCounter::_organizationId
0x490e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxCounter>::Remove(var<u1>)
0x4913  pop
0x4914  leave.s  loc_4920
0x4916  ldloc.0
0x4917  brfalse.s loc_491F
0x4919  ldloc.0
0x491a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x491f  endfinally
0x4920  ret
```
