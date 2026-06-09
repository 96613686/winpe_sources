# Microsoft.Crm.Statistics.StatisticsService::SaveStatistic

- ea: `0x27c0`
- end: `0x2ad1`
- name: `Microsoft.Crm.Statistics.StatisticsService::SaveStatistic`
- size: `785`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x25b0`

## callees

- `0x2310`
- `0x2380`
- `0x27c0`
- `0x66530`
- `0x66ae0`
- `0x66b00`
- `0x67140`
- `0x67450`
- `0x674c0`

## string_xrefs

- `0x284f`: `D:\a\1\s\src\ManagedPlatform\Server\Statistics\StatisticsService.cs`
- `0x2963`: `D:\a\1\s\src\ManagedPlatform\Server\Statistics\StatisticsService.cs`
- `0x2a51`: `D:\a\1\s\src\ManagedPlatform\Server\Statistics\StatisticsService.cs`
- `0x2971`: `OrganizationStatistic created (server={0}, statisticType={1}, hour={2}, value={3})`
- `0x29c0`: `update OrganizationStatisticBase set StatisticValue = StatisticValue + @value where (ServerName = @ServerName and Hour = @ThisHour and StatisticType = @StatisticType)`
- `0x2a5f`: `OrganizationStatistic updated (server={0}, statisticType={1}, hour={2}, value={3})`

## pseudocode

```c

```

## disassembly

```asm
0x27c0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x27c5  stloc.0
0x27c6  ldarg.3
0x27c7  ldc.i4.0
0x27c8  ldc.i4.0
0x27c9  newobj   instance void Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid organizationId, [opt] bool isReader, [opt] valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority priority)
0x27ce  stloc.1
0x27cf  ldloc.1
0x27d0  ldc.i4.1
0x27d1  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool startTransaction)
0x27d6  ldstr    aSelectCountFro// "select count(*) from OrganizationStatis"...
0x27db  stloc.2
0x27dc  ldc.i4.0
0x27dd  stloc.3
0x27de  ldloc.1
0x27df  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x27e4  ldloc.2
0x27e5  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x27ea  stloc.s  4
0x27ec  ldloc.s  4
0x27ee  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x27f3  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x27f8  dup
0x27f9  ldstr    aServername_0// "@ServerName"
0x27fe  call     string [mscorlib]System.Environment::get_MachineName()
0x2803  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2808  pop
0x2809  dup
0x280a  ldstr    aThishour// "@ThisHour"
0x280f  ldarg.1
0x2810  box      [mscorlib]System.Int32
0x2815  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x281a  pop
0x281b  ldstr    aStatistictype// "@StatisticType"
0x2820  ldarg.2
0x2821  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.OperationalMetricsType Microsoft.Crm.Statistics.StatisticsArray::get_MetricsType()
0x2826  box      [mscorlib]System.Int32
0x282b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2830  pop
0x2831  ldloc.s  4
0x2833  ldloc.1
0x2834  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x2839  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_SqlTransaction()
0x283e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::SetTransaction(class [System.Data]System.Data.IDbCommand, class [System.Data]System.Data.IDbTransaction)
0x2843  ldloc.s  4
0x2845  ldc.i4   0x109
0x284a  ldstr    aSavestatistic// "SaveStatistic"
0x284f  ldstr    aDA1SSrcManaged// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x2854  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x2859  unbox.any [mscorlib]System.Int32
0x285e  stloc.3
0x285f  ldloc.3
0x2860  ldc.i4.1
0x2861  cgt
0x2863  ldc.i4.0
0x2864  ceq
0x2866  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x286b  ldstr    aTooManyRowsExi// "Too many rows exist for the given (stat"...
0x2870  ldc.i4.4
0x2871  newarr   [mscorlib]System.Object
0x2876  dup
0x2877  ldc.i4.0
0x2878  ldarg.2
0x2879  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.OperationalMetricsType Microsoft.Crm.Statistics.StatisticsArray::get_MetricsType()
0x287e  box      [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.OperationalMetricsType
0x2883  stelem.ref
0x2884  dup
0x2885  ldc.i4.1
0x2886  call     string [mscorlib]System.Environment::get_MachineName()
0x288b  stelem.ref
0x288c  dup
0x288d  ldc.i4.2
0x288e  ldarg.1
0x288f  box      [mscorlib]System.Int32
0x2894  stelem.ref
0x2895  dup
0x2896  ldc.i4.3
0x2897  ldloc.3
0x2898  box      [mscorlib]System.Int32
0x289d  stelem.ref
0x289e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x28a3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x28a8  leave.s  loc_28B6
0x28aa  ldloc.s  4
0x28ac  brfalse.s loc_28B5
0x28ae  ldloc.s  4
0x28b0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x28b5  endfinally
0x28b6  ldloc.3
0x28b7  brtrue   loc_29C0
0x28bc  ldstr    aInsertIntoOrga// "insert into OrganizationStatisticBase(O"...
0x28c1  stloc.s  5
0x28c3  ldloc.1
0x28c4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x28c9  ldloc.s  5
0x28cb  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x28d0  stloc.s  6
0x28d2  ldloc.s  6
0x28d4  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x28d9  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x28de  dup
0x28df  ldstr    aOrganizationst_1// "@OrganizationStatisticId"
0x28e4  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x28e9  box      [mscorlib]System.Guid
0x28ee  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x28f3  pop
0x28f4  dup
0x28f5  ldstr    aStatisticvalue// "@StatisticValue"
0x28fa  ldarg.2
0x28fb  ldarg.1
0x28fc  callvirt instance int32 Microsoft.Crm.Statistics.StatisticsArray::get_Item(int32 index)
0x2901  box      [mscorlib]System.Int32
0x2906  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x290b  pop
0x290c  dup
0x290d  ldstr    aServername_0// "@ServerName"
0x2912  call     string [mscorlib]System.Environment::get_MachineName()
0x2917  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x291c  pop
0x291d  dup
0x291e  ldstr    aHour// "@Hour"
0x2923  ldarg.1
0x2924  box      [mscorlib]System.Int32
0x2929  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x292e  pop
0x292f  ldstr    aStatistictype// "@StatisticType"
0x2934  ldarg.2
0x2935  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.OperationalMetricsType Microsoft.Crm.Statistics.StatisticsArray::get_MetricsType()
0x293a  box      [mscorlib]System.Int32
0x293f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2944  pop
0x2945  ldloc.s  6
0x2947  ldloc.1
0x2948  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x294d  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_SqlTransaction()
0x2952  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::SetTransaction(class [System.Data]System.Data.IDbCommand, class [System.Data]System.Data.IDbTransaction)
0x2957  ldloc.s  6
0x2959  ldc.i4   0x11F
0x295e  ldstr    aSavestatistic// "SaveStatistic"
0x2963  ldstr    aDA1SSrcManaged// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x2968  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x296d  pop
0x296e  ldarg.3
0x296f  ldc.i4.s 0x14
0x2971  ldstr    aOrganizationst_2// "OrganizationStatistic created (server={"...
0x2976  ldc.i4.4
0x2977  newarr   [mscorlib]System.Object
0x297c  dup
0x297d  ldc.i4.0
0x297e  call     string [mscorlib]System.Environment::get_MachineName()
0x2983  stelem.ref
0x2984  dup
0x2985  ldc.i4.1
0x2986  ldarg.2
0x2987  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.OperationalMetricsType Microsoft.Crm.Statistics.StatisticsArray::get_MetricsType()
0x298c  box      [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.OperationalMetricsType
0x2991  stelem.ref
0x2992  dup
0x2993  ldc.i4.2
0x2994  ldarg.1
0x2995  box      [mscorlib]System.Int32
0x299a  stelem.ref
0x299b  dup
0x299c  ldc.i4.3
0x299d  ldarg.2
0x299e  ldarg.1
0x299f  callvirt instance int32 Microsoft.Crm.Statistics.StatisticsArray::get_Item(int32 index)
0x29a4  box      [mscorlib]System.Int32
0x29a9  stelem.ref
0x29aa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x29af  leave    loc_2AAB
0x29b4  ldloc.s  6
0x29b6  brfalse.s loc_29BF
0x29b8  ldloc.s  6
0x29ba  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x29bf  endfinally
0x29c0  ldstr    aUpdateOrganiza// "update OrganizationStatisticBase set St"...
0x29c5  stloc.s  7
0x29c7  ldloc.1
0x29c8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x29cd  ldloc.s  7
0x29cf  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x29d4  stloc.s  8
0x29d6  ldloc.s  8
0x29d8  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x29dd  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x29e2  dup
0x29e3  ldstr    aServername_0// "@ServerName"
0x29e8  call     string [mscorlib]System.Environment::get_MachineName()
0x29ed  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x29f2  pop
0x29f3  dup
0x29f4  ldstr    aValue// "@value"
0x29f9  ldarg.2
0x29fa  ldarg.1
0x29fb  callvirt instance int32 Microsoft.Crm.Statistics.StatisticsArray::get_Item(int32 index)
0x2a00  box      [mscorlib]System.Int32
0x2a05  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2a0a  pop
0x2a0b  dup
0x2a0c  ldstr    aThishour// "@ThisHour"
0x2a11  ldarg.1
0x2a12  box      [mscorlib]System.Int32
0x2a17  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2a1c  pop
0x2a1d  ldstr    aStatistictype// "@StatisticType"
0x2a22  ldarg.2
0x2a23  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.OperationalMetricsType Microsoft.Crm.Statistics.StatisticsArray::get_MetricsType()
0x2a28  box      [mscorlib]System.Int32
0x2a2d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2a32  pop
0x2a33  ldloc.s  8
0x2a35  ldloc.1
0x2a36  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x2a3b  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_SqlTransaction()
0x2a40  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::SetTransaction(class [System.Data]System.Data.IDbCommand, class [System.Data]System.Data.IDbTransaction)
0x2a45  ldloc.s  8
0x2a47  ldc.i4   0x133
0x2a4c  ldstr    aSavestatistic// "SaveStatistic"
0x2a51  ldstr    aDA1SSrcManaged// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x2a56  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x2a5b  pop
0x2a5c  ldarg.3
0x2a5d  ldc.i4.s 0x14
0x2a5f  ldstr    aOrganizationst_3// "OrganizationStatistic updated (server={"...
0x2a64  ldc.i4.4
0x2a65  newarr   [mscorlib]System.Object
0x2a6a  dup
0x2a6b  ldc.i4.0
0x2a6c  call     string [mscorlib]System.Environment::get_MachineName()
0x2a71  stelem.ref
0x2a72  dup
0x2a73  ldc.i4.1
0x2a74  ldarg.2
0x2a75  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.OperationalMetricsType Microsoft.Crm.Statistics.StatisticsArray::get_MetricsType()
0x2a7a  box      [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.OperationalMetricsType
0x2a7f  stelem.ref
0x2a80  dup
0x2a81  ldc.i4.2
0x2a82  ldarg.1
0x2a83  box      [mscorlib]System.Int32
0x2a88  stelem.ref
0x2a89  dup
0x2a8a  ldc.i4.3
0x2a8b  ldarg.2
0x2a8c  ldarg.1
0x2a8d  callvirt instance int32 Microsoft.Crm.Statistics.StatisticsArray::get_Item(int32 index)
0x2a92  box      [mscorlib]System.Int32
0x2a97  stelem.ref
0x2a98  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2a9d  leave.s  loc_2AAB
0x2a9f  ldloc.s  8
0x2aa1  brfalse.s loc_2AAA
0x2aa3  ldloc.s  8
0x2aa5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2aaa  endfinally
0x2aab  ldloc.1
0x2aac  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x2ab1  leave.s  loc_2AD0
0x2ab3  pop
0x2ab4  ldloc.1
0x2ab5  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x2aba  rethrow
0x2abc  ldloc.1
0x2abd  brfalse.s loc_2AC5
0x2abf  ldloc.1
0x2ac0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ac5  endfinally
0x2ac6  ldloc.0
0x2ac7  brfalse.s loc_2ACF
0x2ac9  ldloc.0
0x2aca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2acf  endfinally
0x2ad0  ret
```
