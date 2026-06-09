# Microsoft.Crm.OrganizationDatabaseUtility::SetReadCommittedSnapshotIsolation_0

- ea: `0x16390`
- end: `0x163f4`
- name: `Microsoft.Crm.OrganizationDatabaseUtility::SetReadCommittedSnapshotIsolation_0`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x16040`
- `0x16390`
- `0x16400`
- `0x1eaa0`
- `0x1f4b0`

## string_xrefs

- `0x1639d`: `Enabling Read Committed Snapshot Isolation for organization.  Id={0}`
- `0x163e3`: `RCSI is already enabled.`

## pseudocode

```c

```

## disassembly

```asm
0x16390  ldarg.0
0x16391  call     instance bool Microsoft.Crm.OrganizationDatabaseUtility::IsReadCommittedSnapshotIsolationEnabledInDB()
0x16396  brtrue.s loc_163DC
0x16398  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1639d  ldstr    aEnablingReadCo// "Enabling Read Committed Snapshot Isolat"...
0x163a2  ldc.i4.1
0x163a3  newarr   [mscorlib]System.Object
0x163a8  dup
0x163a9  ldc.i4.0
0x163aa  ldarg.0
0x163ab  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.OrganizationDatabaseUtility::_organizationId
0x163b0  box      [mscorlib]System.Guid
0x163b5  stelem.ref
0x163b6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x163bb  stloc.0
0x163bc  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x163c1  ldc.i4.s 0x14
0x163c3  ldloc.0
0x163c4  ldc.i4.0
0x163c5  newarr   [mscorlib]System.Object
0x163ca  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x163cf  ldarg.0
0x163d0  ldarg.0
0x163d1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.OrganizationDatabaseUtility::_organizationId
0x163d6  call     instance void Microsoft.Crm.OrganizationDatabaseUtility::SetReadCommittedSnapshotIsolationForDatabase(valuetype [mscorlib]System.Guid organizationId)
0x163db  ret
0x163dc  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x163e1  ldc.i4.s 0x14
0x163e3  ldstr    aRcsiIsAlreadyE// "RCSI is already enabled."
0x163e8  ldc.i4.0
0x163e9  newarr   [mscorlib]System.Object
0x163ee  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x163f3  ret
```
