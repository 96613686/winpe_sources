# Microsoft.Crm.Sandbox.OrganizationWorkerList::ScaleDownIfNeeded

- ea: `0x1670`
- end: `0x17a5`
- name: `Microsoft.Crm.Sandbox.OrganizationWorkerList::ScaleDownIfNeeded`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x12b0`

## callees

- `0x1670`
- `0x17b0`

## string_xrefs

- `0x1678`: `OrganizationWorkerList.ScaleDownIfNeeded:Thread[{0:d4}] Checking if scale down is needed. OrgId: {1}`
- `0x1723`: `OrganizationWorkerList.ScaleDownIfNeeded:Thread[{0:d4}] Scaling down org {1}. Current ready buckets {2} from a total of {3} buckets.`

## pseudocode

```c

```

## disassembly

```asm
0x1670  ldarg.0
0x1671  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1676  ldc.i4.s 0x21
0x1678  ldstr    aOrganizationwo_13// "OrganizationWorkerList.ScaleDownIfNeede"...
0x167d  ldc.i4.2
0x167e  newarr   [mscorlib]System.Object
0x1683  dup
0x1684  ldc.i4.0
0x1685  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x168a  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x168f  box      [mscorlib]System.Int32
0x1694  stelem.ref
0x1695  dup
0x1696  ldc.i4.1
0x1697  ldarg.0
0x1698  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x169d  box      [mscorlib]System.Guid
0x16a2  stelem.ref
0x16a3  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x16a8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x16ad  ldarg.0
0x16ae  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.OrganizationWorkerList::_lastScaleDown
0x16b3  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x16b8  ldarg.0
0x16b9  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Sandbox.OrganizationWorkerList::_scaleDownEvalInterval
0x16be  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x16c3  brfalse  loc_17A4
0x16c8  ldarg.0
0x16c9  ldfld    object Microsoft.Crm.Sandbox.OrganizationWorkerList::_scaleDownLock
0x16ce  stloc.0
0x16cf  ldc.i4.0
0x16d0  stloc.1
0x16d1  ldloc.0
0x16d2  ldloca.s 1
0x16d4  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x16d9  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x16de  ldarg.0
0x16df  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.OrganizationWorkerList::_lastScaleDown
0x16e4  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x16e9  ldarg.0
0x16ea  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Sandbox.OrganizationWorkerList::_scaleDownEvalInterval
0x16ef  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x16f4  brfalse  loc_1798
0x16f9  ldarg.0
0x16fa  ldfld    int64 Microsoft.Crm.Sandbox.OrganizationWorkerList::_workersReadyCount
0x16ff  brfalse.s loc_1710
0x1701  ldarg.0
0x1702  ldfld    int64 Microsoft.Crm.Sandbox.OrganizationWorkerList::_workersConcurrentCount
0x1707  ldarg.0
0x1708  ldfld    int64 Microsoft.Crm.Sandbox.OrganizationWorkerList::_workersReadyCount
0x170d  div
0x170e  br.s     loc_1712
0x1710  ldc.i4.0
0x1711  conv.i8
0x1712  ldarg.0
0x1713  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_minConcurrentRequests
0x1718  conv.i8
0x1719  bge.s    loc_177A
0x171b  ldarg.0
0x171c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1721  ldc.i4.s 0x21
0x1723  ldstr    aOrganizationwo_14// "OrganizationWorkerList.ScaleDownIfNeede"...
0x1728  ldc.i4.4
0x1729  newarr   [mscorlib]System.Object
0x172e  dup
0x172f  ldc.i4.0
0x1730  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1735  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x173a  box      [mscorlib]System.Int32
0x173f  stelem.ref
0x1740  dup
0x1741  ldc.i4.1
0x1742  ldarg.0
0x1743  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1748  box      [mscorlib]System.Guid
0x174d  stelem.ref
0x174e  dup
0x174f  ldc.i4.2
0x1750  ldarg.0
0x1751  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_orgReadyBucketsCount
0x1756  box      [mscorlib]System.Int32
0x175b  stelem.ref
0x175c  dup
0x175d  ldc.i4.3
0x175e  ldarg.0
0x175f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1764  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::get_Count()
0x1769  box      [mscorlib]System.Int32
0x176e  stelem.ref
0x176f  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1774  ldarg.0
0x1775  call     instance void Microsoft.Crm.Sandbox.OrganizationWorkerList::InvalidateReadyBucket()
0x177a  leave.s  loc_17A4
0x177c  ldarg.0
0x177d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1782  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.OrganizationWorkerList::_lastScaleDown
0x1787  ldarg.0
0x1788  ldc.i4.0
0x1789  conv.i8
0x178a  stfld    int64 Microsoft.Crm.Sandbox.OrganizationWorkerList::_workersConcurrentCount
0x178f  ldarg.0
0x1790  ldc.i4.0
0x1791  conv.i8
0x1792  stfld    int64 Microsoft.Crm.Sandbox.OrganizationWorkerList::_workersReadyCount
0x1797  endfinally
0x1798  leave.s  loc_17A4
0x179a  ldloc.1
0x179b  brfalse.s loc_17A3
0x179d  ldloc.0
0x179e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x17a3  endfinally
0x17a4  ret
```
