# Microsoft.Crm.Sandbox.OrganizationWorkerList::TryToEnqueueWorkerUri

- ea: `0x1870`
- end: `0x1ca9`
- name: `Microsoft.Crm.Sandbox.OrganizationWorkerList::TryToEnqueueWorkerUri`
- size: `1081`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x12b0`

## callees

- `0xc60`
- `0xc70`
- `0xc80`
- `0xe20`
- `0xe30`
- `0xe70`
- `0x1870`
- `0x9740`
- `0x97b0`

## string_xrefs

- `0x187b`: `OrganizationWorkerList.TryToEnqueueWorkerUri:Thread[{0:d4}] Initializing for org {1}`
- `0x18e4`: `OrganizationWorkerList.TryToEnqueueWorkerUri:Thread[{0:d4}] Skipping bucket {1} from a total of {2} buckets. Bucket state is {3}. OrgId: {4}`
- `0x1965`: `OrganizationWorkerList.TryToEnqueueWorkerUri:Thread[{0:d4}] LOCKED - Skipping bucket {1} from a total of {2} buckets. Bucket state is {3}. OrgId: {4}`
- `0x19d3`: `OrganizationWorkerList.TryToEnqueueWorkerUri:Thread[{0:d4}] Trying to initialize a clean worker process for bucket {1} from a total of {2} buckets. Bucket state is {3}. OrgId: {4}`
- `0x1a44`: `OrganizationWorkerList.TryToEnqueueWorkerUri:Thread[{0:d4}] No clean worker process found for bucket {1} of {2} buckets. Bucket state is {3}. Starting a new background thread. OrgId: {4}`
- `0x1abc`: `OrganizationWorkerList.TryToEnqueueWorkerUri:Thread[{0:d4}] No clean worker process found for bucket {1} of {2} buckets. Bucket state is {3}. Reseting state of bucket. OrgId: {4}`
- `0x1b66`: `OrganizationWorkerList.TryToEnqueueWorkerUri:Thread[{0:d4}] Worker process found for bucket {1} of {2} buckets. Bucket state is {3}. Worker Url {4}. OrgId: {4}`
- `0x1be5`: `OrganizationWorkerList.TryToEnqueueWorkerUri:Thread[{0:d4}] Unhandled exception for bucket {1} from a total of {2} buckets. Bucket state is {3}. OrgId: {4}. Exception {5}`
- `0x1c86`: `OrganizationWorkerList.TryToEnqueueWorkerUri:Thread[{0:d4}] Could not enqueue any clean worker process. Exiting false. OrgId: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1870  ldarg.3
0x1871  ldnull
0x1872  stind.ref
0x1873  ldarg.0
0x1874  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1879  ldc.i4.s 0x21
0x187b  ldstr    aOrganizationwo_16// "OrganizationWorkerList.TryToEnqueueWork"...
0x1880  ldc.i4.2
0x1881  newarr   [mscorlib]System.Object
0x1886  dup
0x1887  ldc.i4.0
0x1888  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x188d  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x1892  box      [mscorlib]System.Int32
0x1897  stelem.ref
0x1898  dup
0x1899  ldc.i4.1
0x189a  ldarg.0
0x189b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x18a0  box      [mscorlib]System.Guid
0x18a5  stelem.ref
0x18a6  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18ab  ldc.i4.0
0x18ac  stloc.0
0x18ad  br       loc_1C6C
0x18b2  ldloc.0
0x18b3  ldarg.0
0x18b4  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_nextId
0x18b9  add
0x18ba  ldarg.0
0x18bb  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x18c0  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x18c5  rem
0x18c6  stloc.1
0x18c7  ldarg.0
0x18c8  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x18cd  ldloc.1
0x18ce  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Item(!!T0)
0x18d3  stloc.2
0x18d4  ldloc.2
0x18d5  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x18da  brfalse.s loc_1943
0x18dc  ldarg.0
0x18dd  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x18e2  ldc.i4.s 0x21
0x18e4  ldstr    aOrganizationwo_17// "OrganizationWorkerList.TryToEnqueueWork"...
0x18e9  ldc.i4.5
0x18ea  newarr   [mscorlib]System.Object
0x18ef  dup
0x18f0  ldc.i4.0
0x18f1  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x18f6  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x18fb  box      [mscorlib]System.Int32
0x1900  stelem.ref
0x1901  dup
0x1902  ldc.i4.1
0x1903  ldloc.1
0x1904  box      [mscorlib]System.Int32
0x1909  stelem.ref
0x190a  dup
0x190b  ldc.i4.2
0x190c  ldarg.0
0x190d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1912  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x1917  box      [mscorlib]System.Int32
0x191c  stelem.ref
0x191d  dup
0x191e  ldc.i4.3
0x191f  ldloc.2
0x1920  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x1925  box      Microsoft.Crm.Sandbox.BucketState
0x192a  stelem.ref
0x192b  dup
0x192c  ldc.i4.4
0x192d  ldarg.0
0x192e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1933  box      [mscorlib]System.Guid
0x1938  stelem.ref
0x1939  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x193e  br       loc_1C68
0x1943  ldloc.2
0x1944  callvirt instance object Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_LockObject()
0x1949  stloc.3
0x194a  ldc.i4.0
0x194b  stloc.s  4
0x194d  ldloc.3
0x194e  ldloca.s 4
0x1950  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1955  ldloc.2
0x1956  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x195b  brfalse.s loc_19C4
0x195d  ldarg.0
0x195e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1963  ldc.i4.s 0x21
0x1965  ldstr    aOrganizationwo_18// "OrganizationWorkerList.TryToEnqueueWork"...
0x196a  ldc.i4.5
0x196b  newarr   [mscorlib]System.Object
0x1970  dup
0x1971  ldc.i4.0
0x1972  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1977  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x197c  box      [mscorlib]System.Int32
0x1981  stelem.ref
0x1982  dup
0x1983  ldc.i4.1
0x1984  ldloc.1
0x1985  box      [mscorlib]System.Int32
0x198a  stelem.ref
0x198b  dup
0x198c  ldc.i4.2
0x198d  ldarg.0
0x198e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1993  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x1998  box      [mscorlib]System.Int32
0x199d  stelem.ref
0x199e  dup
0x199f  ldc.i4.3
0x19a0  ldloc.2
0x19a1  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x19a6  box      Microsoft.Crm.Sandbox.BucketState
0x19ab  stelem.ref
0x19ac  dup
0x19ad  ldc.i4.4
0x19ae  ldarg.0
0x19af  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x19b4  box      [mscorlib]System.Guid
0x19b9  stelem.ref
0x19ba  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19bf  leave    loc_1C68
0x19c4  ldloc.2
0x19c5  ldc.i4.1
0x19c6  callvirt instance void Microsoft.Crm.Sandbox.OrganizationWorkerBucket::set_State(valuetype Microsoft.Crm.Sandbox.BucketState value)
0x19cb  ldarg.0
0x19cc  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x19d1  ldc.i4.s 0x21
0x19d3  ldstr    aOrganizationwo_19// "OrganizationWorkerList.TryToEnqueueWork"...
0x19d8  ldc.i4.5
0x19d9  newarr   [mscorlib]System.Object
0x19de  dup
0x19df  ldc.i4.0
0x19e0  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x19e5  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x19ea  box      [mscorlib]System.Int32
0x19ef  stelem.ref
0x19f0  dup
0x19f1  ldc.i4.1
0x19f2  ldloc.1
0x19f3  box      [mscorlib]System.Int32
0x19f8  stelem.ref
0x19f9  dup
0x19fa  ldc.i4.2
0x19fb  ldarg.0
0x19fc  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1a01  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x1a06  box      [mscorlib]System.Int32
0x1a0b  stelem.ref
0x1a0c  dup
0x1a0d  ldc.i4.3
0x1a0e  ldloc.2
0x1a0f  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x1a14  box      Microsoft.Crm.Sandbox.BucketState
0x1a19  stelem.ref
0x1a1a  dup
0x1a1b  ldc.i4.4
0x1a1c  ldarg.0
0x1a1d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1a22  box      [mscorlib]System.Guid
0x1a27  stelem.ref
0x1a28  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a2d  ldarg.1
0x1a2e  callvirt instance var<u1> class [mscorlib]System.Func`1<class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::Invoke()
0x1a33  stloc.s  5
0x1a35  ldloc.s  5
0x1a37  brtrue   loc_1B37
0x1a3c  ldarg.0
0x1a3d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1a42  ldc.i4.s 0x21
0x1a44  ldstr    aOrganizationwo_20// "OrganizationWorkerList.TryToEnqueueWork"...
0x1a49  ldc.i4.5
0x1a4a  newarr   [mscorlib]System.Object
0x1a4f  dup
0x1a50  ldc.i4.0
0x1a51  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1a56  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x1a5b  box      [mscorlib]System.Int32
0x1a60  stelem.ref
0x1a61  dup
0x1a62  ldc.i4.1
0x1a63  ldloc.1
0x1a64  box      [mscorlib]System.Int32
0x1a69  stelem.ref
0x1a6a  dup
0x1a6b  ldc.i4.2
0x1a6c  ldarg.0
0x1a6d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1a72  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x1a77  box      [mscorlib]System.Int32
0x1a7c  stelem.ref
0x1a7d  dup
0x1a7e  ldc.i4.3
0x1a7f  ldloc.2
0x1a80  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x1a85  box      Microsoft.Crm.Sandbox.BucketState
0x1a8a  stelem.ref
0x1a8b  dup
0x1a8c  ldc.i4.4
0x1a8d  ldarg.0
0x1a8e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1a93  box      [mscorlib]System.Guid
0x1a98  stelem.ref
0x1a99  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a9e  ldarg.2
0x1a9f  callvirt instance void [mscorlib]System.Action::Invoke()
0x1aa4  ldarg.1
0x1aa5  callvirt instance var<u1> class [mscorlib]System.Func`1<class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::Invoke()
0x1aaa  stloc.s  5
0x1aac  ldloc.s  5
0x1aae  brtrue   loc_1B37
0x1ab3  ldnull
0x1ab4  ldarg.0
0x1ab5  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1aba  ldc.i4.s 0x21
0x1abc  ldstr    aOrganizationwo_21// "OrganizationWorkerList.TryToEnqueueWork"...
0x1ac1  ldc.i4.5
0x1ac2  newarr   [mscorlib]System.Object
0x1ac7  dup
0x1ac8  ldc.i4.0
0x1ac9  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1ace  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x1ad3  box      [mscorlib]System.Int32
0x1ad8  stelem.ref
0x1ad9  dup
0x1ada  ldc.i4.1
0x1adb  ldloc.1
0x1adc  box      [mscorlib]System.Int32
0x1ae1  stelem.ref
0x1ae2  dup
0x1ae3  ldc.i4.2
0x1ae4  ldarg.0
0x1ae5  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1aea  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x1aef  box      [mscorlib]System.Int32
0x1af4  stelem.ref
0x1af5  dup
0x1af6  ldc.i4.3
0x1af7  ldloc.2
0x1af8  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x1afd  box      Microsoft.Crm.Sandbox.BucketState
0x1b02  stelem.ref
0x1b03  dup
0x1b04  ldc.i4.4
0x1b05  ldarg.0
0x1b06  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1b0b  box      [mscorlib]System.Guid
0x1b10  stelem.ref
0x1b11  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b16  ldloc.2
0x1b17  ldc.i4.0
0x1b18  callvirt instance void Microsoft.Crm.Sandbox.OrganizationWorkerBucket::set_State(valuetype Microsoft.Crm.Sandbox.BucketState value)
0x1b1d  ldloc.2
0x1b1e  callvirt instance class [mscorlib]System.Threading.AutoResetEvent Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_EnqueueSyncronization()
0x1b23  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x1b28  pop
0x1b29  ldloc.2
0x1b2a  callvirt instance void Microsoft.Crm.Sandbox.OrganizationWorkerBucket::ResetState()
0x1b2f  ldc.i4.0
0x1b30  stloc.s  6
0x1b32  leave    loc_1CA6
0x1b37  ldloc.2
0x1b38  ldc.i4.2
0x1b39  callvirt instance void Microsoft.Crm.Sandbox.OrganizationWorkerBucket::set_State(valuetype Microsoft.Crm.Sandbox.BucketState value)
0x1b3e  ldloc.2
0x1b3f  ldloc.s  5
0x1b41  callvirt instance void Microsoft.Crm.Sandbox.OrganizationWorkerBucket::set_WorkerProcess(class Microsoft.Crm.Sandbox.SandboxWorkerProcess value)
0x1b46  ldarg.3
0x1b47  ldloc.2
0x1b48  stind.ref
0x1b49  ldloc.s  5
0x1b4b  ldarg.0
0x1b4c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1b51  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x1b56  ldloc.s  5
0x1b58  ldc.i4.1
0x1b59  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::set_AssignedToOrganization(bool value)
0x1b5e  ldarg.0
0x1b5f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1b64  ldc.i4.s 0x21
0x1b66  ldstr    aOrganizationwo_22// "OrganizationWorkerList.TryToEnqueueWork"...
0x1b6b  ldc.i4.6
0x1b6c  newarr   [mscorlib]System.Object
0x1b71  dup
0x1b72  ldc.i4.0
0x1b73  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1b78  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x1b7d  box      [mscorlib]System.Int32
0x1b82  stelem.ref
0x1b83  dup
0x1b84  ldc.i4.1
0x1b85  ldloc.1
0x1b86  box      [mscorlib]System.Int32
  ... truncated ...
```
