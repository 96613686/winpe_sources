# Microsoft.Crm.Asynchronous.CleanupSolutionComponentsOperation::InternalExecute

- ea: `0xa30`
- end: `0xb4b`
- name: `Microsoft.Crm.Asynchronous.CleanupSolutionComponentsOperation::InternalExecute`
- size: `283`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xa30`

## string_xrefs

- `0xa38`: `Attempting to Cleanup Solution Components for org {0}`
- `0xad8`: `Cleanup of Solution Components for org {0} failedl`
- `0xb20`: `Cleanup of Solution Components for org {0} was successful`

## pseudocode

```c

```

## disassembly

```asm
0xa30  ldarg.1
0xa31  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xa36  ldc.i4.s 0x15
0xa38  ldstr    aAttemptingToCl// "Attempting to Cleanup Solution Componen"...
0xa3d  ldc.i4.1
0xa3e  newarr   [mscorlib]System.Object
0xa43  dup
0xa44  ldc.i4.0
0xa45  ldarg.0
0xa46  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xa4b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xa50  box      [mscorlib]System.Guid
0xa55  stelem.ref
0xa56  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa5b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0xa60  stloc.0
0xa61  ldarg.1
0xa62  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xa67  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0xa6c  ldc.i4.0
0xa6d  ldc.i4.0
0xa6e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xa73  ldarg.1
0xa74  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xa79  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection, valuetype [mscorlib]System.Guid)
0xa7e  stloc.1
0xa7f  ldloc.1
0xa80  ldc.i4.0
0xa81  ldc.i4.0
0xa82  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0xa87  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnBeginRequest(bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext, valuetype [mscorlib]System.Guid)
0xa8c  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentService::.ctor()
0xa91  dup
0xa92  ldloc.1
0xa93  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xa98  ldloc.1
0xa99  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::get_SolutionId()
0xa9e  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentService::CleanupSolutionComponentEntries(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xaa3  dup
0xaa4  ldloc.1
0xaa5  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentService::CleanupNonExistingSolutionReferences(class [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext)
0xaaa  dup
0xaab  ldloc.1
0xaac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xab1  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentService::CleanupUnPublishedMetadataLocalizedLabels(valuetype [mscorlib]System.Guid)
0xab6  ldloc.1
0xab7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xabc  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentService::CleanupOrphanWorkflows(valuetype [mscorlib]System.Guid)
0xac1  ldloc.1
0xac2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnEndRequest()
0xac7  leave.s  loc_B18
0xac9  stloc.2
0xaca  ldloc.1
0xacb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnErrorRequest()
0xad0  ldarg.1
0xad1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xad6  ldc.i4.s 0x15
0xad8  ldstr    aCleanupOfSolut// "Cleanup of Solution Components for org "...
0xadd  ldc.i4.1
0xade  newarr   [mscorlib]System.Object
0xae3  dup
0xae4  ldc.i4.0
0xae5  ldarg.0
0xae6  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xaeb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xaf0  box      [mscorlib]System.Guid
0xaf5  stelem.ref
0xaf6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xafb  ldloc.2
0xafc  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0xb01  stloc.3
0xb02  leave.s  loc_B49
0xb04  ldloc.1
0xb05  brfalse.s loc_B0D
0xb07  ldloc.1
0xb08  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb0d  endfinally
0xb0e  ldloc.0
0xb0f  brfalse.s loc_B17
0xb11  ldloc.0
0xb12  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb17  endfinally
0xb18  ldarg.1
0xb19  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xb1e  ldc.i4.s 0x15
0xb20  ldstr    aCleanupOfSolut_0// "Cleanup of Solution Components for org "...
0xb25  ldc.i4.1
0xb26  newarr   [mscorlib]System.Object
0xb2b  dup
0xb2c  ldc.i4.0
0xb2d  ldarg.0
0xb2e  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xb33  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xb38  box      [mscorlib]System.Guid
0xb3d  stelem.ref
0xb3e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb43  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0xb48  ret
0xb49  ldloc.3
0xb4a  ret
```
