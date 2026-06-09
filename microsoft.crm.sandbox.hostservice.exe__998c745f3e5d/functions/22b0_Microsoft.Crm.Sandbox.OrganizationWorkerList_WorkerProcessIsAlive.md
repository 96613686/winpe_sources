# Microsoft.Crm.Sandbox.OrganizationWorkerList::WorkerProcessIsAlive

- ea: `0x22b0`
- end: `0x24a5`
- name: `Microsoft.Crm.Sandbox.OrganizationWorkerList::WorkerProcessIsAlive`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1190`

## callees

- `0x22b0`
- `0x5770`
- `0x5780`
- `0x9780`
- `0x9790`
- `0x9de0`

## string_xrefs

- `0x22d3`: `OrganizationWorkerList.WorkerProcessIsAlive:Thread[{0:d4}] Bucket {1} HasExited returned Error {2}`
- `0x2319`: `OrganizationWorkerList.TryGetReadyWorkerUri:Thread[{0:d4}] Bucket {1} process has exited`
- `0x236e`: `OrganizationWorkerList.TryGetReadyWorkerUri:Thread[{0:d4}] Bucket {1} channel is null`
- `0x23e2`: `OrganizationWorkerList.TryGetReadyWorkerUri:Thread[{0:d4}] Bucket {1} channel has state {2}`
- `0x2441`: `OrganizationWorkerList.WorkerProcessIsAlive:Thread[{0:d4}] Bucket {1} status is Ready - returning true`
- `0x2476`: `OrganizationWorkerList.WorkerProcessIsAlive:Thread[{0:d4}] Bucket {1} status is not Ready - returning false`

## pseudocode

```c

```

## disassembly

```asm
0x22b0  ldarg.1
0x22b1  callvirt instance class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerProcess()
0x22b6  callvirt instance void [System]System.Diagnostics.Process::Refresh()
0x22bb  ldarg.1
0x22bc  callvirt instance class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerProcess()
0x22c1  callvirt instance bool [System]System.Diagnostics.Process::get_HasExited()
0x22c6  stloc.0
0x22c7  leave.s  loc_230E
0x22c9  stloc.2
0x22ca  ldloc.2
0x22cb  ldarg.0
0x22cc  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x22d1  ldc.i4.s 0x21
0x22d3  ldstr    aOrganizationwo_38// "OrganizationWorkerList.WorkerProcessIsA"...
0x22d8  ldc.i4.3
0x22d9  newarr   [mscorlib]System.Object
0x22de  dup
0x22df  ldc.i4.0
0x22e0  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x22e5  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x22ea  box      [mscorlib]System.Int32
0x22ef  stelem.ref
0x22f0  dup
0x22f1  ldc.i4.1
0x22f2  ldarg.2
0x22f3  box      [mscorlib]System.Int32
0x22f8  stelem.ref
0x22f9  dup
0x22fa  ldc.i4.2
0x22fb  ldloc.2
0x22fc  callvirt instance string [mscorlib]System.Object::ToString()
0x2301  stelem.ref
0x2302  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2307  ldc.i4.0
0x2308  stloc.3
0x2309  leave    loc_24A3
0x230e  ldloc.0
0x230f  brfalse.s loc_2359
0x2311  ldarg.0
0x2312  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x2317  ldc.i4.s 0x21
0x2319  ldstr    aOrganizationwo_39// "OrganizationWorkerList.TryGetReadyWorke"...
0x231e  ldc.i4.2
0x231f  newarr   [mscorlib]System.Object
0x2324  dup
0x2325  ldc.i4.0
0x2326  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x232b  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x2330  box      [mscorlib]System.Int32
0x2335  stelem.ref
0x2336  dup
0x2337  ldc.i4.1
0x2338  ldarg.2
0x2339  box      [mscorlib]System.Int32
0x233e  stelem.ref
0x233f  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2344  ldarg.1
0x2345  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerClient()
0x234a  ldc.i4.4
0x234b  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::set_WorkerStatus(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus value)
0x2350  ldarg.1
0x2351  ldc.i4.5
0x2352  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::Exit(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason exitReason)
0x2357  ldc.i4.0
0x2358  ret
0x2359  ldarg.1
0x235a  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerClient()
0x235f  callvirt instance var<u1> class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker>::get_RawProxy()
0x2364  brtrue.s loc_23AE
0x2366  ldarg.0
0x2367  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x236c  ldc.i4.s 0x21
0x236e  ldstr    aOrganizationwo_40// "OrganizationWorkerList.TryGetReadyWorke"...
0x2373  ldc.i4.2
0x2374  newarr   [mscorlib]System.Object
0x2379  dup
0x237a  ldc.i4.0
0x237b  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2380  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x2385  box      [mscorlib]System.Int32
0x238a  stelem.ref
0x238b  dup
0x238c  ldc.i4.1
0x238d  ldarg.2
0x238e  box      [mscorlib]System.Int32
0x2393  stelem.ref
0x2394  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2399  ldarg.1
0x239a  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerClient()
0x239f  ldc.i4.4
0x23a0  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::set_WorkerStatus(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus value)
0x23a5  ldarg.1
0x23a6  ldc.i4.5
0x23a7  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::Exit(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason exitReason)
0x23ac  ldc.i4.0
0x23ad  ret
0x23ae  ldarg.1
0x23af  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerClient()
0x23b4  callvirt instance var<u1> class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker>::get_RawProxy()
0x23b9  castclass [System.ServiceModel]System.ServiceModel.IClientChannel
0x23be  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.CommunicationState [System.ServiceModel]System.ServiceModel.ICommunicationObject::get_State()
0x23c3  stloc.1
0x23c4  ldloc.1
0x23c5  ldc.i4.3
0x23c6  sub
0x23c7  switch   loc_23DA, loc_23DA, loc_23DA
0x23d8  br.s     loc_242B
0x23da  ldarg.0
0x23db  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x23e0  ldc.i4.s 0x21
0x23e2  ldstr    aOrganizationwo_41// "OrganizationWorkerList.TryGetReadyWorke"...
0x23e7  ldc.i4.3
0x23e8  newarr   [mscorlib]System.Object
0x23ed  dup
0x23ee  ldc.i4.0
0x23ef  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x23f4  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x23f9  box      [mscorlib]System.Int32
0x23fe  stelem.ref
0x23ff  dup
0x2400  ldc.i4.1
0x2401  ldarg.2
0x2402  box      [mscorlib]System.Int32
0x2407  stelem.ref
0x2408  dup
0x2409  ldc.i4.2
0x240a  ldloc.1
0x240b  box      [System.ServiceModel]System.ServiceModel.CommunicationState
0x2410  stelem.ref
0x2411  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2416  ldarg.1
0x2417  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerClient()
0x241c  ldc.i4.4
0x241d  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::set_WorkerStatus(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus value)
0x2422  ldarg.1
0x2423  ldc.i4.5
0x2424  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::Exit(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason exitReason)
0x2429  ldc.i4.0
0x242a  ret
0x242b  ldarg.1
0x242c  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerClient()
0x2431  callvirt instance valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxWorkerClient::get_WorkerStatus()
0x2436  ldc.i4.3
0x2437  bne.un.s loc_246E
0x2439  ldarg.0
0x243a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x243f  ldc.i4.s 0x21
0x2441  ldstr    aOrganizationwo_42// "OrganizationWorkerList.WorkerProcessIsA"...
0x2446  ldc.i4.2
0x2447  newarr   [mscorlib]System.Object
0x244c  dup
0x244d  ldc.i4.0
0x244e  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2453  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x2458  box      [mscorlib]System.Int32
0x245d  stelem.ref
0x245e  dup
0x245f  ldc.i4.1
0x2460  ldarg.2
0x2461  box      [mscorlib]System.Int32
0x2466  stelem.ref
0x2467  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x246c  ldc.i4.1
0x246d  ret
0x246e  ldarg.0
0x246f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x2474  ldc.i4.s 0x21
0x2476  ldstr    aOrganizationwo_43// "OrganizationWorkerList.WorkerProcessIsA"...
0x247b  ldc.i4.2
0x247c  newarr   [mscorlib]System.Object
0x2481  dup
0x2482  ldc.i4.0
0x2483  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2488  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x248d  box      [mscorlib]System.Int32
0x2492  stelem.ref
0x2493  dup
0x2494  ldc.i4.1
0x2495  ldarg.2
0x2496  box      [mscorlib]System.Int32
0x249b  stelem.ref
0x249c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x24a1  ldc.i4.0
0x24a2  ret
0x24a3  ldloc.3
0x24a4  ret
```
