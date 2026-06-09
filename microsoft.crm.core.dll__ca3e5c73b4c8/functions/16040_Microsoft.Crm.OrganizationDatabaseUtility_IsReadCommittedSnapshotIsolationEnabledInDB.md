# Microsoft.Crm.OrganizationDatabaseUtility::IsReadCommittedSnapshotIsolationEnabledInDB

- ea: `0x16040`
- end: `0x160b1`
- name: `Microsoft.Crm.OrganizationDatabaseUtility::IsReadCommittedSnapshotIsolationEnabledInDB`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x16390`

## callees

- `0xd180`
- `0x11a10`
- `0x11be0`
- `0x11c80`
- `0x11d00`
- `0x16040`
- `0x160c0`
- `0x1eaa0`
- `0x1f510`

## string_xrefs

- `0x16069`: `ReadCommittedSnapshotIsolation`
- `0x16085`: `Getting ReadCommittedSnapshotIsolation state from DB failed: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x16040  ldc.i4.0
0x16041  stloc.0
0x16042  ldarg.0
0x16043  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.OrganizationDatabaseUtility::_organizationId
0x16048  ldc.i4.0
0x16049  ldc.i4.0
0x1604a  newobj   instance void Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid organizationId, [opt] bool isReader, [opt] valuetype Microsoft.Crm.ReadPriority priority)
0x1604f  ldarg.0
0x16050  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.OrganizationDatabaseUtility::_organizationId
0x16055  newobj   instance void Microsoft.Crm.SqlExecutionContext::.ctor(class Microsoft.Crm.CrmDbConnection connection, valuetype [mscorlib]System.Guid organizationId)
0x1605a  stloc.1
0x1605b  ldloc.1
0x1605c  ldc.i4.0
0x1605d  callvirt instance void Microsoft.Crm.SqlExecutionContext::OnBeginRequest(bool startTransaction)
0x16062  ldarg.0
0x16063  ldloc.1
0x16064  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.Crm.OrganizationDatabaseUtility::IsSnapshotIsolationAndRcsiEnabledInDb(class Microsoft.Crm.ISqlExecutionContext sqlContext)
0x16069  ldstr    aReadcommitteds_0// "ReadCommittedSnapshotIsolation"
0x1606e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::get_Item(void)
0x16073  stloc.0
0x16074  ldloc.1
0x16075  callvirt instance void Microsoft.Crm.SqlExecutionContext::OnEndRequest()
0x1607a  leave.s  loc_160A1
0x1607c  stloc.2
0x1607d  ldloc.2
0x1607e  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x16083  ldc.i4.s 0x14
0x16085  ldstr    aGettingReadcom// "Getting ReadCommittedSnapshotIsolation "...
0x1608a  ldc.i4.1
0x1608b  newarr   [mscorlib]System.Object
0x16090  dup
0x16091  ldc.i4.0
0x16092  ldloc.2
0x16093  stelem.ref
0x16094  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x16099  ldloc.1
0x1609a  callvirt instance void Microsoft.Crm.SqlExecutionContext::OnErrorRequest()
0x1609f  leave.s  loc_160A1
0x160a1  ldloc.0
0x160a2  stloc.3
0x160a3  leave.s  loc_160AF
0x160a5  ldloc.1
0x160a6  brfalse.s loc_160AE
0x160a8  ldloc.1
0x160a9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x160ae  endfinally
0x160af  ldloc.3
0x160b0  ret
```
