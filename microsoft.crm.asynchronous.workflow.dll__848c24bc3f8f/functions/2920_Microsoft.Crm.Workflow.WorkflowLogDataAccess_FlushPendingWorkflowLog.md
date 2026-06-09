# Microsoft.Crm.Workflow.WorkflowLogDataAccess::FlushPendingWorkflowLog

- ea: `0x2920`
- end: `0x2a57`
- name: `Microsoft.Crm.Workflow.WorkflowLogDataAccess::FlushPendingWorkflowLog`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x2f30`

## callees

- `0x2920`
- `0x2a60`
- `0x2bd0`
- `0x2e50`
- `0x2e60`

## string_xrefs

- `0x2962`: `Exception while trying to open database connection for organization {0}`
- `0x2a11`: `d:\dbs\sh\dccm2\1101_190851\cmd\4\src\Core\ObjectModel\Async\Handlers\Workflow\WorkflowLogDataAccess.cs`

## pseudocode

```c

```

## disassembly

```asm
0x2920  ldarg.1
0x2921  callvirt instance int32 class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Workflow.WorkflowLogDescriptor>::get_Count()
0x2926  ldc.i4.0
0x2927  bgt.s    loc_292B
0x2929  ldc.i4.0
0x292a  ret
0x292b  ldarg.0
0x292c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x2931  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x2936  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x293b  ldstr    aWorkflowlog// "workflowlog"
0x2940  ldc.i4.1
0x2941  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x2946  stloc.0
0x2947  ldarg.0
0x2948  ldarg.0
0x2949  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x294e  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection(valuetype [mscorlib]System.Guid)
0x2953  stloc.1
0x2954  ldloc.1
0x2955  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x295a  leave.s  loc_297A
0x295c  stloc.s  4
0x295e  ldarg.0
0x295f  ldloc.s  4
0x2961  ldnull
0x2962  ldstr    aExceptionWhile// "Exception while trying to open database"...
0x2967  ldloc.1
0x2968  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0x296d  ldarg.0
0x296e  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0x2973  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception, class [System.Data]System.Data.IDbCommand, string, valuetype [mscorlib]System.Guid, string)
0x2978  rethrow
0x297a  ldc.i4.0
0x297b  stloc.2
0x297c  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2981  stloc.3
0x2982  ldloc.1
0x2983  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x2988  stloc.s  5
0x298a  br.s     loc_29F2
0x298c  ldarg.1
0x298d  callvirt instance var<u1> class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Workflow.WorkflowLogDescriptor>::Dequeue()
0x2992  stloc.s  6
0x2994  ldloc.s  6
0x2996  callvirt instance valuetype Microsoft.Crm.Workflow.OperationType Microsoft.Crm.Workflow.WorkflowLogDescriptor::get_Operation()
0x299b  stloc.s  7
0x299d  ldloc.s  7
0x299f  brfalse.s loc_29A8
0x29a1  ldloc.s  7
0x29a3  ldc.i4.1
0x29a4  beq.s    loc_29CE
0x29a6  br.s     loc_29F2
0x29a8  ldloc.3
0x29a9  ldarg.0
0x29aa  ldloc.2
0x29ab  dup
0x29ac  ldc.i4.1
0x29ad  add
0x29ae  stloc.2
0x29af  ldloc.s  6
0x29b1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.WorkflowLogDescriptor::get_Entity()
0x29b6  ldloc.0
0x29b7  ldloc.s  5
0x29b9  ldarg.2
0x29ba  call     instance string Microsoft.Crm.Workflow.WorkflowLogDataAccess::GenerateInsert(int32 row, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity log, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata, class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.Workflow.WorkflowContext context)
0x29bf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x29c4  pop
0x29c5  ldloc.3
0x29c6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x29cb  pop
0x29cc  br.s     loc_29F2
0x29ce  ldloc.3
0x29cf  ldarg.0
0x29d0  ldloc.2
0x29d1  dup
0x29d2  ldc.i4.1
0x29d3  add
0x29d4  stloc.2
0x29d5  ldloc.s  6
0x29d7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.WorkflowLogDescriptor::get_Entity()
0x29dc  ldloc.0
0x29dd  ldloc.s  5
0x29df  ldarg.2
0x29e0  call     instance string Microsoft.Crm.Workflow.WorkflowLogDataAccess::GenerateUpdate(int32 row, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity log, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata, class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.Workflow.WorkflowContext context)
0x29e5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x29ea  pop
0x29eb  ldloc.3
0x29ec  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x29f1  pop
0x29f2  ldarg.1
0x29f3  callvirt instance int32 class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Workflow.WorkflowLogDescriptor>::get_Count()
0x29f8  ldc.i4.0
0x29f9  bgt.s    loc_298C
0x29fb  ldloc.s  5
0x29fd  ldloc.3
0x29fe  callvirt instance string [mscorlib]System.Object::ToString()
0x2a03  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2a08  ldloc.s  5
0x2a0a  ldc.i4.s 0x56
0x2a0c  ldstr    aFlushpendingwo// "FlushPendingWorkflowLog"
0x2a11  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x2a16  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x2a1b  stloc.s  8
0x2a1d  leave.s  loc_2A54
0x2a1f  stloc.s  9
0x2a21  ldarg.0
0x2a22  ldloc.s  9
0x2a24  ldloc.s  5
0x2a26  ldstr    aExceptionWhile_0// "Exception while executing database quer"...
0x2a2b  ldloc.1
0x2a2c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0x2a31  ldarg.0
0x2a32  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0x2a37  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception, class [System.Data]System.Data.IDbCommand, string, valuetype [mscorlib]System.Guid, string)
0x2a3c  rethrow
0x2a3e  ldloc.s  5
0x2a40  brfalse.s loc_2A49
0x2a42  ldloc.s  5
0x2a44  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a49  endfinally
0x2a4a  ldloc.1
0x2a4b  brfalse.s loc_2A53
0x2a4d  ldloc.1
0x2a4e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a53  endfinally
0x2a54  ldloc.s  8
0x2a56  ret
```
