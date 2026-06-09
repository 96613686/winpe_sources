# Microsoft.Crm.Sandbox.OrganizationWorkerList::TryGetEnqueuedWorkerUri

- ea: `0x1cb0`
- end: `0x1f02`
- name: `Microsoft.Crm.Sandbox.OrganizationWorkerList::TryGetEnqueuedWorkerUri`
- size: `594`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x12b0`

## callees

- `0xc70`
- `0x1cb0`
- `0x1f10`

## string_xrefs

- `0x1ced`: `OrganizationWorkerList.TryGetEnqueuedWorkerUri:Thread[{0:d4}] Skipping bucket {1} from a total of {2} buckets. Bucket state is {3}. OrgId: {4}`
- `0x1d54`: `OrganizationWorkerList.TryGetEnqueuedWorkerUri:Thread[{0:d4}] Trying to get a worker from bucket {1} from a total of {2} buckets. Bucket state is {3}. OrgId: {4}`
- `0x1dd0`: `OrganizationWorkerList.TryGetEnqueuedWorkerUriThread[{0:d4}]: Waiting for bucket {1}  from a total of {2} buckets to get a clean worker process. Bucket state is {3}. OrgId: {4}`
- `0x1e37`: `OrganizationWorkerList.TryGetEnqueuedWorkerUri:Thread[{0:d4}] Bucket {1} has {2} threads waiting for clean worker process. Maximum is {3}. Skipping. OrgId: {4}`
- `0x1e96`: `OrganizationWorkerList.TryGetEnqueuedWorkerUri:Thread[{0:d4}] Worker {1} is initializing and cannot wait on it, {2} enqueued, maximum is {3}. OrgId: {4}`

## pseudocode

```c

```

## disassembly

```asm
0x1cb0  ldarg.1
0x1cb1  ldnull
0x1cb2  stind.ref
0x1cb3  ldc.i4.0
0x1cb4  stloc.0
0x1cb5  br       loc_1EEF
0x1cba  ldloc.0
0x1cbb  ldarg.0
0x1cbc  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_nextId
0x1cc1  add
0x1cc2  ldarg.0
0x1cc3  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1cc8  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x1ccd  rem
0x1cce  stloc.1
0x1ccf  ldarg.0
0x1cd0  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1cd5  ldloc.1
0x1cd6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Item(!!T0)
0x1cdb  stloc.2
0x1cdc  ldloc.2
0x1cdd  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x1ce2  ldc.i4.1
0x1ce3  beq.s    loc_1D4C
0x1ce5  ldarg.0
0x1ce6  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1ceb  ldc.i4.s 0x21
0x1ced  ldstr    aOrganizationwo_25// "OrganizationWorkerList.TryGetEnqueuedWo"...
0x1cf2  ldc.i4.5
0x1cf3  newarr   [mscorlib]System.Object
0x1cf8  dup
0x1cf9  ldc.i4.0
0x1cfa  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1cff  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x1d04  box      [mscorlib]System.Int32
0x1d09  stelem.ref
0x1d0a  dup
0x1d0b  ldc.i4.1
0x1d0c  ldloc.1
0x1d0d  box      [mscorlib]System.Int32
0x1d12  stelem.ref
0x1d13  dup
0x1d14  ldc.i4.2
0x1d15  ldarg.0
0x1d16  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1d1b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x1d20  box      [mscorlib]System.Int32
0x1d25  stelem.ref
0x1d26  dup
0x1d27  ldc.i4.3
0x1d28  ldloc.2
0x1d29  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x1d2e  box      Microsoft.Crm.Sandbox.BucketState
0x1d33  stelem.ref
0x1d34  dup
0x1d35  ldc.i4.4
0x1d36  ldarg.0
0x1d37  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1d3c  box      [mscorlib]System.Guid
0x1d41  stelem.ref
0x1d42  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1d47  br       loc_1EEB
0x1d4c  ldarg.0
0x1d4d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1d52  ldc.i4.s 0x21
0x1d54  ldstr    aOrganizationwo_26// "OrganizationWorkerList.TryGetEnqueuedWo"...
0x1d59  ldc.i4.5
0x1d5a  newarr   [mscorlib]System.Object
0x1d5f  dup
0x1d60  ldc.i4.0
0x1d61  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1d66  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x1d6b  box      [mscorlib]System.Int32
0x1d70  stelem.ref
0x1d71  dup
0x1d72  ldc.i4.1
0x1d73  ldloc.1
0x1d74  box      [mscorlib]System.Int32
0x1d79  stelem.ref
0x1d7a  dup
0x1d7b  ldc.i4.2
0x1d7c  ldarg.0
0x1d7d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1d82  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x1d87  box      [mscorlib]System.Int32
0x1d8c  stelem.ref
0x1d8d  dup
0x1d8e  ldc.i4.3
0x1d8f  ldloc.2
0x1d90  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x1d95  box      Microsoft.Crm.Sandbox.BucketState
0x1d9a  stelem.ref
0x1d9b  dup
0x1d9c  ldc.i4.4
0x1d9d  ldarg.0
0x1d9e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1da3  box      [mscorlib]System.Guid
0x1da8  stelem.ref
0x1da9  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1dae  ldloc.2
0x1daf  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerBucket::EnqueuedCount
0x1db4  ldarg.0
0x1db5  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_maxConcurrentRequests
0x1dba  bge.s    loc_1E2F
0x1dbc  ldarg.0
0x1dbd  ldloc.2
0x1dbe  call     instance bool Microsoft.Crm.Sandbox.OrganizationWorkerList::WaitForBucket(class Microsoft.Crm.Sandbox.OrganizationWorkerBucket organizationWorkerBucket)
0x1dc3  brfalse  loc_1E8E
0x1dc8  ldarg.0
0x1dc9  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1dce  ldc.i4.s 0x21
0x1dd0  ldstr    aOrganizationwo_27// "OrganizationWorkerList.TryGetEnqueuedWo"...
0x1dd5  ldc.i4.5
0x1dd6  newarr   [mscorlib]System.Object
0x1ddb  dup
0x1ddc  ldc.i4.0
0x1ddd  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1de2  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x1de7  box      [mscorlib]System.Int32
0x1dec  stelem.ref
0x1ded  dup
0x1dee  ldc.i4.1
0x1def  ldloc.1
0x1df0  box      [mscorlib]System.Int32
0x1df5  stelem.ref
0x1df6  dup
0x1df7  ldc.i4.2
0x1df8  ldarg.0
0x1df9  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1dfe  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x1e03  box      [mscorlib]System.Int32
0x1e08  stelem.ref
0x1e09  dup
0x1e0a  ldc.i4.3
0x1e0b  ldloc.2
0x1e0c  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x1e11  box      Microsoft.Crm.Sandbox.BucketState
0x1e16  stelem.ref
0x1e17  dup
0x1e18  ldc.i4.4
0x1e19  ldarg.0
0x1e1a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1e1f  box      [mscorlib]System.Guid
0x1e24  stelem.ref
0x1e25  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e2a  ldarg.1
0x1e2b  ldloc.2
0x1e2c  stind.ref
0x1e2d  ldc.i4.1
0x1e2e  ret
0x1e2f  ldarg.0
0x1e30  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1e35  ldc.i4.s 0x21
0x1e37  ldstr    aOrganizationwo_28// "OrganizationWorkerList.TryGetEnqueuedWo"...
0x1e3c  ldc.i4.5
0x1e3d  newarr   [mscorlib]System.Object
0x1e42  dup
0x1e43  ldc.i4.0
0x1e44  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1e49  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x1e4e  box      [mscorlib]System.Int32
0x1e53  stelem.ref
0x1e54  dup
0x1e55  ldc.i4.1
0x1e56  ldloc.1
0x1e57  box      [mscorlib]System.Int32
0x1e5c  stelem.ref
0x1e5d  dup
0x1e5e  ldc.i4.2
0x1e5f  ldloc.2
0x1e60  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerBucket::EnqueuedCount
0x1e65  box      [mscorlib]System.Int32
0x1e6a  stelem.ref
0x1e6b  dup
0x1e6c  ldc.i4.3
0x1e6d  ldarg.0
0x1e6e  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_maxConcurrentRequests
0x1e73  box      [mscorlib]System.Int32
0x1e78  stelem.ref
0x1e79  dup
0x1e7a  ldc.i4.4
0x1e7b  ldarg.0
0x1e7c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1e81  box      [mscorlib]System.Guid
0x1e86  stelem.ref
0x1e87  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e8c  br.s     loc_1EEB
0x1e8e  ldarg.0
0x1e8f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1e94  ldc.i4.s 0x21
0x1e96  ldstr    aOrganizationwo_29// "OrganizationWorkerList.TryGetEnqueuedWo"...
0x1e9b  ldc.i4.5
0x1e9c  newarr   [mscorlib]System.Object
0x1ea1  dup
0x1ea2  ldc.i4.0
0x1ea3  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1ea8  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x1ead  box      [mscorlib]System.Int32
0x1eb2  stelem.ref
0x1eb3  dup
0x1eb4  ldc.i4.1
0x1eb5  ldloc.1
0x1eb6  box      [mscorlib]System.Int32
0x1ebb  stelem.ref
0x1ebc  dup
0x1ebd  ldc.i4.2
0x1ebe  ldloc.2
0x1ebf  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerBucket::EnqueuedCount
0x1ec4  box      [mscorlib]System.Int32
0x1ec9  stelem.ref
0x1eca  dup
0x1ecb  ldc.i4.3
0x1ecc  ldarg.0
0x1ecd  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_maxConcurrentRequests
0x1ed2  box      [mscorlib]System.Int32
0x1ed7  stelem.ref
0x1ed8  dup
0x1ed9  ldc.i4.4
0x1eda  ldarg.0
0x1edb  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1ee0  box      [mscorlib]System.Guid
0x1ee5  stelem.ref
0x1ee6  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1eeb  ldloc.0
0x1eec  ldc.i4.1
0x1eed  add
0x1eee  stloc.0
0x1eef  ldloc.0
0x1ef0  ldarg.0
0x1ef1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1ef6  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x1efb  blt      loc_1CBA
0x1f00  ldc.i4.0
0x1f01  ret
```
