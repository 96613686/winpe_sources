# Microsoft.Crm.Sandbox.OrganizationWorkerList::InvalidateReadyBucket

- ea: `0x17b0`
- end: `0x1861`
- name: `Microsoft.Crm.Sandbox.OrganizationWorkerList::InvalidateReadyBucket`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1670`

## callees

- `0xc70`
- `0xc80`
- `0x17b0`

## string_xrefs

- `0x17ea`: `OrganizationWorkerList.InvalidateReadyBucket:Thread[{0:d4}] Invalidating bucket {1} from a total of {2} buckets. Bucket state is {3}. OrgId: {4}`

## pseudocode

```c

```

## disassembly

```asm
0x17b0  ldc.i4.0
0x17b1  stloc.0
0x17b2  br       loc_184F
0x17b7  ldloc.0
0x17b8  ldarg.0
0x17b9  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_nextId
0x17be  add
0x17bf  ldarg.0
0x17c0  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x17c5  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x17ca  rem
0x17cb  stloc.1
0x17cc  ldarg.0
0x17cd  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x17d2  ldloc.1
0x17d3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Item(!!T0)
0x17d8  stloc.2
0x17d9  ldloc.2
0x17da  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x17df  ldc.i4.2
0x17e0  bne.un.s loc_184B
0x17e2  ldarg.0
0x17e3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x17e8  ldc.i4.s 0x21
0x17ea  ldstr    aOrganizationwo_15// "OrganizationWorkerList.InvalidateReadyB"...
0x17ef  ldc.i4.5
0x17f0  newarr   [mscorlib]System.Object
0x17f5  dup
0x17f6  ldc.i4.0
0x17f7  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x17fc  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x1801  box      [mscorlib]System.Int32
0x1806  stelem.ref
0x1807  dup
0x1808  ldc.i4.1
0x1809  ldloc.1
0x180a  box      [mscorlib]System.Int32
0x180f  stelem.ref
0x1810  dup
0x1811  ldc.i4.2
0x1812  ldarg.0
0x1813  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1818  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x181d  box      [mscorlib]System.Int32
0x1822  stelem.ref
0x1823  dup
0x1824  ldc.i4.3
0x1825  ldloc.2
0x1826  callvirt instance valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State()
0x182b  box      Microsoft.Crm.Sandbox.BucketState
0x1830  stelem.ref
0x1831  dup
0x1832  ldc.i4.4
0x1833  ldarg.0
0x1834  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1839  box      [mscorlib]System.Guid
0x183e  stelem.ref
0x183f  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1844  ldloc.2
0x1845  ldc.i4.3
0x1846  callvirt instance void Microsoft.Crm.Sandbox.OrganizationWorkerBucket::set_State(valuetype Microsoft.Crm.Sandbox.BucketState value)
0x184b  ldloc.0
0x184c  ldc.i4.1
0x184d  add
0x184e  stloc.0
0x184f  ldloc.0
0x1850  ldarg.0
0x1851  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1856  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x185b  blt      loc_17B7
0x1860  ret
```
