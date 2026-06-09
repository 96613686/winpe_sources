# Microsoft.Crm.DeletionService::<CleanUpSubscriptionTrackingDeletedObjects>b__26_0

- ea: `0x1600`
- end: `0x19c7`
- name: `Microsoft.Crm.DeletionService::<CleanUpSubscriptionTrackingDeletedObjects>b__26_0`
- size: `967`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x640`
- `0xb00`
- `0x1600`
- `0xaf40`
- `0xaf50`

## string_xrefs

- `0x1697`: `D:\a\1\s\src\ManagedPlatform\SDK\DeletionService\DeletionService.cs`
- `0x189f`: `@numOfRecordsToBeDeleted`
- `0x1608`: `DeletionService: Inside DeletionService.CleanUpSubscriptionTrackingDeletedObjects`
- `0x1628`: `DeletionService: Inside DeletionService.CleanUpSubscriptionTrackingDeletedObjects`
- `0x1623`: `CleanUpSubscriptionTrackingDeletedObjects`
- `0x1692`: `CleanUpSubscriptionTrackingDeletedObjects`
- `0x16f1`: `CleanUpSubscriptionTrackingDeletedObjects`
- `0x175e`: `CleanUpSubscriptionTrackingDeletedObjects`
- `0x17fd`: `CleanUpSubscriptionTrackingDeletedObjects`
- `0x1677`: `SELECT coalesce(min(CompletedSyncVersionNumber), @@dbts) FROM Subscription`
- `0x16c4`: `DeletionService: CleanUpSubscriptionTrackingDeletedObjects : minVersionNumberExpired={0}, subscriptionVersionNumberExpired={1}`
- `0x16f6`: `DeletionService: CleanUpSubscriptionTrackingDeletedObjects : minVersionNumberExpired={0}, subscriptionVersionNumberExpired={1}`
- `0x173a`: `DeletionService: Exiting CleanUpSubscriptionTrackingDeletedObjects since minVersionNumberExpired={0}`
- `0x1763`: `DeletionService: Exiting CleanUpSubscriptionTrackingDeletedObjects since minVersionNumberExpired={0}`
- `0x17b4`: `DeletionService: Skipping delete for table SubscriptionTrackingDeletedObject since there are pending records in the table that are referenced by table {0} {1}`
- `0x1802`: `DeletionService: Skipping delete for table SubscriptionTrackingDeletedObject since there are pending records in the table that are referenced by table {0} {1}`
- `0x17e7`: `PrincipalObjectAccess`
- `0x182a`: `PrincipalObjectAccess`
- `0x1877`: `DELETE TOP(@numOfRecordsToBeDeleted) FROM SubscriptionTrackingDeletedObject WHERE TimeStamp <= convert(timestamp, @versionNumberExpired)`
- `0x18d0`: `SubscriptionTrackingDeletedObjects`
- `0x1968`: `SubscriptionTrackingDeletedObjects`
- `0x18d5`: `DeletionService: Before cleaning CleanUpSubscriptionTrackingDeletedObjects table whose TimeStamp <= {0}`
- `0x1926`: `DeletionService: Deletion Service deleted {0} rows in {1} seconds from SubscriptionTrackingDeletedObjects where TimeStamp<={2}. Completed all Deletes : {3}`
- `0x196d`: `DeletionService: Execution of CleanUpSubscriptionTrackingDeletedObjects is completed, whose whose TimeStamp <= {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1600  ldarg.0
0x1601  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1606  ldc.i4.s 0x14
0x1608  ldstr    aDeletionservic_30// "DeletionService: Inside DeletionService"...
0x160d  ldc.i4.0
0x160e  newarr   [mscorlib]System.Object
0x1613  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1618  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x161d  ldarg.0
0x161e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1623  ldstr    aCleanupsubscri// "CleanUpSubscriptionTrackingDeletedObjec"...
0x1628  ldstr    aDeletionservic_30// "DeletionService: Inside DeletionService"...
0x162d  ldc.i4.0
0x162e  ldc.i4.0
0x162f  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x1634  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1639  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x163e  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1643  ldc.i4.0
0x1644  ldsfld   string [mscorlib]System.String::Empty
0x1649  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x164e  ldarg.0
0x164f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1654  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1659  ldc.i4.0
0x165a  ldc.i4.0
0x165b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1660  stloc.0
0x1661  ldloc.0
0x1662  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1667  ldc.i4.0
0x1668  conv.i8
0x1669  stloc.1
0x166a  ldloc.0
0x166b  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1670  stloc.3
0x1671  ldloc.3
0x1672  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1677  ldstr    aSelectCoalesce// "SELECT coalesce(min(CompletedSyncVersio"...
0x167c  ldc.i4.0
0x167d  newarr   [mscorlib]System.Object
0x1682  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1687  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x168c  ldloc.3
0x168d  ldc.i4   0x33B
0x1692  ldstr    aCleanupsubscri// "CleanUpSubscriptionTrackingDeletedObjec"...
0x1697  ldstr    aDA1SSrcManaged// "D:\\a\\1\\s\\src\\ManagedPlatform\\SDK"...
0x169c  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x16a1  unbox.any [mscorlib]System.Int64
0x16a6  stloc.1
0x16a7  leave.s  loc_16B3
0x16a9  ldloc.3
0x16aa  brfalse.s loc_16B2
0x16ac  ldloc.3
0x16ad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16b2  endfinally
0x16b3  ldarg.0
0x16b4  ldloc.0
0x16b5  ldloc.1
0x16b6  call     instance int64 Microsoft.Crm.DeletionService::GetChangeTrackingExpiredVersion(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection, int64 subscriptionVersionNumberExpired)
0x16bb  stloc.2
0x16bc  ldarg.0
0x16bd  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x16c2  ldc.i4.s 0x14
0x16c4  ldstr    aDeletionservic_31// "DeletionService: CleanUpSubscriptionTra"...
0x16c9  ldc.i4.2
0x16ca  newarr   [mscorlib]System.Object
0x16cf  dup
0x16d0  ldc.i4.0
0x16d1  ldloc.2
0x16d2  box      [mscorlib]System.Int64
0x16d7  stelem.ref
0x16d8  dup
0x16d9  ldc.i4.1
0x16da  ldloc.1
0x16db  box      [mscorlib]System.Int64
0x16e0  stelem.ref
0x16e1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x16e6  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x16eb  ldarg.0
0x16ec  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x16f1  ldstr    aCleanupsubscri// "CleanUpSubscriptionTrackingDeletedObjec"...
0x16f6  ldstr    aDeletionservic_31// "DeletionService: CleanUpSubscriptionTra"...
0x16fb  ldloc.2
0x16fc  box      [mscorlib]System.Int64
0x1701  ldloc.1
0x1702  box      [mscorlib]System.Int64
0x1707  call     string [mscorlib]System.String::Format(string, object, object)
0x170c  ldc.i4.0
0x170d  ldc.i4.m1
0x170e  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x1713  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1718  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x171d  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1722  ldc.i4.0
0x1723  ldsfld   string [mscorlib]System.String::Empty
0x1728  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x172d  ldloc.2
0x172e  ldc.i4.m1
0x172f  conv.i8
0x1730  bne.un.s loc_1799
0x1732  ldarg.0
0x1733  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1738  ldc.i4.s 0x14
0x173a  ldstr    aDeletionservic_32// "DeletionService: Exiting CleanUpSubscri"...
0x173f  ldc.i4.1
0x1740  newarr   [mscorlib]System.Object
0x1745  dup
0x1746  ldc.i4.0
0x1747  ldloc.2
0x1748  box      [mscorlib]System.Int64
0x174d  stelem.ref
0x174e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1753  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x1758  ldarg.0
0x1759  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x175e  ldstr    aCleanupsubscri// "CleanUpSubscriptionTrackingDeletedObjec"...
0x1763  ldstr    aDeletionservic_32// "DeletionService: Exiting CleanUpSubscri"...
0x1768  ldloc.2
0x1769  box      [mscorlib]System.Int64
0x176e  call     string [mscorlib]System.String::Format(string, object)
0x1773  ldc.i4.0
0x1774  ldc.i4.m1
0x1775  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x177a  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x177f  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x1784  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1789  ldc.i4.0
0x178a  ldsfld   string [mscorlib]System.String::Empty
0x178f  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x1794  leave    loc_19C6
0x1799  ldarg.0
0x179a  ldfld    bool Microsoft.Crm.DeletionService::_verifyStaleMatchCodeRecordsDeleted
0x179f  brfalse.s loc_17AC
0x17a1  ldarg.0
0x17a2  ldfld    bool Microsoft.Crm.DeletionService::_verifyStalePOARecordsDeleted
0x17a7  brtrue   loc_185A
0x17ac  ldarg.0
0x17ad  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x17b2  ldc.i4.s 0x14
0x17b4  ldstr    aDeletionservic_33// "DeletionService: Skipping delete for ta"...
0x17b9  ldc.i4.2
0x17ba  newarr   [mscorlib]System.Object
0x17bf  dup
0x17c0  ldc.i4.0
0x17c1  ldarg.0
0x17c2  ldfld    bool Microsoft.Crm.DeletionService::_verifyStaleMatchCodeRecordsDeleted
0x17c7  brfalse.s loc_17D0
0x17c9  ldsfld   string [mscorlib]System.String::Empty
0x17ce  br.s     loc_17D5
0x17d0  ldstr    aMatchcode// "MatchCode<>"
0x17d5  stelem.ref
0x17d6  dup
0x17d7  ldc.i4.1
0x17d8  ldarg.0
0x17d9  ldfld    bool Microsoft.Crm.DeletionService::_verifyStalePOARecordsDeleted
0x17de  brfalse.s loc_17E7
0x17e0  ldsfld   string [mscorlib]System.String::Empty
0x17e5  br.s     loc_17EC
0x17e7  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x17ec  stelem.ref
0x17ed  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x17f2  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x17f7  ldarg.0
0x17f8  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x17fd  ldstr    aCleanupsubscri// "CleanUpSubscriptionTrackingDeletedObjec"...
0x1802  ldstr    aDeletionservic_33// "DeletionService: Skipping delete for ta"...
0x1807  ldarg.0
0x1808  ldfld    bool Microsoft.Crm.DeletionService::_verifyStaleMatchCodeRecordsDeleted
0x180d  brfalse.s loc_1816
0x180f  ldsfld   string [mscorlib]System.String::Empty
0x1814  br.s     loc_181B
0x1816  ldstr    aMatchcode// "MatchCode<>"
0x181b  ldarg.0
0x181c  ldfld    bool Microsoft.Crm.DeletionService::_verifyStalePOARecordsDeleted
0x1821  brfalse.s loc_182A
0x1823  ldsfld   string [mscorlib]System.String::Empty
0x1828  br.s     loc_182F
0x182a  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x182f  call     string [mscorlib]System.String::Format(string, object, object)
0x1834  ldc.i4.0
0x1835  ldc.i4.m1
0x1836  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x183b  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1840  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x1845  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x184a  ldc.i4.0
0x184b  ldsfld   string [mscorlib]System.String::Empty
0x1850  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x1855  leave    loc_19C6
0x185a  ldloc.0
0x185b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x1860  stloc.s  4
0x1862  ldloc.0
0x1863  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1868  stloc.s  5
0x186a  ldc.i4.m1
0x186b  stloc.s  6
0x186d  ldc.i4.0
0x186e  stloc.s  7
0x1870  ldloc.s  5
0x1872  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1877  ldstr    aDeleteTopNumof_1// "DELETE TOP(@numOfRecordsToBeDeleted) FR"...
0x187c  ldc.i4.0
0x187d  newarr   [mscorlib]System.Object
0x1882  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1887  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x188c  ldloc.s  5
0x188e  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1893  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1898  dup
0x1899  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x189e  dup
0x189f  ldstr    aNumofrecordsto// "@numOfRecordsToBeDeleted"
0x18a4  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x18a9  box      [mscorlib]System.Int32
0x18ae  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x18b3  pop
0x18b4  ldstr    aVersionnumbere// "@versionNumberExpired"
0x18b9  ldloc.2
0x18ba  box      [mscorlib]System.Int64
0x18bf  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x18c4  pop
0x18c5  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x18ca  ldarg.0
0x18cb  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x18d0  ldstr    aSubscriptiontr// "SubscriptionTrackingDeletedObjects"
0x18d5  ldstr    aDeletionservic_34// "DeletionService: Before cleaning CleanU"...
0x18da  ldloc.2
0x18db  box      [mscorlib]System.Int64
0x18e0  call     string [mscorlib]System.String::Format(string, object)
0x18e5  ldc.i4.0
0x18e6  ldloc.s  6
0x18e8  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x18ed  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x18f2  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x18f7  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x18fc  ldc.i4.0
0x18fd  ldloc.s  5
0x18ff  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x1904  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x1909  ldloc.s  4
0x190b  ldloc.s  5
0x190d  ldarg.0
0x190e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1913  ldloca.s 6
0x1915  ldloca.s 7
0x1917  call     int32 Microsoft.Crm.DeletionService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid orgId, [out] int32& durationInSecs, [out] bool& completedAllDelete)
0x191c  stloc.s  8
0x191e  ldarg.0
0x191f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1924  ldc.i4.s 0x14
0x1926  ldstr    aDeletionservic_35// "DeletionService: Deletion Service delet"...
0x192b  ldc.i4.4
0x192c  newarr   [mscorlib]System.Object
0x1931  dup
0x1932  ldc.i4.0
0x1933  ldloc.s  8
0x1935  box      [mscorlib]System.Int32
0x193a  stelem.ref
0x193b  dup
0x193c  ldc.i4.1
0x193d  ldloc.s  6
0x193f  box      [mscorlib]System.Int32
0x1944  stelem.ref
0x1945  dup
0x1946  ldc.i4.2
0x1947  ldloc.2
0x1948  box      [mscorlib]System.Int64
0x194d  stelem.ref
0x194e  dup
0x194f  ldc.i4.3
0x1950  ldloc.s  7
0x1952  box      [mscorlib]System.Boolean
0x1957  stelem.ref
0x1958  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x195d  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x1962  ldarg.0
0x1963  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1968  ldstr    aSubscriptiontr// "SubscriptionTrackingDeletedObjects"
0x196d  ldstr    aDeletionservic_36// "DeletionService: Execution of CleanUpSu"...
0x1972  ldloc.2
0x1973  box      [mscorlib]System.Int64
0x1978  call     string [mscorlib]System.String::Format(string, object)
0x197d  ldloc.s  8
0x197f  ldloc.s  6
0x1981  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x1986  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x198b  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x1990  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1995  ldc.i4.1
0x1996  ldloc.s  5
0x1998  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x199d  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x19a2  leave.s  loc_19C6
0x19a4  ldloc.s  5
0x19a6  brfalse.s loc_19AF
0x19a8  ldloc.s  5
0x19aa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19af  endfinally
  ... truncated ...
```
