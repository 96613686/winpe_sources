# Microsoft.Crm.Asynchronous.RefreshPrincipalObjectAccessReadSnapshotOperation::InternalExecute

- ea: `0x5990`
- end: `0x5ba8`
- name: `Microsoft.Crm.Asynchronous.RefreshPrincipalObjectAccessReadSnapshotOperation::InternalExecute`
- size: `536`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x5990`

## string_xrefs

- `0x599a`: `Operation type must be 'RefreshReadSharingSnapshots'`
- `0x59d6`: `InternalExecute:RegenerateReadSharingSnapshotData`
- `0x5a15`: `InternalExecute:RegenerateReadSharingSnapshotData`
- `0x59db`: `Starting Execution: RegenerateReadSharingSnapshotData.`
- `0x5a1a`: `Completed Execution: RegenerateReadSharingSnapshotData.`
- `0x5a49`: `SELECT ObjectTypeCode, COUNT(PrincipalObjectAccessId) AS ReadShareCount\n											  FROM PrincipalObjectAccess POA \n											  WHERE ((POA.AccessRightsMask | POA.InheritedAccessRightsMask) &1) = 1 \n											  GROUP BY ObjectTypeCode `
- `0x5a5c`: `d:\dbs\sh\dccm2\1101_190851\cmd\5\src\Core\ObjectModel\Async\Handlers\System\RefreshPrincipalObjectAccessReadSnapshotOperation.cs`
- `0x5ab0`: `ReadShareCount`
- `0x5abe`: `ReadShareCount`
- `0x5adb`: `ReadShareCount`

## pseudocode

```c

```

## disassembly

```asm
0x5990  ldarg.1
0x5991  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x5996  ldc.i4.s 0x2F
0x5998  ceq
0x599a  ldstr    aOperationTypeM_15// "Operation type must be 'RefreshReadShar"...
0x599f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x59a4  ldarg.0
0x59a5  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x59aa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x59af  stloc.0
0x59b0  ldloc.0
0x59b1  ldc.i4   0x258
0x59b6  ldc.i4.0
0x59b7  ldc.i4.0
0x59b8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x59bd  ldloc.0
0x59be  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection, valuetype [mscorlib]System.Guid)
0x59c3  stloc.1
0x59c4  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x59c9  stloc.2
0x59ca  ldloc.2
0x59cb  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x59d0  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::get_Instance()
0x59d5  ldloc.0
0x59d6  ldstr    aInternalexecut_0// "InternalExecute:RegenerateReadSharingSn"...
0x59db  ldstr    aStartingExecut// "Starting Execution: RegenerateReadShari"...
0x59e0  ldc.i4.m1
0x59e1  ldsfld   string [mscorlib]System.String::Empty
0x59e6  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::PoarsInformation(valuetype [mscorlib]System.Guid, string, string, int32, string)
0x59eb  ldloc.1
0x59ec  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x59f1  stloc.3
0x59f2  ldloc.3
0x59f3  castclass [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext
0x59f8  ldc.i4.1
0x59f9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnBeginRequest(bool)
0x59fe  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotService::.ctor()
0x5a03  ldloc.1
0x5a04  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotService::RegenerateReadSharingSnapshotData(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5a09  ldloc.2
0x5a0a  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x5a0f  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::get_Instance()
0x5a14  ldloc.0
0x5a15  ldstr    aInternalexecut_0// "InternalExecute:RegenerateReadSharingSn"...
0x5a1a  ldstr    aCompletedExecu_4// "Completed Execution: RegenerateReadShar"...
0x5a1f  ldloc.2
0x5a20  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x5a25  stloc.s  6
0x5a27  ldloca.s 6
0x5a29  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x5a2e  conv.i4
0x5a2f  ldsfld   string [mscorlib]System.String::Empty
0x5a34  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::PoarsInformation(valuetype [mscorlib]System.Guid, string, string, int32, string)
0x5a39  ldc.i4.m1
0x5a3a  stloc.s  4
0x5a3c  ldc.i4.m1
0x5a3d  stloc.s  5
0x5a3f  ldloc.3
0x5a40  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand()
0x5a45  stloc.s  7
0x5a47  ldloc.s  7
0x5a49  ldstr    aSelectObjectty// "SELECT ObjectTypeCode, COUNT(PrincipalO"...
0x5a4e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x5a53  ldloc.s  7
0x5a55  ldc.i4.s 0x3E
0x5a57  ldstr    aInternalexecut// "InternalExecute"
0x5a5c  ldstr    aDDbsShDccm2110_6// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0x5a61  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x5a66  stloc.s  8
0x5a68  br       loc_5B29
0x5a6d  ldloc.s  8
0x5a6f  ldstr    aObjecttypecode// "ObjectTypeCode"
0x5a74  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x5a79  brfalse.s loc_5AAB
0x5a7b  ldloc.s  8
0x5a7d  ldstr    aObjecttypecode// "ObjectTypeCode"
0x5a82  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x5a87  callvirt instance string [mscorlib]System.Object::ToString()
0x5a8c  ldsfld   string [mscorlib]System.String::Empty
0x5a91  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5a96  brtrue.s loc_5AAB
0x5a98  ldloc.s  8
0x5a9a  ldstr    aObjecttypecode// "ObjectTypeCode"
0x5a9f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x5aa4  unbox.any [mscorlib]System.Int32
0x5aa9  br.s     loc_5AAC
0x5aab  ldc.i4.m1
0x5aac  stloc.s  4
0x5aae  ldloc.s  8
0x5ab0  ldstr    aReadsharecount// "ReadShareCount"
0x5ab5  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x5aba  brfalse.s loc_5AEC
0x5abc  ldloc.s  8
0x5abe  ldstr    aReadsharecount// "ReadShareCount"
0x5ac3  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x5ac8  callvirt instance string [mscorlib]System.Object::ToString()
0x5acd  ldsfld   string [mscorlib]System.String::Empty
0x5ad2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5ad7  brtrue.s loc_5AEC
0x5ad9  ldloc.s  8
0x5adb  ldstr    aReadsharecount// "ReadShareCount"
0x5ae0  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x5ae5  unbox.any [mscorlib]System.Int32
0x5aea  br.s     loc_5AED
0x5aec  ldc.i4.m1
0x5aed  stloc.s  5
0x5aef  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContextFactory::get_Current()
0x5af4  ldloc.0
0x5af5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory::GetOrganizationContext(valuetype [mscorlib]System.Guid)
0x5afa  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5aff  ldloc.s  4
0x5b01  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0x5b06  stloc.s  9
0x5b08  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrincipalObjectAccessEventSource [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrincipalObjectAccessEventSource::get_Instance()
0x5b0d  ldloc.0
0x5b0e  ldloc.s  4
0x5b10  ldloc.s  9
0x5b12  brfalse.s loc_5B1D
0x5b14  ldloc.s  9
0x5b16  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x5b1b  br.s     loc_5B22
0x5b1d  ldsfld   string [mscorlib]System.String::Empty
0x5b22  ldloc.s  5
0x5b24  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrincipalObjectAccessEventSource::LogPrincipalObjectAccessCount(valuetype [mscorlib]System.Guid, int32, string, int32)
0x5b29  ldloc.s  8
0x5b2b  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x5b30  brtrue   loc_5A6D
0x5b35  leave.s  loc_5B43
0x5b37  ldloc.s  8
0x5b39  brfalse.s loc_5B42
0x5b3b  ldloc.s  8
0x5b3d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b42  endfinally
0x5b43  leave.s  loc_5B51
0x5b45  ldloc.s  7
0x5b47  brfalse.s loc_5B50
0x5b49  ldloc.s  7
0x5b4b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b50  endfinally
0x5b51  ldloc.3
0x5b52  castclass [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext
0x5b57  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnEndRequest()
0x5b5c  leave.s  loc_5BA0
0x5b5e  stloc.s  0xA
0x5b60  ldloc.3
0x5b61  castclass [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext
0x5b66  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnErrorRequest()
0x5b6b  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::get_Instance()
0x5b70  ldloc.0
0x5b71  ldstr    aInternalexecut// "InternalExecute"
0x5b76  ldloc.s  0xA
0x5b78  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5b7d  ldc.i4.m1
0x5b7e  ldloc.s  0xA
0x5b80  callvirt instance string [mscorlib]System.Object::ToString()
0x5b85  call     string [mscorlib]System.Environment::get_StackTrace()
0x5b8a  ldsfld   string [mscorlib]System.String::Empty
0x5b8f  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::PoarsError(valuetype [mscorlib]System.Guid, string, string, int32, string, string, string)
0x5b94  rethrow
0x5b96  ldloc.1
0x5b97  brfalse.s loc_5B9F
0x5b99  ldloc.1
0x5b9a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b9f  endfinally
0x5ba0  ldc.i4.s 0x1E
0x5ba2  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRemoveEventResult::.ctor(int32)
0x5ba7  ret
```
