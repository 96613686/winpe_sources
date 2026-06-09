# Microsoft.Crm.TableEntity::DeleteStaleMatchCodeRecords

- ea: `0x2790`
- end: `0x2912`
- name: `Microsoft.Crm.TableEntity::DeleteStaleMatchCodeRecords`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x2560`

## callees

- `0x640`
- `0x2520`
- `0x2790`
- `0xaf40`
- `0xaf50`

## string_xrefs

- `0x28a6`: `@numOfRecordsToBeDeleted`
- `0x27b3`: `DeleteStaleMatchCodeRecords`
- `0x27b8`: `D:\a\1\s\src\ManagedPlatform\SDK\DeletionService\TableEntity.cs`
- `0x2809`: `DeletionService: MatchCode table {0} does not exist. Skipping Deletion from this table.`
- `0x2829`: `DeletionService: MatchCode table {0} does not exist. Skipping Deletion from this table.`
- `0x2824`: `TableEntity.DeleteStaleMatchCodeRecords`
- `0x2868`: `DELETE TOP(@numOfRecordsToBeDeleted) FROM {0} WHERE ObjectId IN (SELECT ObjectId FROM SubscriptionTrackingDeletedObject WHERE ObjectTypeCode = {1});`
- `0x28cf`: `DeletionService: Deletion Service deleted {0} rows in {1} seconds from {2}. Completed all Deletes : {3}`

## pseudocode

```c

```

## disassembly

```asm
0x2790  ldc.i4.m1
0x2791  stloc.0
0x2792  ldc.i4.0
0x2793  stloc.1
0x2794  ldstr    aIfExistsSelect// "\r\n\t\t\t\tif exists (select 1 from sy"...
0x2799  ldarg.2
0x279a  call     string [mscorlib]System.String::Format(string, object)
0x279f  stloc.2
0x27a0  ldarg.1
0x27a1  ldloc.2
0x27a2  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x27a7  stloc.s  4
0x27a9  ldc.i4.0
0x27aa  stloc.s  5
0x27ac  ldloc.s  4
0x27ae  ldc.i4   0x83
0x27b3  ldstr    aDeletestalemat// "DeleteStaleMatchCodeRecords"
0x27b8  ldstr    aDA1SSrcManaged_0// "D:\\a\\1\\s\\src\\ManagedPlatform\\SDK"...
0x27bd  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x27c2  stloc.s  6
0x27c4  ldloc.s  6
0x27c6  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x27cb  brtrue.s loc_27DE
0x27cd  ldc.i4   0x80040216
0x27d2  ldc.i4.0
0x27d3  newarr   [mscorlib]System.Object
0x27d8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x27dd  throw
0x27de  ldloc.s  6
0x27e0  ldstr    aMatchcodetable// "MatchCodeTableExists"
0x27e5  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x27ea  unbox.any [mscorlib]System.Int32
0x27ef  stloc.s  5
0x27f1  leave.s  loc_27FF
0x27f3  ldloc.s  6
0x27f5  brfalse.s loc_27FE
0x27f7  ldloc.s  6
0x27f9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27fe  endfinally
0x27ff  ldloc.s  5
0x2801  brtrue.s loc_2855
0x2803  ldc.i4.1
0x2804  stloc.1
0x2805  ldarg.s  4
0x2807  ldc.i4.s 0x14
0x2809  ldstr    aDeletionservic_61// "DeletionService: MatchCode table {0} do"...
0x280e  ldc.i4.1
0x280f  newarr   [mscorlib]System.Object
0x2814  dup
0x2815  ldc.i4.0
0x2816  ldarg.2
0x2817  stelem.ref
0x2818  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x281d  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x2822  ldarg.s  4
0x2824  ldstr    aTableentityDel// "TableEntity.DeleteStaleMatchCodeRecords"
0x2829  ldstr    aDeletionservic_61// "DeletionService: MatchCode table {0} do"...
0x282e  ldarg.2
0x282f  call     string [mscorlib]System.String::Format(string, object)
0x2834  ldc.i4.m1
0x2835  ldloc.0
0x2836  ldc.i4.0
0x2837  ldloc.s  4
0x2839  callvirt instance int32 [System.Data]System.Data.IDbCommand::get_CommandTimeout()
0x283e  ldc.i4.m1
0x283f  ldc.i4.m1
0x2840  ldloc.1
0x2841  ldloc.s  4
0x2843  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x2848  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x284d  ldloc.1
0x284e  stloc.s  7
0x2850  leave    loc_290F
0x2855  leave.s  loc_2863
0x2857  ldloc.s  4
0x2859  brfalse.s loc_2862
0x285b  ldloc.s  4
0x285d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2862  endfinally
0x2863  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2868  ldstr    aDeleteTopNumof_6// "DELETE TOP(@numOfRecordsToBeDeleted) FR"...
0x286d  ldc.i4.2
0x286e  newarr   [mscorlib]System.Object
0x2873  dup
0x2874  ldc.i4.0
0x2875  ldarg.2
0x2876  stelem.ref
0x2877  dup
0x2878  ldc.i4.1
0x2879  ldarg.0
0x287a  call     instance int32 Microsoft.Crm.TableEntity::get_ObjectTypeCode()
0x287f  box      [mscorlib]System.Int32
0x2884  stelem.ref
0x2885  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x288a  stloc.3
0x288b  ldarg.1
0x288c  ldloc.3
0x288d  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x2892  stloc.s  8
0x2894  ldloc.s  8
0x2896  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x289b  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x28a0  dup
0x28a1  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x28a6  ldstr    aNumofrecordsto// "@numOfRecordsToBeDeleted"
0x28ab  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x28b0  box      [mscorlib]System.Int32
0x28b5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x28ba  pop
0x28bb  ldarg.3
0x28bc  ldloc.s  8
0x28be  ldarg.s  4
0x28c0  ldloca.s 0
0x28c2  ldloca.s 1
0x28c4  call     int32 Microsoft.Crm.DeletionService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid orgId, [out] int32& durationInSecs, [out] bool& completedAllDelete)
0x28c9  stloc.s  9
0x28cb  ldarg.s  4
0x28cd  ldc.i4.s 0x14
0x28cf  ldstr    aDeletionservic_62// "DeletionService: Deletion Service delet"...
0x28d4  ldc.i4.4
0x28d5  newarr   [mscorlib]System.Object
0x28da  dup
0x28db  ldc.i4.0
0x28dc  ldloc.s  9
0x28de  box      [mscorlib]System.Int32
0x28e3  stelem.ref
0x28e4  dup
0x28e5  ldc.i4.1
0x28e6  ldloc.0
0x28e7  box      [mscorlib]System.Int32
0x28ec  stelem.ref
0x28ed  dup
0x28ee  ldc.i4.2
0x28ef  ldarg.2
0x28f0  stelem.ref
0x28f1  dup
0x28f2  ldc.i4.3
0x28f3  ldloc.1
0x28f4  box      [mscorlib]System.Boolean
0x28f9  stelem.ref
0x28fa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x28ff  leave.s  loc_290D
0x2901  ldloc.s  8
0x2903  brfalse.s loc_290C
0x2905  ldloc.s  8
0x2907  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x290c  endfinally
0x290d  ldloc.1
0x290e  ret
0x290f  ldloc.s  7
0x2911  ret
```
