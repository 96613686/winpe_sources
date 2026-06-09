# Microsoft.Crm.Sandbox.OrganizationWorkerList::TryGetReadyWorkerUri

- ea: `0x2040`
- end: `0x22ac`
- name: `Microsoft.Crm.Sandbox.OrganizationWorkerList::TryGetReadyWorkerUri`
- size: `620`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x12b0`

## callees

- `0xc50`
- `0xc70`
- `0xe70`
- `0x2040`
- `0x9840`

## string_xrefs

- `0x207d`: `OrganizationWorkerList.TryGetReadyWorkerUri:Thread[{0:d4}] Skipping bucket {1} from a total of {2} buckets. Bucket state is {3}. OrgId: {4}`
- `0x20e4`: `OrganizationWorkerList.TryGetReadyWorkerUri:Thread[{0:d4}] Trying to get a worker from bucket {1} from a total of {2} buckets. Bucket state is {3}. OrgId: {4}`
- `0x2150`: `OrganizationWorkerList.TryGetReadyWorkerUri:Thread[{0:d4}] Bucket {1} has null URI. Bucket state is {2}. OrgId: {3}`
- `0x21bb`: `OrganizationWorkerList.TryGetReadyWorkerUri:Thread[{0:d4}] Worker {1} is ready and can process this request, it has a total of {2} active worker request, maximum is {3}. OrgId: {4}`
- `0x2240`: `OrganizationWorkerList.TryGetReadyWorkerUri:Thread[{0:d4}] Worker {1} is ready but cannot process this request, it has a total of {2} active worker request, maximum is {3}. OrgId: {4}`

## pseudocode

```c

```

## disassembly

```asm
0x2040  ldarg.1
0x2041  ldnull
0x2042  stind.ref
0x2043  ldc.i4.0
0x2044  stloc.0
0x2045  br       loc_2299
0x204a  ldloc.0
0x204b  ldarg.0
0x204c  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_nextId
0x2051  add
0x2052  ldarg.0
0x2053  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x2058  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x205d  rem
0x205e  stloc.1
0x205f  ldarg.0
0x2060  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x2065  ldloc.1
0x2066  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Item(!!T0)
0x206b  stloc.2
0x206c  ldloc.2
0x206d  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x2072  ldc.i4.2
0x2073  beq.s    loc_20DC
0x2075  ldarg.0
0x2076  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x207b  ldc.i4.s 0x21
0x207d  ldstr    aOrganizationwo_33// "OrganizationWorkerList.TryGetReadyWorke"...
0x2082  ldc.i4.5
0x2083  newarr   [mscorlib]System.Object
0x2088  dup
0x2089  ldc.i4.0
0x208a  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x208f  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x2094  box      [mscorlib]System.Int32
0x2099  stelem.ref
0x209a  dup
0x209b  ldc.i4.1
0x209c  ldloc.1
0x209d  box      [mscorlib]System.Int32
0x20a2  stelem.ref
0x20a3  dup
0x20a4  ldc.i4.2
0x20a5  ldarg.0
0x20a6  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x20ab  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x20b0  box      [mscorlib]System.Int32
0x20b5  stelem.ref
0x20b6  dup
0x20b7  ldc.i4.3
0x20b8  ldloc.2
0x20b9  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x20be  box      Microsoft.Crm.Sandbox.BucketState
0x20c3  stelem.ref
0x20c4  dup
0x20c5  ldc.i4.4
0x20c6  ldarg.0
0x20c7  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x20cc  box      [mscorlib]System.Guid
0x20d1  stelem.ref
0x20d2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20d7  br       loc_2295
0x20dc  ldarg.0
0x20dd  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x20e2  ldc.i4.s 0x21
0x20e4  ldstr    aOrganizationwo_34// "OrganizationWorkerList.TryGetReadyWorke"...
0x20e9  ldc.i4.5
0x20ea  newarr   [mscorlib]System.Object
0x20ef  dup
0x20f0  ldc.i4.0
0x20f1  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x20f6  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x20fb  box      [mscorlib]System.Int32
0x2100  stelem.ref
0x2101  dup
0x2102  ldc.i4.1
0x2103  ldloc.1
0x2104  box      [mscorlib]System.Int32
0x2109  stelem.ref
0x210a  dup
0x210b  ldc.i4.2
0x210c  ldarg.0
0x210d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x2112  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x2117  box      [mscorlib]System.Int32
0x211c  stelem.ref
0x211d  dup
0x211e  ldc.i4.3
0x211f  ldloc.2
0x2120  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x2125  box      Microsoft.Crm.Sandbox.BucketState
0x212a  stelem.ref
0x212b  dup
0x212c  ldc.i4.4
0x212d  ldarg.0
0x212e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x2133  box      [mscorlib]System.Guid
0x2138  stelem.ref
0x2139  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x213e  ldloc.2
0x213f  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerProcess Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_WorkerProcess()
0x2144  stloc.3
0x2145  ldloc.3
0x2146  brtrue.s loc_21A2
0x2148  ldarg.0
0x2149  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x214e  ldc.i4.s 0x21
0x2150  ldstr    aOrganizationwo_35// "OrganizationWorkerList.TryGetReadyWorke"...
0x2155  ldc.i4.4
0x2156  newarr   [mscorlib]System.Object
0x215b  dup
0x215c  ldc.i4.0
0x215d  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2162  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x2167  box      [mscorlib]System.Int32
0x216c  stelem.ref
0x216d  dup
0x216e  ldc.i4.1
0x216f  ldloc.1
0x2170  box      [mscorlib]System.Int32
0x2175  stelem.ref
0x2176  dup
0x2177  ldc.i4.2
0x2178  ldloc.2
0x2179  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x217e  box      Microsoft.Crm.Sandbox.BucketState
0x2183  stelem.ref
0x2184  dup
0x2185  ldc.i4.3
0x2186  ldarg.0
0x2187  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x218c  box      [mscorlib]System.Guid
0x2191  stelem.ref
0x2192  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2197  ldloc.2
0x2198  callvirt instance void Microsoft.Crm.Sandbox.OrganizationWorkerBucket::ResetState()
0x219d  br       loc_2295
0x21a2  ldloc.3
0x21a3  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_TotalActiveWorkerRequestCount()
0x21a8  ldarg.0
0x21a9  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_maxConcurrentRequests
0x21ae  bge      loc_2238
0x21b3  ldarg.0
0x21b4  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x21b9  ldc.i4.s 0x21
0x21bb  ldstr    aOrganizationwo_36// "OrganizationWorkerList.TryGetReadyWorke"...
0x21c0  ldc.i4.5
0x21c1  newarr   [mscorlib]System.Object
0x21c6  dup
0x21c7  ldc.i4.0
0x21c8  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x21cd  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x21d2  box      [mscorlib]System.Int32
0x21d7  stelem.ref
0x21d8  dup
0x21d9  ldc.i4.1
0x21da  ldloc.1
0x21db  box      [mscorlib]System.Int32
0x21e0  stelem.ref
0x21e1  dup
0x21e2  ldc.i4.2
0x21e3  ldloc.3
0x21e4  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_TotalActiveWorkerRequestCount()
0x21e9  box      [mscorlib]System.Int32
0x21ee  stelem.ref
0x21ef  dup
0x21f0  ldc.i4.3
0x21f1  ldarg.0
0x21f2  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_maxConcurrentRequests
0x21f7  box      [mscorlib]System.Int32
0x21fc  stelem.ref
0x21fd  dup
0x21fe  ldc.i4.4
0x21ff  ldarg.0
0x2200  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x2205  box      [mscorlib]System.Guid
0x220a  stelem.ref
0x220b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2210  ldarg.0
0x2211  ldarg.0
0x2212  ldfld    int64 Microsoft.Crm.Sandbox.OrganizationWorkerList::_workersReadyCount
0x2217  ldc.i4.1
0x2218  conv.i8
0x2219  add
0x221a  stfld    int64 Microsoft.Crm.Sandbox.OrganizationWorkerList::_workersReadyCount
0x221f  ldarg.0
0x2220  ldarg.0
0x2221  ldfld    int64 Microsoft.Crm.Sandbox.OrganizationWorkerList::_workersReadyCount
0x2226  ldloc.3
0x2227  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_TotalActiveWorkerRequestCount()
0x222c  conv.i8
0x222d  add
0x222e  stfld    int64 Microsoft.Crm.Sandbox.OrganizationWorkerList::_workersReadyCount
0x2233  ldarg.1
0x2234  ldloc.2
0x2235  stind.ref
0x2236  ldc.i4.1
0x2237  ret
0x2238  ldarg.0
0x2239  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x223e  ldc.i4.s 0x21
0x2240  ldstr    aOrganizationwo_37// "OrganizationWorkerList.TryGetReadyWorke"...
0x2245  ldc.i4.5
0x2246  newarr   [mscorlib]System.Object
0x224b  dup
0x224c  ldc.i4.0
0x224d  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2252  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x2257  box      [mscorlib]System.Int32
0x225c  stelem.ref
0x225d  dup
0x225e  ldc.i4.1
0x225f  ldloc.1
0x2260  box      [mscorlib]System.Int32
0x2265  stelem.ref
0x2266  dup
0x2267  ldc.i4.2
0x2268  ldloc.3
0x2269  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_TotalActiveWorkerRequestCount()
0x226e  box      [mscorlib]System.Int32
0x2273  stelem.ref
0x2274  dup
0x2275  ldc.i4.3
0x2276  ldarg.0
0x2277  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_maxConcurrentRequests
0x227c  box      [mscorlib]System.Int32
0x2281  stelem.ref
0x2282  dup
0x2283  ldc.i4.4
0x2284  ldarg.0
0x2285  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x228a  box      [mscorlib]System.Guid
0x228f  stelem.ref
0x2290  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2295  ldloc.0
0x2296  ldc.i4.1
0x2297  add
0x2298  stloc.0
0x2299  ldloc.0
0x229a  ldarg.0
0x229b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x22a0  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x22a5  blt      loc_204A
0x22aa  ldc.i4.0
0x22ab  ret
```
