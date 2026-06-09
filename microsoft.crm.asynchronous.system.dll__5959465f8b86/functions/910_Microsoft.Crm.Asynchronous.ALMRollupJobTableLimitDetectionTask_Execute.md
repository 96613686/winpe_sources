# Microsoft.Crm.Asynchronous.ALMRollupJobTableLimitDetectionTask::Execute

- ea: `0x910`
- end: `0x9e8`
- name: `Microsoft.Crm.Asynchronous.ALMRollupJobTableLimitDetectionTask::Execute`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x220`
- `0x230`
- `0x4f0`
- `0x910`
- `0x9f0`
- `0xa00`
- `0xe160`

## string_xrefs

- `0x91e`: `ALM Rollup Job Table Limit task started for Org {0}`
- `0x9a8`: `ALM Rollup Job Table Limit task completed for Org {0}`

## pseudocode

```c

```

## disassembly

```asm
0x910  newobj   instance void <>c__DisplayClass2_0::.ctor()
0x915  stloc.0
0x916  ldarg.0
0x917  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::get_OrganizationId()
0x91c  ldc.i4.s 0x15
0x91e  ldstr    aAlmRollupJobTa// "ALM Rollup Job Table Limit task started"...
0x923  ldc.i4.1
0x924  newarr   [mscorlib]System.Object
0x929  dup
0x92a  ldc.i4.0
0x92b  ldarg.0
0x92c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::get_OrganizationId()
0x931  box      [mscorlib]System.Guid
0x936  stelem.ref
0x937  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x93c  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::DefaultInstance
0x941  ldarg.0
0x942  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::get_OrganizationId()
0x947  ldc.i4.1
0x948  ldc.i4.0
0x949  ldc.i4.0
0x94a  ldnull
0x94b  ldc.i4.0
0x94c  ldc.i4.0
0x94d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::Get(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ConnectionAccessType, int32, string, bool, int32)
0x952  stloc.1
0x953  ldloc.0
0x954  ldc.i4.0
0x955  stfld    int32 <>c__DisplayClass2_0::rollupRecordCount
0x95a  ldloc.1
0x95b  ldarg.0
0x95c  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo Microsoft.Crm.Asynchronous.ALMRollupJobTableLimitDetectionTask::GetRecordCountCommand()
0x961  ldloc.0
0x962  ldftn    instance void <>c__DisplayClass2_0::<Execute>b__0(class [System.Data]System.Data.IDataReader r)
0x968  newobj   instance void class [mscorlib]System.Action`1<class [System.Data]System.Data.IDataReader>::.ctor(object, native int)
0x96d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess::ExecuteReaderAction(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, class [mscorlib]System.Action`1<class [System.Data]System.Data.IDataReader>)
0x972  ldloc.0
0x973  ldc.i4.0
0x974  stfld    int32 <>c__DisplayClass2_0::rollupFieldCount
0x979  ldloc.0
0x97a  ldfld    int32 <>c__DisplayClass2_0::rollupRecordCount
0x97f  conv.i8
0x980  ldarg.0
0x981  ldfld    int64 Microsoft.Crm.Asynchronous.ALMRollupJobTableLimitDetectionTask::RollupJobBaseThreshold
0x986  ble.s    loc_9A0
0x988  ldloc.1
0x989  ldarg.0
0x98a  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo Microsoft.Crm.Asynchronous.ALMRollupJobTableLimitDetectionTask::GetRollupFieldInfoCommand()
0x98f  ldloc.0
0x990  ldftn    instance void <>c__DisplayClass2_0::<Execute>b__1(class [System.Data]System.Data.IDataReader r)
0x996  newobj   instance void class [mscorlib]System.Action`1<class [System.Data]System.Data.IDataReader>::.ctor(object, native int)
0x99b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess::ExecuteReaderAction(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, class [mscorlib]System.Action`1<class [System.Data]System.Data.IDataReader>)
0x9a0  ldarg.0
0x9a1  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::get_OrganizationId()
0x9a6  ldc.i4.s 0x15
0x9a8  ldstr    aAlmRollupJobTa_0// "ALM Rollup Job Table Limit task complet"...
0x9ad  ldc.i4.1
0x9ae  newarr   [mscorlib]System.Object
0x9b3  dup
0x9b4  ldc.i4.0
0x9b5  ldarg.0
0x9b6  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::get_OrganizationId()
0x9bb  box      [mscorlib]System.Guid
0x9c0  stelem.ref
0x9c1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9c6  call     class Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTelemetryEvent Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTelemetryEvent::get_Instance()
0x9cb  ldarg.0
0x9cc  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::get_OrganizationId()
0x9d1  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x9d6  ldloc.0
0x9d7  ldfld    int32 <>c__DisplayClass2_0::rollupRecordCount
0x9dc  ldloc.0
0x9dd  ldfld    int32 <>c__DisplayClass2_0::rollupFieldCount
0x9e2  callvirt instance void Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTelemetryEvent::ALMRollupJobLimitDetectionCompleted(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, int32 rollupJobBaseRecordCount, int32 rollupFieldCount)
0x9e7  ret
```
