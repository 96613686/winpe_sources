# Microsoft.Crm.Asynchronous.IndexManagementOperation::InternalExecute

- ea: `0x38e0`
- end: `0x3b22`
- name: `Microsoft.Crm.Asynchronous.IndexManagementOperation::InternalExecute`
- size: `578`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x38e0`
- `0x3b30`

## string_xrefs

- `0x399d`: `IndexManagementServiceExecutionTimeoutInMinutes`
- `0x3a30`: `  Completed Execution: DoIndexManagement`

## pseudocode

```c

```

## disassembly

```asm
0x38e0  ldarg.1
0x38e1  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x38e6  ldc.i4.s 0xF
0x38e8  ceq
0x38ea  ldstr    aOperationTypeM_11// "Operation type must be 'IndexManagement"...
0x38ef  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x38f4  ldarg.0
0x38f5  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x38fa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x38ff  stloc.0
0x3900  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x3905  stloc.1
0x3906  ldloc.0
0x3907  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0x390c  ldc.i4.0
0x390d  ldc.i4.0
0x390e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x3913  ldloc.0
0x3914  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection, valuetype [mscorlib]System.Guid)
0x3919  stloc.2
0x391a  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::get_Instance()
0x391f  ldarg.1
0x3920  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x3925  ldstr    aIndexmanagemen// "IndexManagementOperation.InternalExecut"...
0x392a  ldstr    aSqlconenctionS// "SQLConenction State: "
0x392f  ldloc.2
0x3930  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x3935  callvirt instance valuetype [System.Data]System.Data.ConnectionState [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_State()
0x393a  box      [System.Data]System.Data.ConnectionState
0x393f  call     string [mscorlib]System.String::Concat(object, object)
0x3944  ldc.i4.m1
0x3945  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::IndexManagementServiceInformation(valuetype [mscorlib]System.Guid, string, string, int32)
0x394a  ldloc.2
0x394b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3950  castclass [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext
0x3955  ldc.i4.0
0x3956  ldc.i4.0
0x3957  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x395c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnBeginRequest(bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext, valuetype [mscorlib]System.Guid)
0x3961  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::get_Instance()
0x3966  ldloc.0
0x3967  ldstr    aIndexmanagemen_0// "IndexManagementOperation.InternalExecut"...
0x396c  ldstr    aSqlconenctionS// "SQLConenction State: "
0x3971  ldloc.2
0x3972  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x3977  callvirt instance valuetype [System.Data]System.Data.ConnectionState [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_State()
0x397c  box      [System.Data]System.Data.ConnectionState
0x3981  ldstr    aStartedExecuti// "  Started Executing: DoIndexManagement."
0x3986  call     string [mscorlib]System.String::Concat(object, object, object)
0x398b  ldc.i4.m1
0x398c  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::IndexManagementServiceInformation(valuetype [mscorlib]System.Guid, string, string, int32)
0x3991  ldloc.1
0x3992  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x3997  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x399c  ldloc.0
0x399d  ldstr    aIndexmanagemen_1// "IndexManagementServiceExecutionTimeoutI"...
0x39a2  ldc.i4   0x95
0x39a7  ldstr    aInternalexecut// "InternalExecute"
0x39ac  ldstr    aDDbsShDccm2110_3// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0x39b1  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x39b6  dup
0x39b7  brtrue.s loc_39C1
0x39b9  pop
0x39ba  ldc.i4.s 0x78
0x39bc  box      [mscorlib]System.Int32
0x39c1  unbox.any [mscorlib]System.Int32
0x39c6  ldc.i4.s 0x3C
0x39c8  mul
0x39c9  ldc.i4   0x3E8
0x39ce  mul
0x39cf  stloc.3
0x39d0  ldarg.0
0x39d1  ldloc.2
0x39d2  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.Crm.Asynchronous.IndexManagementOperation::DoIndexManagementAsync(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext sqlContext)
0x39d7  stloc.s  4
0x39d9  ldc.i4.2
0x39da  newarr   [mscorlib]System.Threading.Tasks.Task
0x39df  dup
0x39e0  ldc.i4.0
0x39e1  ldloc.s  4
0x39e3  stelem.ref
0x39e4  dup
0x39e5  ldc.i4.1
0x39e6  ldloc.3
0x39e7  call     class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.Task::Delay(int32)
0x39ec  stelem.ref
0x39ed  call     class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Threading.Tasks.Task> [mscorlib]System.Threading.Tasks.Task::WhenAny(class [mscorlib]System.Threading.Tasks.Task[])
0x39f2  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Threading.Tasks.Task>::GetAwaiter()
0x39f7  stloc.s  5
0x39f9  ldloca.s 5
0x39fb  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Threading.Tasks.Task>::GetResult()
0x3a00  ldloc.s  4
0x3a02  bne.un.s loc_3A51
0x3a04  ldloc.2
0x3a05  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x3a0a  ldloc.1
0x3a0b  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x3a10  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::get_Instance()
0x3a15  ldloc.0
0x3a16  ldstr    aIndexmanagemen_0// "IndexManagementOperation.InternalExecut"...
0x3a1b  ldstr    aSqlconenctionS// "SQLConenction State: "
0x3a20  ldloc.2
0x3a21  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x3a26  callvirt instance valuetype [System.Data]System.Data.ConnectionState [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_State()
0x3a2b  box      [System.Data]System.Data.ConnectionState
0x3a30  ldstr    aCompletedExecu// "  Completed Execution: DoIndexManagemen"...
0x3a35  call     string [mscorlib]System.String::Concat(object, object, object)
0x3a3a  ldloc.1
0x3a3b  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x3a40  stloc.s  6
0x3a42  ldloca.s 6
0x3a44  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x3a49  conv.i4
0x3a4a  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::IndexManagementServiceInformation(valuetype [mscorlib]System.Guid, string, string, int32)
0x3a4f  br.s     loc_3A9C
0x3a51  ldloc.2
0x3a52  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x3a57  ldloc.1
0x3a58  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x3a5d  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::get_Instance()
0x3a62  ldloc.0
0x3a63  ldstr    aIndexmanagemen_0// "IndexManagementOperation.InternalExecut"...
0x3a68  ldstr    aSqlconenctionS// "SQLConenction State: "
0x3a6d  ldloc.2
0x3a6e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x3a73  callvirt instance valuetype [System.Data]System.Data.ConnectionState [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_State()
0x3a78  box      [System.Data]System.Data.ConnectionState
0x3a7d  ldstr    aTimedoutExecut// "  Timedout Execution: DoIndexManagement"
0x3a82  call     string [mscorlib]System.String::Concat(object, object, object)
0x3a87  ldloc.1
0x3a88  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x3a8d  stloc.s  6
0x3a8f  ldloca.s 6
0x3a91  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x3a96  conv.i4
0x3a97  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::IndexManagementServiceInformation(valuetype [mscorlib]System.Guid, string, string, int32)
0x3a9c  leave.s  loc_3B1C
0x3a9e  stloc.s  7
0x3aa0  ldloc.2
0x3aa1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x3aa6  ldloc.1
0x3aa7  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x3aac  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::get_Instance()
0x3ab1  ldloc.0
0x3ab2  ldstr    aIndexmanagemen_0// "IndexManagementOperation.InternalExecut"...
0x3ab7  ldc.i4.4
0x3ab8  newarr   [mscorlib]System.Object
0x3abd  dup
0x3abe  ldc.i4.0
0x3abf  ldstr    aSqlconenctionS// "SQLConenction State: "
0x3ac4  stelem.ref
0x3ac5  dup
0x3ac6  ldc.i4.1
0x3ac7  ldloc.2
0x3ac8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x3acd  callvirt instance valuetype [System.Data]System.Data.ConnectionState [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_State()
0x3ad2  box      [System.Data]System.Data.ConnectionState
0x3ad7  stelem.ref
0x3ad8  dup
0x3ad9  ldc.i4.2
0x3ada  ldstr    aExceptionMessa// "  Exception Message: "
0x3adf  stelem.ref
0x3ae0  dup
0x3ae1  ldc.i4.3
0x3ae2  ldloc.s  7
0x3ae4  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3ae9  stelem.ref
0x3aea  call     string [mscorlib]System.String::Concat(object[])
0x3aef  ldloc.1
0x3af0  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x3af5  stloc.s  6
0x3af7  ldloca.s 6
0x3af9  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x3afe  conv.i4
0x3aff  ldloc.s  7
0x3b01  callvirt instance string [mscorlib]System.Object::ToString()
0x3b06  call     string [mscorlib]System.Environment::get_StackTrace()
0x3b0b  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::IndexManagementServiceError(valuetype [mscorlib]System.Guid, string, string, int32, string, string)
0x3b10  rethrow
0x3b12  ldloc.2
0x3b13  brfalse.s loc_3B1B
0x3b15  ldloc.2
0x3b16  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3b1b  endfinally
0x3b1c  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0x3b21  ret
```
