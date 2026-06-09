# Microsoft.Crm.Sandbox.OrganizationWorkerList::TryGetNextWorkerProcess

- ea: `0x1190`
- end: `0x12ad`
- name: `Microsoft.Crm.Sandbox.OrganizationWorkerList::TryGetNextWorkerProcess`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x7610`

## callees

- `0xc50`
- `0xc70`
- `0xe50`
- `0xe70`
- `0x1190`
- `0x12b0`
- `0x22b0`
- `0x9840`

## string_xrefs

- `0x11da`: `OrganizationWorkerList.TryGetNextWorkerProcess:Thread[{0:d4}] Reusing {1} as next worker process`
- `0x123c`: `OrganizationWorkerList.TryGetNextWorkerProcess:Thread[{0:d4}] Returning {1} as next worker process`
- `0x1285`: `OrganizationWorkerList.TryGetNextWorkerProcess:Thread[{0:d4}] Could not find any available worker process`

## pseudocode

```c

```

## disassembly

```asm
0x1190  ldarg.0
0x1191  ldfld    class Microsoft.Crm.Sandbox.OrganizationWorkerBucket Microsoft.Crm.Sandbox.OrganizationWorkerList::_previousUsedBucket
0x1196  brfalse.s loc_1202
0x1198  ldarg.0
0x1199  ldfld    class Microsoft.Crm.Sandbox.OrganizationWorkerBucket Microsoft.Crm.Sandbox.OrganizationWorkerList::_previousUsedBucket
0x119e  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x11a3  ldc.i4.2
0x11a4  bne.un.s loc_1202
0x11a6  ldarg.0
0x11a7  ldfld    class Microsoft.Crm.Sandbox.OrganizationWorkerBucket Microsoft.Crm.Sandbox.OrganizationWorkerList::_previousUsedBucket
0x11ac  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerProcess Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_WorkerProcess()
0x11b1  brfalse.s loc_1202
0x11b3  ldarg.0
0x11b4  ldfld    class Microsoft.Crm.Sandbox.OrganizationWorkerBucket Microsoft.Crm.Sandbox.OrganizationWorkerList::_previousUsedBucket
0x11b9  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerProcess Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_WorkerProcess()
0x11be  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_TotalActiveWorkerRequestCount()
0x11c3  ldarg.0
0x11c4  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_minConcurrentRequests
0x11c9  bge.s    loc_1202
0x11cb  ldarg.0
0x11cc  ldfld    class Microsoft.Crm.Sandbox.OrganizationWorkerBucket Microsoft.Crm.Sandbox.OrganizationWorkerList::_previousUsedBucket
0x11d1  stloc.0
0x11d2  ldarg.0
0x11d3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x11d8  ldc.i4.s 0x21
0x11da  ldstr    aOrganizationwo_1// "OrganizationWorkerList.TryGetNextWorker"...
0x11df  ldc.i4.2
0x11e0  newarr   [mscorlib]System.Object
0x11e5  dup
0x11e6  ldc.i4.0
0x11e7  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x11ec  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x11f1  box      [mscorlib]System.Int32
0x11f6  stelem.ref
0x11f7  dup
0x11f8  ldc.i4.1
0x11f9  ldloc.0
0x11fa  stelem.ref
0x11fb  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1200  br.s     loc_1215
0x1202  ldarg.0
0x1203  ldarg.2
0x1204  ldarg.3
0x1205  ldloca.s 0
0x1207  call     instance bool Microsoft.Crm.Sandbox.OrganizationWorkerList::TryGetNextWorkerProcessInternal(class [mscorlib]System.Func`1<class Microsoft.Crm.Sandbox.SandboxWorkerProcess> getCleanWorkerProcessFromQueue, class [mscorlib]System.Action startNewWorkersInBackground, [out] class Microsoft.Crm.Sandbox.OrganizationWorkerBucket& returnValue)
0x120c  brfalse.s loc_1215
0x120e  ldarg.0
0x120f  ldloc.0
0x1210  stfld    class Microsoft.Crm.Sandbox.OrganizationWorkerBucket Microsoft.Crm.Sandbox.OrganizationWorkerList::_previousUsedBucket
0x1215  ldloc.0
0x1216  brfalse.s loc_126D
0x1218  ldloc.0
0x1219  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerProcess Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_WorkerProcess()
0x121e  brfalse.s loc_126D
0x1220  ldarg.0
0x1221  ldloc.0
0x1222  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerProcess Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_WorkerProcess()
0x1227  ldloc.0
0x1228  callvirt instance int32 Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_Id()
0x122d  call     instance bool Microsoft.Crm.Sandbox.OrganizationWorkerList::WorkerProcessIsAlive(class Microsoft.Crm.Sandbox.SandboxWorkerProcess workerProcess, int32 bucketId)
0x1232  brfalse.s loc_126D
0x1234  ldarg.0
0x1235  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x123a  ldc.i4.s 0x21
0x123c  ldstr    aOrganizationwo_2// "OrganizationWorkerList.TryGetNextWorker"...
0x1241  ldc.i4.2
0x1242  newarr   [mscorlib]System.Object
0x1247  dup
0x1248  ldc.i4.0
0x1249  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x124e  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x1253  box      [mscorlib]System.Int32
0x1258  stelem.ref
0x1259  dup
0x125a  ldc.i4.1
0x125b  ldloc.0
0x125c  stelem.ref
0x125d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1262  ldarg.s  4
0x1264  ldloc.0
0x1265  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerProcess Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_WorkerProcess()
0x126a  stind.ref
0x126b  ldc.i4.1
0x126c  ret
0x126d  ldloc.0
0x126e  brfalse.s loc_1276
0x1270  ldloc.0
0x1271  callvirt instance void Microsoft.Crm.Sandbox.OrganizationWorkerBucket::ResetState()
0x1276  ldarg.0
0x1277  ldnull
0x1278  stfld    class Microsoft.Crm.Sandbox.OrganizationWorkerBucket Microsoft.Crm.Sandbox.OrganizationWorkerList::_previousUsedBucket
0x127d  ldarg.0
0x127e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1283  ldc.i4.s 0x21
0x1285  ldstr    aOrganizationwo_3// "OrganizationWorkerList.TryGetNextWorker"...
0x128a  ldc.i4.1
0x128b  newarr   [mscorlib]System.Object
0x1290  dup
0x1291  ldc.i4.0
0x1292  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1297  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x129c  box      [mscorlib]System.Int32
0x12a1  stelem.ref
0x12a2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x12a7  ldarg.s  4
0x12a9  ldnull
0x12aa  stind.ref
0x12ab  ldc.i4.0
0x12ac  ret
```
