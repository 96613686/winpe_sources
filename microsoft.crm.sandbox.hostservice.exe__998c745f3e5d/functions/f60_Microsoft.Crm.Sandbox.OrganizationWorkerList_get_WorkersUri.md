# Microsoft.Crm.Sandbox.OrganizationWorkerList::get_WorkersUri

- ea: `0xf60`
- end: `0xfdd`
- name: `Microsoft.Crm.Sandbox.OrganizationWorkerList::get_WorkersUri`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x7ae0`

## callees

- `0xc50`
- `0xc70`
- `0xe20`
- `0xf60`
- `0x98f0`

## pseudocode

```c

```

## disassembly

```asm
0xf60  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.Uri>::.ctor()
0xf65  stloc.0
0xf66  ldarg.0
0xf67  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0xf6c  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::GetEnumerator()
0xf71  stloc.1
0xf72  br.s     loc_FBD
0xf74  ldloca.s 1
0xf76  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Current()
0xf7b  stloc.2
0xf7c  ldloc.2
0xf7d  callvirt instance object Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_LockObject()
0xf82  stloc.3
0xf83  ldc.i4.0
0xf84  stloc.s  4
0xf86  ldloc.3
0xf87  ldloca.s 4
0xf89  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xf8e  ldloc.2
0xf8f  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0xf94  ldc.i4.2
0xf95  bne.un.s loc_FB0
0xf97  ldloc.2
0xf98  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerProcess Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_WorkerProcess()
0xf9d  brfalse.s loc_FB0
0xf9f  ldloc.0
0xfa0  ldloc.2
0xfa1  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerProcess Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_WorkerProcess()
0xfa6  callvirt instance class [System]System.Uri Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Uri()
0xfab  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.Uri>::Add(var<u1>)
0xfb0  leave.s  loc_FBD
0xfb2  ldloc.s  4
0xfb4  brfalse.s loc_FBC
0xfb6  ldloc.3
0xfb7  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xfbc  endfinally
0xfbd  ldloca.s 1
0xfbf  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::MoveNext()
0xfc4  brtrue.s loc_F74
0xfc6  leave.s  loc_FD6
0xfc8  ldloca.s 1
0xfca  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>
0xfd0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfd5  endfinally
0xfd6  ldloc.0
0xfd7  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System]System.Uri>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0xfdc  ret
```
