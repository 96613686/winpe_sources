# <>c__DisplayClass5_0::<Run>b__0

- ea: `0xa95c0`
- end: `0xa9810`
- name: `<>c__DisplayClass5_0::<Run>b__0`
- size: `592`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x2e0`
- `0x370`
- `0x920`
- `0x2500`
- `0x2520`
- `0x2680`
- `0xaf40`
- `0xaf50`
- `0xa95c0`

## string_xrefs

- `0xa95cd`: `DeletionService: Started Deletion Service for Org:{0}, NumOfRecordsToBeDeletedPerExecution:{1}, DeletionServiceExecutionTimeoutInMinutes:{2}, DeletionServiceDBConnectionTimeoutInSeconds:{3}`
- `0xa962c`: `DeletionService: Started Deletion Service`
- `0xa9659`: `MSCRMDeletionService`
- `0xa96bb`: `DeletionService: Error encounted when retrieving tables`
- `0xa96f3`: `DeletionService: Initializing Table {0} for ObjectTypeCode {1}`
- `0xa9768`: `DeletionService: Deletion Service encountered an internal error while executing Deletion operation.`
- `0xa97a5`: `DeletionService: Exiting Deletion Service for Org:{0}`
- `0xa97dd`: `DeletionService: Exiting Deletion Service`

## pseudocode

```c

```

## disassembly

```asm
0xa95c0  ldarg.0
0xa95c1  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass5_0::<>4__this
0xa95c6  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa95cb  ldc.i4.s 0x14
0xa95cd  ldstr    aDeletionservic_63// "DeletionService: Started Deletion Servi"...
0xa95d2  ldc.i4.4
0xa95d3  newarr   [mscorlib]System.Object
0xa95d8  dup
0xa95d9  ldc.i4.0
0xa95da  ldarg.0
0xa95db  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass5_0::<>4__this
0xa95e0  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa95e5  box      [mscorlib]System.Guid
0xa95ea  stelem.ref
0xa95eb  dup
0xa95ec  ldc.i4.1
0xa95ed  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xa95f2  box      [mscorlib]System.Int32
0xa95f7  stelem.ref
0xa95f8  dup
0xa95f9  ldc.i4.2
0xa95fa  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xa95ff  box      [mscorlib]System.Int32
0xa9604  stelem.ref
0xa9605  dup
0xa9606  ldc.i4.3
0xa9607  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xa960c  box      [mscorlib]System.Int32
0xa9611  stelem.ref
0xa9612  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa9617  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0xa961c  ldarg.0
0xa961d  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass5_0::<>4__this
0xa9622  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa9627  ldstr    aRun// "Run"
0xa962c  ldstr    aDeletionservic_64// "DeletionService: Started Deletion Servi"...
0xa9631  ldc.i4.0
0xa9632  ldc.i4.m1
0xa9633  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0xa9638  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xa963d  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xa9642  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xa9647  ldc.i4.0
0xa9648  ldsfld   string [mscorlib]System.String::Empty
0xa964d  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0xa9652  newobj   instance void [System]System.Diagnostics.EventLog::.ctor()
0xa9657  stloc.0
0xa9658  ldloc.0
0xa9659  ldstr    aMscrmdeletions// "MSCRMDeletionService"
0xa965e  callvirt instance void [System]System.Diagnostics.EventLog::set_Source(string)
0xa9663  ldarg.0
0xa9664  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass5_0::<>4__this
0xa9669  ldloc.0
0xa966a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor(class [System]System.Diagnostics.EventLog)
0xa966f  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog Microsoft.Crm.DeletionService::_eventLog
0xa9674  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0xa9679  stloc.1
0xa967a  ldloc.1
0xa967b  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0xa9680  ldarg.0
0xa9681  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass5_0::<>4__this
0xa9686  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa968b  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xa9690  ldc.i4.0
0xa9691  ldc.i4.0
0xa9692  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xa9697  stloc.2
0xa9698  ldloc.2
0xa9699  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xa969e  ldarg.0
0xa969f  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass5_0::<>4__this
0xa96a4  ldloc.2
0xa96a5  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.TableEntity> Microsoft.Crm.DeletionService::GetTablesForDelete(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection)
0xa96aa  stloc.3
0xa96ab  leave.s  loc_A96D3
0xa96ad  stloc.s  4
0xa96af  ldarg.0
0xa96b0  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass5_0::<>4__this
0xa96b5  ldc.i4   0xC000400A
0xa96ba  conv.u8
0xa96bb  ldstr    aDeletionservic_65// "DeletionService: Error encounted when r"...
0xa96c0  ldloc.s  4
0xa96c2  callvirt instance string [mscorlib]System.Object::ToString()
0xa96c7  ldsfld   string [mscorlib]System.String::Empty
0xa96cc  call     instance void Microsoft.Crm.DeletionService::LogCrmTraceAndEventLog(int64 logId, string crmTraceMessage, string errorMessage, string sqlText)
0xa96d1  rethrow
0xa96d3  ldloc.3
0xa96d4  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.TableEntity>::GetEnumerator()
0xa96d9  stloc.s  5
0xa96db  br.s     loc_A9724
0xa96dd  ldloca.s 5
0xa96df  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.TableEntity>::get_Current()
0xa96e4  stloc.s  6
0xa96e6  ldarg.0
0xa96e7  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass5_0::<>4__this
0xa96ec  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa96f1  ldc.i4.s 0x14
0xa96f3  ldstr    aDeletionservic_66// "DeletionService: Initializing Table {0}"...
0xa96f8  ldc.i4.2
0xa96f9  newarr   [mscorlib]System.Object
0xa96fe  dup
0xa96ff  ldc.i4.0
0xa9700  ldloc.s  6
0xa9702  callvirt instance string Microsoft.Crm.TableEntity::get_BaseTableName()
0xa9707  stelem.ref
0xa9708  dup
0xa9709  ldc.i4.1
0xa970a  ldloc.s  6
0xa970c  callvirt instance int32 Microsoft.Crm.TableEntity::get_ObjectTypeCode()
0xa9711  box      [mscorlib]System.Int32
0xa9716  stelem.ref
0xa9717  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa971c  ldloc.s  6
0xa971e  ldloc.2
0xa971f  callvirt instance void Microsoft.Crm.TableEntity::Init(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection)
0xa9724  ldloca.s 5
0xa9726  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.TableEntity>::MoveNext()
0xa972b  brtrue.s loc_A96DD
0xa972d  leave.s  loc_A973D
0xa972f  ldloca.s 5
0xa9731  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.TableEntity>
0xa9737  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa973c  endfinally
0xa973d  ldloc.2
0xa973e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0xa9743  ldarg.0
0xa9744  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass5_0::<>4__this
0xa9749  ldloc.3
0xa974a  ldarg.0
0xa974b  ldfld    class Microsoft.Crm.IDeletionServiceProvider <>c__DisplayClass5_0::deletionServiceProvider
0xa9750  call     instance void Microsoft.Crm.DeletionService::RunDeletionTasks(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.TableEntity> tableList, class Microsoft.Crm.IDeletionServiceProvider deletionServiceProvider)
0xa9755  leave    loc_A980F
0xa975a  stloc.s  7
0xa975c  ldarg.0
0xa975d  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass5_0::<>4__this
0xa9762  ldc.i4   0xC0004007
0xa9767  conv.u8
0xa9768  ldstr    aDeletionservic_67// "DeletionService: Deletion Service encou"...
0xa976d  ldloc.s  7
0xa976f  callvirt instance string [mscorlib]System.Object::ToString()
0xa9774  ldsfld   string [mscorlib]System.String::Empty
0xa9779  call     instance void Microsoft.Crm.DeletionService::LogCrmTraceAndEventLog(int64 logId, string crmTraceMessage, string errorMessage, string sqlText)
0xa977e  rethrow
0xa9780  ldloc.1
0xa9781  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xa9786  ldloc.1
0xa9787  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0xa978c  stloc.s  9
0xa978e  ldloca.s 9
0xa9790  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0xa9795  conv.i4
0xa9796  stloc.s  8
0xa9798  ldarg.0
0xa9799  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass5_0::<>4__this
0xa979e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa97a3  ldc.i4.s 0x14
0xa97a5  ldstr    aDeletionservic_68// "DeletionService: Exiting Deletion Servi"...
0xa97aa  ldc.i4.1
0xa97ab  newarr   [mscorlib]System.Object
0xa97b0  dup
0xa97b1  ldc.i4.0
0xa97b2  ldarg.0
0xa97b3  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass5_0::<>4__this
0xa97b8  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa97bd  box      [mscorlib]System.Guid
0xa97c2  stelem.ref
0xa97c3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa97c8  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0xa97cd  ldarg.0
0xa97ce  ldfld    class Microsoft.Crm.DeletionService <>c__DisplayClass5_0::<>4__this
0xa97d3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xa97d8  ldstr    aRun// "Run"
0xa97dd  ldstr    aDeletionservic_69// "DeletionService: Exiting Deletion Servi"...
0xa97e2  ldc.i4.0
0xa97e3  ldloc.s  8
0xa97e5  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0xa97ea  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xa97ef  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xa97f4  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xa97f9  ldc.i4.0
0xa97fa  ldsfld   string [mscorlib]System.String::Empty
0xa97ff  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0xa9804  endfinally
0xa9805  ldloc.2
0xa9806  brfalse.s loc_A980E
0xa9808  ldloc.2
0xa9809  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa980e  endfinally
0xa980f  ret
```
