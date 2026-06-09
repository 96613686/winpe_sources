# Microsoft.Crm.Sandbox.OrganizationWorkerList::TryGetNextWorkerProcessInternal

- ea: `0x12b0`
- end: `0x15ae`
- name: `Microsoft.Crm.Sandbox.OrganizationWorkerList::TryGetNextWorkerProcessInternal`
- size: `766`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1190`

## callees

- `0xc50`
- `0xc70`
- `0x12b0`
- `0x15b0`
- `0x1670`
- `0x1870`
- `0x1cb0`
- `0x1f10`
- `0x2040`
- `0x24b0`

## string_xrefs

- `0x1325`: `OrganizationWorkerList.TryGetNextWorkerProcessInternal:Thread[{0:d4}] Returning {1} as next worker process, from TryGetReadyWorkerUri`
- `0x1367`: `OrganizationWorkerList.TryGetNextWorkerProcess:Thread[{0:d4}] Returning {1} as next worker process, from TryGetReadyWorkerUri`
- `0x13a1`: `OrganizationWorkerList.TryGetNextWorkerProcess:Thread[{0:d4}] Returning {1} as next worker process, from TryGetEnqueuedWorkerUri`
- `0x13dd`: `OrganizationWorkerList.TryGetNextWorkerProcess:Thread[{0:d4}] Assigning new worker process for org. Returning {1} as next worker process, from TryToEnqueueWorkerUri`
- `0x144f`: `OrganizationWorkerList.TryGetNextWorkerProcess:Thread[{0:d4}] Returning {1} as next worker process for org {2}, from first next bucket, ignoring max count.`
- `0x14a3`: `OrganizationWorkerList.TryGetNextWorkerProcessInternal:Thread[{0:d4}] Waiting for bucket {1} to initialize to process org {2}. Ignoring queue size.`
- `0x1524`: `OrganizationWorkerList.TryGetNextWorkerProcess:Thread[{0:d4}] Returning {1} as next worker process for org {2}. Had to wait for the next one.`
- `0x157c`: `OrganizationWorkerList.TryGetNextWorkerProcess:Thread[{0:d4}] No available bucket ready or available to wait for org {1}`

## pseudocode

```c

```

## disassembly

```asm
0x12b0  ldarg.0
0x12b1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x12b6  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x12bb  ldc.i4.1
0x12bc  ble.s    loc_1314
0x12be  ldc.i4.1
0x12bf  stloc.2
0x12c0  br.s     loc_1300
0x12c2  ldloc.2
0x12c3  ldarg.0
0x12c4  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_nextId
0x12c9  add
0x12ca  ldarg.0
0x12cb  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x12d0  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x12d5  rem
0x12d6  stloc.3
0x12d7  ldarg.0
0x12d8  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x12dd  ldloc.3
0x12de  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Item(!!T0)
0x12e3  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x12e8  stloc.s  4
0x12ea  ldloc.s  4
0x12ec  brfalse.s loc_12FC
0x12ee  ldloc.s  4
0x12f0  ldc.i4.3
0x12f1  beq.s    loc_12FC
0x12f3  ldarg.0
0x12f4  ldloc.3
0x12f5  stfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_nextId
0x12fa  br.s     loc_130E
0x12fc  ldloc.2
0x12fd  ldc.i4.1
0x12fe  add
0x12ff  stloc.2
0x1300  ldloc.2
0x1301  ldarg.0
0x1302  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1307  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x130c  blt.s    loc_12C2
0x130e  ldarg.0
0x130f  call     instance void Microsoft.Crm.Sandbox.OrganizationWorkerList::ScaleDownIfNeeded()
0x1314  ldarg.0
0x1315  ldarg.3
0x1316  call     instance bool Microsoft.Crm.Sandbox.OrganizationWorkerList::TryGetReadyWorkerUri([out] class Microsoft.Crm.Sandbox.OrganizationWorkerBucket& returnValue)
0x131b  brfalse.s loc_134E
0x131d  ldarg.0
0x131e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1323  ldc.i4.s 0x21
0x1325  ldstr    aOrganizationwo_4// "OrganizationWorkerList.TryGetNextWorker"...
0x132a  ldc.i4.2
0x132b  newarr   [mscorlib]System.Object
0x1330  dup
0x1331  ldc.i4.0
0x1332  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1337  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x133c  box      [mscorlib]System.Int32
0x1341  stelem.ref
0x1342  dup
0x1343  ldc.i4.1
0x1344  ldarg.3
0x1345  ldind.ref
0x1346  stelem.ref
0x1347  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x134c  ldc.i4.1
0x134d  ret
0x134e  ldarg.0
0x134f  call     instance bool Microsoft.Crm.Sandbox.OrganizationWorkerList::ActivateInactiveBucket()
0x1354  brfalse.s loc_1390
0x1356  ldarg.0
0x1357  ldarg.3
0x1358  call     instance bool Microsoft.Crm.Sandbox.OrganizationWorkerList::TryGetReadyWorkerUri([out] class Microsoft.Crm.Sandbox.OrganizationWorkerBucket& returnValue)
0x135d  brfalse.s loc_1390
0x135f  ldarg.0
0x1360  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1365  ldc.i4.s 0x21
0x1367  ldstr    aOrganizationwo_5// "OrganizationWorkerList.TryGetNextWorker"...
0x136c  ldc.i4.2
0x136d  newarr   [mscorlib]System.Object
0x1372  dup
0x1373  ldc.i4.0
0x1374  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1379  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x137e  box      [mscorlib]System.Int32
0x1383  stelem.ref
0x1384  dup
0x1385  ldc.i4.1
0x1386  ldarg.3
0x1387  ldind.ref
0x1388  stelem.ref
0x1389  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x138e  ldc.i4.1
0x138f  ret
0x1390  ldarg.0
0x1391  ldarg.3
0x1392  call     instance bool Microsoft.Crm.Sandbox.OrganizationWorkerList::TryGetEnqueuedWorkerUri([out] class Microsoft.Crm.Sandbox.OrganizationWorkerBucket& returnValue)
0x1397  brfalse.s loc_13CA
0x1399  ldarg.0
0x139a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x139f  ldc.i4.s 0x21
0x13a1  ldstr    aOrganizationwo_6// "OrganizationWorkerList.TryGetNextWorker"...
0x13a6  ldc.i4.2
0x13a7  newarr   [mscorlib]System.Object
0x13ac  dup
0x13ad  ldc.i4.0
0x13ae  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x13b3  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x13b8  box      [mscorlib]System.Int32
0x13bd  stelem.ref
0x13be  dup
0x13bf  ldc.i4.1
0x13c0  ldarg.3
0x13c1  ldind.ref
0x13c2  stelem.ref
0x13c3  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13c8  ldc.i4.1
0x13c9  ret
0x13ca  ldarg.0
0x13cb  ldarg.1
0x13cc  ldarg.2
0x13cd  ldarg.3
0x13ce  call     instance bool Microsoft.Crm.Sandbox.OrganizationWorkerList::TryToEnqueueWorkerUri(class [mscorlib]System.Func`1<class Microsoft.Crm.Sandbox.SandboxWorkerProcess> getCleanWorkerProcessFromQueue, class [mscorlib]System.Action startNewWorkersInBackground, [out] class Microsoft.Crm.Sandbox.OrganizationWorkerBucket& returnValue)
0x13d3  brfalse.s loc_141B
0x13d5  ldarg.0
0x13d6  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x13db  ldc.i4.s 0x21
0x13dd  ldstr    aOrganizationwo_7// "OrganizationWorkerList.TryGetNextWorker"...
0x13e2  ldc.i4.2
0x13e3  newarr   [mscorlib]System.Object
0x13e8  dup
0x13e9  ldc.i4.0
0x13ea  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x13ef  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x13f4  box      [mscorlib]System.Int32
0x13f9  stelem.ref
0x13fa  dup
0x13fb  ldc.i4.1
0x13fc  ldarg.3
0x13fd  ldind.ref
0x13fe  stelem.ref
0x13ff  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1404  ldarg.0
0x1405  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x140a  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0x140f  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::WorkerProcessActive()
0x1414  call     void Microsoft.Crm.Sandbox.OrganizationWorkerList::LogMapChanged()
0x1419  ldc.i4.1
0x141a  ret
0x141b  ldarg.0
0x141c  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_nextId
0x1421  ldarg.0
0x1422  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1427  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x142c  rem
0x142d  stloc.0
0x142e  ldarg.0
0x142f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1434  ldloc.0
0x1435  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Item(!!T0)
0x143a  stloc.1
0x143b  ldloc.1
0x143c  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x1441  ldc.i4.2
0x1442  bne.un.s loc_1486
0x1444  ldarg.3
0x1445  ldloc.1
0x1446  stind.ref
0x1447  ldarg.0
0x1448  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x144d  ldc.i4.s 0x21
0x144f  ldstr    aOrganizationwo_8// "OrganizationWorkerList.TryGetNextWorker"...
0x1454  ldc.i4.3
0x1455  newarr   [mscorlib]System.Object
0x145a  dup
0x145b  ldc.i4.0
0x145c  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1461  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x1466  box      [mscorlib]System.Int32
0x146b  stelem.ref
0x146c  dup
0x146d  ldc.i4.1
0x146e  ldarg.3
0x146f  ldind.ref
0x1470  stelem.ref
0x1471  dup
0x1472  ldc.i4.2
0x1473  ldarg.0
0x1474  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1479  box      [mscorlib]System.Guid
0x147e  stelem.ref
0x147f  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1484  ldc.i4.1
0x1485  ret
0x1486  ldloc.1
0x1487  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x148c  ldc.i4.1
0x148d  bne.un.s loc_14DE
0x148f  ldarg.0
0x1490  ldloc.1
0x1491  call     instance bool Microsoft.Crm.Sandbox.OrganizationWorkerList::WaitForBucket(class Microsoft.Crm.Sandbox.OrganizationWorkerBucket organizationWorkerBucket)
0x1496  brfalse.s loc_14DE
0x1498  ldarg.3
0x1499  ldloc.1
0x149a  stind.ref
0x149b  ldarg.0
0x149c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x14a1  ldc.i4.s 0x21
0x14a3  ldstr    aOrganizationwo_9// "OrganizationWorkerList.TryGetNextWorker"...
0x14a8  ldc.i4.3
0x14a9  newarr   [mscorlib]System.Object
0x14ae  dup
0x14af  ldc.i4.0
0x14b0  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x14b5  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x14ba  box      [mscorlib]System.Int32
0x14bf  stelem.ref
0x14c0  dup
0x14c1  ldc.i4.1
0x14c2  ldloc.0
0x14c3  box      [mscorlib]System.Int32
0x14c8  stelem.ref
0x14c9  dup
0x14ca  ldc.i4.2
0x14cb  ldarg.0
0x14cc  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x14d1  box      [mscorlib]System.Guid
0x14d6  stelem.ref
0x14d7  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x14dc  ldc.i4.1
0x14dd  ret
0x14de  ldc.i4.0
0x14df  stloc.s  5
0x14e1  br.s     loc_1561
0x14e3  ldloc.s  5
0x14e5  ldarg.0
0x14e6  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_nextId
0x14eb  add
0x14ec  ldarg.0
0x14ed  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x14f2  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x14f7  rem
0x14f8  stloc.s  6
0x14fa  ldarg.0
0x14fb  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1500  ldloc.s  6
0x1502  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Item(!!T0)
0x1507  stloc.1
0x1508  ldloc.1
0x1509  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x150e  ldc.i4.2
0x150f  bne.un.s loc_155B
0x1511  ldloc.1
0x1512  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerProcess Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_WorkerProcess()
0x1517  brfalse.s loc_155B
0x1519  ldarg.3
0x151a  ldloc.1
0x151b  stind.ref
0x151c  ldarg.0
0x151d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1522  ldc.i4.s 0x21
0x1524  ldstr    aOrganizationwo_10// "OrganizationWorkerList.TryGetNextWorker"...
0x1529  ldc.i4.3
0x152a  newarr   [mscorlib]System.Object
0x152f  dup
0x1530  ldc.i4.0
0x1531  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1536  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x153b  box      [mscorlib]System.Int32
0x1540  stelem.ref
0x1541  dup
0x1542  ldc.i4.1
0x1543  ldarg.3
0x1544  ldind.ref
0x1545  stelem.ref
0x1546  dup
0x1547  ldc.i4.2
0x1548  ldarg.0
0x1549  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x154e  box      [mscorlib]System.Guid
0x1553  stelem.ref
0x1554  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1559  ldc.i4.1
0x155a  ret
0x155b  ldloc.s  5
0x155d  ldc.i4.1
0x155e  add
0x155f  stloc.s  5
0x1561  ldloc.s  5
0x1563  ldarg.0
0x1564  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1569  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x156e  blt      loc_14E3
0x1573  ldnull
0x1574  ldarg.0
0x1575  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x157a  ldc.i4.s 0x21
0x157c  ldstr    aOrganizationwo_11// "OrganizationWorkerList.TryGetNextWorker"...
0x1581  ldc.i4.2
0x1582  newarr   [mscorlib]System.Object
  ... truncated ...
```
