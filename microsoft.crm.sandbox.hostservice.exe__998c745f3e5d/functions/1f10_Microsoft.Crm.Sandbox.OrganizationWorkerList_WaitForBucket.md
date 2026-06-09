# Microsoft.Crm.Sandbox.OrganizationWorkerList::WaitForBucket

- ea: `0x1f10`
- end: `0x2039`
- name: `Microsoft.Crm.Sandbox.OrganizationWorkerList::WaitForBucket`
- size: `297`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x12b0`
- `0x1cb0`

## callees

- `0xc70`
- `0xe30`
- `0x1f10`

## string_xrefs

- `0x1f4f`: `OrganizationWorkerList.WaitForBucket:Thread[{0:d4}] Timed out waiting for bucket. Bucket state: {1}. OrgId: {2} `
- `0x1f9c`: `OrganizationWorkerList.WaitForBucket:Thread[{0:d4}] Successfully waited for bucket. Bucket state: {1}. OrgId: {2} `
- `0x1fe8`: `OrganizationWorkerList.WaitForBucket:Thread[{0:d4}] Unhandled exception while waiting. Bucket state: {1}. OrgId: {2} `

## pseudocode

```c

```

## disassembly

```asm
0x1f10  ldarg.0
0x1f11  ldflda   int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_orgWaitingInitializingBucketCount
0x1f16  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x1f1b  pop
0x1f1c  ldarg.1
0x1f1d  callvirt instance class [mscorlib]System.Threading.AutoResetEvent Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_EnqueueSyncronization()
0x1f22  stloc.0
0x1f23  ldarg.1
0x1f24  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x1f29  ldc.i4.1
0x1f2a  beq.s    loc_1F2E
0x1f2c  ldnull
0x1f2d  stloc.0
0x1f2e  ldloc.0
0x1f2f  brfalse  loc_1FDE
0x1f34  ldloc.0
0x1f35  ldarg.0
0x1f36  ldfld    float64 Microsoft.Crm.Sandbox.OrganizationWorkerList::maxWaitTimeInSeconds
0x1f3b  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x1f40  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(valuetype [mscorlib]System.TimeSpan)
0x1f45  brtrue.s loc_1F94
0x1f47  ldarg.0
0x1f48  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1f4d  ldc.i4.s 0x21
0x1f4f  ldstr    aOrganizationwo_30// "OrganizationWorkerList.WaitForBucket:Th"...
0x1f54  ldc.i4.3
0x1f55  newarr   [mscorlib]System.Object
0x1f5a  dup
0x1f5b  ldc.i4.0
0x1f5c  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1f61  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x1f66  box      [mscorlib]System.Int32
0x1f6b  stelem.ref
0x1f6c  dup
0x1f6d  ldc.i4.1
0x1f6e  ldarg.1
0x1f6f  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x1f74  box      Microsoft.Crm.Sandbox.BucketState
0x1f79  stelem.ref
0x1f7a  dup
0x1f7b  ldc.i4.2
0x1f7c  ldarg.0
0x1f7d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1f82  box      [mscorlib]System.Guid
0x1f87  stelem.ref
0x1f88  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1f8d  ldc.i4.0
0x1f8e  stloc.1
0x1f8f  leave    loc_2037
0x1f94  ldarg.0
0x1f95  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1f9a  ldc.i4.s 0x21
0x1f9c  ldstr    aOrganizationwo_31// "OrganizationWorkerList.WaitForBucket:Th"...
0x1fa1  ldc.i4.3
0x1fa2  newarr   [mscorlib]System.Object
0x1fa7  dup
0x1fa8  ldc.i4.0
0x1fa9  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1fae  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x1fb3  box      [mscorlib]System.Int32
0x1fb8  stelem.ref
0x1fb9  dup
0x1fba  ldc.i4.1
0x1fbb  ldarg.1
0x1fbc  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x1fc1  box      Microsoft.Crm.Sandbox.BucketState
0x1fc6  stelem.ref
0x1fc7  dup
0x1fc8  ldc.i4.2
0x1fc9  ldarg.0
0x1fca  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1fcf  box      [mscorlib]System.Guid
0x1fd4  stelem.ref
0x1fd5  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1fda  ldc.i4.1
0x1fdb  stloc.1
0x1fdc  leave.s  loc_2037
0x1fde  leave.s  loc_2035
0x1fe0  ldarg.0
0x1fe1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1fe6  ldc.i4.s 0x21
0x1fe8  ldstr    aOrganizationwo_32// "OrganizationWorkerList.WaitForBucket:Th"...
0x1fed  ldc.i4.3
0x1fee  newarr   [mscorlib]System.Object
0x1ff3  dup
0x1ff4  ldc.i4.0
0x1ff5  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1ffa  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x1fff  box      [mscorlib]System.Int32
0x2004  stelem.ref
0x2005  dup
0x2006  ldc.i4.1
0x2007  ldarg.1
0x2008  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x200d  box      Microsoft.Crm.Sandbox.BucketState
0x2012  stelem.ref
0x2013  dup
0x2014  ldc.i4.2
0x2015  ldarg.0
0x2016  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x201b  box      [mscorlib]System.Guid
0x2020  stelem.ref
0x2021  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2026  leave.s  loc_2035
0x2028  ldarg.0
0x2029  ldflda   int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_orgWaitingInitializingBucketCount
0x202e  call     int32 [mscorlib]System.Threading.Interlocked::Decrement(int32&)
0x2033  pop
0x2034  endfinally
0x2035  ldc.i4.0
0x2036  ret
0x2037  ldloc.1
0x2038  ret
```
