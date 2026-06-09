# Microsoft.Crm.Sandbox.OrganizationWorkerList::ActivateInactiveBucket

- ea: `0x15b0`
- end: `0x1670`
- name: `Microsoft.Crm.Sandbox.OrganizationWorkerList::ActivateInactiveBucket`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x12b0`

## callees

- `0xc70`
- `0xc80`
- `0x15b0`

## string_xrefs

- `0x15f6`: `OrganizationWorkerList.ActivateInactiveBucket:Thread[{0:d4}] Activating bucket {1} from a total of {2} buckets. Bucket state is {3}. OrgId: {4}`

## pseudocode

```c

```

## disassembly

```asm
0x15b0  ldarg.0
0x15b1  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_orgInactiveBucketsCount
0x15b6  ldc.i4.0
0x15b7  ble      loc_166E
0x15bc  ldc.i4.0
0x15bd  stloc.0
0x15be  br       loc_165D
0x15c3  ldloc.0
0x15c4  ldarg.0
0x15c5  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_nextId
0x15ca  add
0x15cb  ldarg.0
0x15cc  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x15d1  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x15d6  rem
0x15d7  stloc.1
0x15d8  ldarg.0
0x15d9  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x15de  ldloc.1
0x15df  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Item(!!T0)
0x15e4  stloc.2
0x15e5  ldloc.2
0x15e6  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x15eb  ldc.i4.3
0x15ec  bne.un.s loc_1659
0x15ee  ldarg.0
0x15ef  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x15f4  ldc.i4.s 0x21
0x15f6  ldstr    aOrganizationwo_12// "OrganizationWorkerList.ActivateInactive"...
0x15fb  ldc.i4.5
0x15fc  newarr   [mscorlib]System.Object
0x1601  dup
0x1602  ldc.i4.0
0x1603  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1608  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x160d  box      [mscorlib]System.Int32
0x1612  stelem.ref
0x1613  dup
0x1614  ldc.i4.1
0x1615  ldloc.1
0x1616  box      [mscorlib]System.Int32
0x161b  stelem.ref
0x161c  dup
0x161d  ldc.i4.2
0x161e  ldarg.0
0x161f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1624  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x1629  box      [mscorlib]System.Int32
0x162e  stelem.ref
0x162f  dup
0x1630  ldc.i4.3
0x1631  ldloc.2
0x1632  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x1637  box      Microsoft.Crm.Sandbox.BucketState
0x163c  stelem.ref
0x163d  dup
0x163e  ldc.i4.4
0x163f  ldarg.0
0x1640  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1645  box      [mscorlib]System.Guid
0x164a  stelem.ref
0x164b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1650  ldloc.2
0x1651  ldc.i4.2
0x1652  callvirt instance void Microsoft.Crm.Sandbox.OrganizationWorkerBucket::set_State(valuetype Microsoft.Crm.Sandbox.BucketState value)
0x1657  ldc.i4.1
0x1658  ret
0x1659  ldloc.0
0x165a  ldc.i4.1
0x165b  add
0x165c  stloc.0
0x165d  ldloc.0
0x165e  ldarg.0
0x165f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1664  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x1669  blt      loc_15C3
0x166e  ldc.i4.0
0x166f  ret
```
