# Microsoft.Crm.Sandbox.SandboxHostManager::ProcessBadList

- ea: `0x1700`
- end: `0x178b`
- name: `Microsoft.Crm.Sandbox.SandboxHostManager::ProcessBadList`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x89a0`

## callees

- `0x640`
- `0x1700`

## string_xrefs

- `0x1733`: `SandboxHostManager.ProcessBadList: {0}: removedFromReady: {1}`
- `0x175c`: `SandboxHostManager.ProcessBadList: {0}: removedFromPending: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1700  ldarg.0
0x1701  brfalse  loc_178A
0x1706  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxHostManager::_listsLock
0x170b  ldc.i4.2
0x170c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x1711  stloc.0
0x1712  ldarg.1
0x1713  ldarg.0
0x1714  callvirt instance string Microsoft.Crm.Sandbox.SandboxHostInfo::get_MachineName()
0x1719  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::Remove(var<u1>)
0x171e  stloc.1
0x171f  ldarg.2
0x1720  ldarg.0
0x1721  callvirt instance string Microsoft.Crm.Sandbox.SandboxHostInfo::get_MachineName()
0x1726  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::Remove(var<u1>)
0x172b  stloc.2
0x172c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1731  ldc.i4.s 0x23
0x1733  ldstr    aSandboxhostman_38// "SandboxHostManager.ProcessBadList: {0}:"...
0x1738  ldc.i4.2
0x1739  newarr   [mscorlib]System.Object
0x173e  dup
0x173f  ldc.i4.0
0x1740  ldarg.0
0x1741  callvirt instance string Microsoft.Crm.Sandbox.SandboxHostInfo::get_MachineName()
0x1746  stelem.ref
0x1747  dup
0x1748  ldc.i4.1
0x1749  ldloc.1
0x174a  box      [mscorlib]System.Boolean
0x174f  stelem.ref
0x1750  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1755  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x175a  ldc.i4.s 0x23
0x175c  ldstr    aSandboxhostman_39// "SandboxHostManager.ProcessBadList: {0}:"...
0x1761  ldc.i4.2
0x1762  newarr   [mscorlib]System.Object
0x1767  dup
0x1768  ldc.i4.0
0x1769  ldarg.0
0x176a  callvirt instance string Microsoft.Crm.Sandbox.SandboxHostInfo::get_MachineName()
0x176f  stelem.ref
0x1770  dup
0x1771  ldc.i4.1
0x1772  ldloc.2
0x1773  box      [mscorlib]System.Boolean
0x1778  stelem.ref
0x1779  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x177e  leave.s  loc_178A
0x1780  ldloc.0
0x1781  brfalse.s loc_1789
0x1783  ldloc.0
0x1784  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1789  endfinally
0x178a  ret
```
