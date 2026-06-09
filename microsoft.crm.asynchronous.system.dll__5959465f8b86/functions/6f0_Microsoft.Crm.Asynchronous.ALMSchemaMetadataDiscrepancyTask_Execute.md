# Microsoft.Crm.Asynchronous.ALMSchemaMetadataDiscrepancyTask::Execute

- ea: `0x6f0`
- end: `0x831`
- name: `Microsoft.Crm.Asynchronous.ALMSchemaMetadataDiscrepancyTask::Execute`
- size: `321`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x220`
- `0x280`
- `0x4f0`
- `0x6f0`

## string_xrefs

- `0x6f8`: `ALM Schema Metadata Discrepancy task started for Org {0}`
- `0x7af`: `ALM Schema Metadata Discrepancy task detected missing columns: {0}, missing tables: {1}, missing views: {2}, missing sprocs: {3} & duplicate labels:{4} for org: {5}`

## pseudocode

```c

```

## disassembly

```asm
0x6f0  ldarg.0
0x6f1  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::get_OrganizationId()
0x6f6  ldc.i4.s 0x15
0x6f8  ldstr    aAlmSchemaMetad// "ALM Schema Metadata Discrepancy task st"...
0x6fd  ldc.i4.1
0x6fe  newarr   [mscorlib]System.Object
0x703  dup
0x704  ldc.i4.0
0x705  ldarg.0
0x706  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::get_OrganizationId()
0x70b  box      [mscorlib]System.Guid
0x710  stelem.ref
0x711  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x716  ldarg.0
0x717  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::get_OrganizationId()
0x71c  ldc.i4.0
0x71d  ldc.i4.0
0x71e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x723  stloc.0
0x724  ldloc.0
0x725  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x72a  ldloc.0
0x72b  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x730  stloc.1
0x731  ldloc.1
0x732  ldsfld   string Microsoft.Crm.Asynchronous.ALMSchemaMetadataDiscrepancyTask::missingColumnInSchemaQuery
0x737  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x73c  ldloc.1
0x73d  callvirt instance object [System.Data]System.Data.IDbCommand::ExecuteScalar()
0x742  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x747  stloc.2
0x748  ldloc.1
0x749  ldsfld   string Microsoft.Crm.Asynchronous.ALMSchemaMetadataDiscrepancyTask::missingTablesInSchemaQuery
0x74e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x753  ldloc.1
0x754  callvirt instance object [System.Data]System.Data.IDbCommand::ExecuteScalar()
0x759  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x75e  stloc.3
0x75f  ldloc.1
0x760  ldsfld   string Microsoft.Crm.Asynchronous.ALMSchemaMetadataDiscrepancyTask::missingViewsInSchemaQuery
0x765  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x76a  ldloc.1
0x76b  callvirt instance object [System.Data]System.Data.IDbCommand::ExecuteScalar()
0x770  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x775  stloc.s  4
0x777  ldloc.1
0x778  ldsfld   string Microsoft.Crm.Asynchronous.ALMSchemaMetadataDiscrepancyTask::missingStoredProcsInSchemaQuery
0x77d  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x782  ldloc.1
0x783  callvirt instance object [System.Data]System.Data.IDbCommand::ExecuteScalar()
0x788  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x78d  stloc.s  5
0x78f  ldloc.1
0x790  ldsfld   string Microsoft.Crm.Asynchronous.ALMSchemaMetadataDiscrepancyTask::duplicateLabelsInSchemaQuery
0x795  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x79a  ldloc.1
0x79b  callvirt instance object [System.Data]System.Data.IDbCommand::ExecuteScalar()
0x7a0  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x7a5  stloc.s  6
0x7a7  ldarg.0
0x7a8  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::get_OrganizationId()
0x7ad  ldc.i4.s 0x15
0x7af  ldstr    aAlmSchemaMetad_0// "ALM Schema Metadata Discrepancy task de"...
0x7b4  ldc.i4.6
0x7b5  newarr   [mscorlib]System.Object
0x7ba  dup
0x7bb  ldc.i4.0
0x7bc  ldloc.2
0x7bd  box      [mscorlib]System.Int32
0x7c2  stelem.ref
0x7c3  dup
0x7c4  ldc.i4.1
0x7c5  ldloc.3
0x7c6  box      [mscorlib]System.Int32
0x7cb  stelem.ref
0x7cc  dup
0x7cd  ldc.i4.2
0x7ce  ldloc.s  4
0x7d0  box      [mscorlib]System.Int32
0x7d5  stelem.ref
0x7d6  dup
0x7d7  ldc.i4.3
0x7d8  ldloc.s  5
0x7da  box      [mscorlib]System.Int32
0x7df  stelem.ref
0x7e0  dup
0x7e1  ldc.i4.4
0x7e2  ldloc.s  6
0x7e4  box      [mscorlib]System.Int32
0x7e9  stelem.ref
0x7ea  dup
0x7eb  ldc.i4.5
0x7ec  ldarg.0
0x7ed  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::get_OrganizationId()
0x7f2  box      [mscorlib]System.Guid
0x7f7  stelem.ref
0x7f8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7fd  call     class Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTelemetryEvent Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTelemetryEvent::get_Instance()
0x802  ldarg.0
0x803  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::get_OrganizationId()
0x808  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x80d  ldloc.2
0x80e  ldloc.3
0x80f  ldloc.s  4
0x811  ldloc.s  5
0x813  ldloc.s  6
0x815  callvirt instance void Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTelemetryEvent::ALMSchemaMetadataDiscrepancyCompleted(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, int32 missingColumnInSchemaCount, int32 missingTablesInSchemaCount, int32 missingViewsInSchemaCount, int32 missingStoredProcsInSchemaCount, int32 duplicateLabelsCount)
0x81a  leave.s  loc_830
0x81c  ldloc.1
0x81d  brfalse.s loc_825
0x81f  ldloc.1
0x820  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x825  endfinally
0x826  ldloc.0
0x827  brfalse.s loc_82F
0x829  ldloc.0
0x82a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x82f  endfinally
0x830  ret
```
