# Microsoft.Crm.Asynchronous.RecurringSeriesExpansionDataAccess::PostponeOrPreponeRecurringSeriesExpansionJob

- ea: `0x5bb0`
- end: `0x5d3f`
- name: `Microsoft.Crm.Asynchronous.RecurringSeriesExpansionDataAccess::PostponeOrPreponeRecurringSeriesExpansionJob`
- size: `399`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x4da0`
- `0x4fa0`

## callees

- `0x5bb0`

## string_xrefs

- `0x5c37`: `RecurringSeriesExpansionOperation handler could not retrieve it's existing postponeuntil date, hence postponeuntil could not be updated.`
- `0x5c97`: `update AsyncOperationBase\nset\n	PostponeUntil = @postPoneUntil,	\n	ModifiedOn = @modifiedOn,\n	ModifiedBy = CreatedBy\nwhere\n	AsyncOperationId = @id`

## pseudocode

```c

```

## disassembly

```asm
0x5bb0  ldarg.0
0x5bb1  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.RecurringSeriesExpansionDataAccess::_orgConfig
0x5bb6  stloc.0
0x5bb7  ldc.i4.0
0x5bb8  stloc.1
0x5bb9  ldloc.0
0x5bba  ldloca.s 1
0x5bbc  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x5bc1  ldc.i4.1
0x5bc2  newarr   [mscorlib]System.String
0x5bc7  dup
0x5bc8  ldc.i4.0
0x5bc9  ldstr    aPostponeuntil// "postponeuntil"
0x5bce  stelem.ref
0x5bcf  stloc.2
0x5bd0  ldnull
0x5bd1  stloc.3
0x5bd2  ldarg.0
0x5bd3  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.RecurringSeriesExpansionDataAccess::_crmService
0x5bd8  ldstr    aAsyncoperation// "asyncoperation"
0x5bdd  ldarg.1
0x5bde  ldloc.2
0x5bdf  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x5be4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x5be9  stloc.3
0x5bea  leave.s  loc_5C14
0x5bec  ldarg.0
0x5bed  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.RecurringSeriesExpansionDataAccess::_orgConfig
0x5bf2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x5bf7  ldc.i4.s 0x15
0x5bf9  ldstr    aRecurringserie_2// "RecurringSeriesExpansionOperation handl"...
0x5bfe  ldc.i4.1
0x5bff  newarr   [mscorlib]System.Object
0x5c04  dup
0x5c05  ldc.i4.0
0x5c06  ldarg.1
0x5c07  box      [mscorlib]System.Guid
0x5c0c  stelem.ref
0x5c0d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5c12  rethrow
0x5c14  ldloc.3
0x5c15  brfalse.s loc_5C29
0x5c17  ldloc.3
0x5c18  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x5c1d  ldstr    aPostponeuntil// "postponeuntil"
0x5c22  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x5c27  brtrue.s loc_5C52
0x5c29  ldnull
0x5c2a  ldarg.0
0x5c2b  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.RecurringSeriesExpansionDataAccess::_orgConfig
0x5c30  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x5c35  ldc.i4.s 0x15
0x5c37  ldstr    aRecurringserie_3// "RecurringSeriesExpansionOperation handl"...
0x5c3c  ldc.i4.0
0x5c3d  newarr   [mscorlib]System.Object
0x5c42  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5c47  ldstr    aAsyncHandlerFo_1// "Async Handler for Recurring Series Expa"...
0x5c4c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x5c51  throw
0x5c52  ldloc.3
0x5c53  ldstr    aPostponeuntil// "postponeuntil"
0x5c58  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x5c5d  unbox.any [mscorlib]System.DateTime
0x5c62  stloc.s  4
0x5c64  ldloca.s 4
0x5c66  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x5c6b  stloc.s  4
0x5c6d  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x5c72  stloc.s  5
0x5c74  ldarg.3
0x5c75  brfalse.s loc_5C86
0x5c77  ldarg.2
0x5c78  ldloc.s  4
0x5c7a  call     bool [mscorlib]System.DateTime::op_GreaterThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5c7f  brfalse.s loc_5C95
0x5c81  leave    loc_5D3E
0x5c86  ldarg.2
0x5c87  ldloc.s  4
0x5c89  call     bool [mscorlib]System.DateTime::op_LessThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5c8e  brfalse.s loc_5C95
0x5c90  leave    loc_5D3E
0x5c95  ldloc.s  5
0x5c97  ldstr    aUpdateAsyncope// "update AsyncOperationBase\r\nset\r\n\tP"...
0x5c9c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x5ca1  ldloc.s  5
0x5ca3  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x5ca8  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x5cad  dup
0x5cae  ldstr    aPostponeuntil_0// "@postPoneUntil"
0x5cb3  ldarg.2
0x5cb4  box      [mscorlib]System.DateTime
0x5cb9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5cbe  pop
0x5cbf  dup
0x5cc0  ldstr    aId// "@id"
0x5cc5  ldarg.1
0x5cc6  box      [mscorlib]System.Guid
0x5ccb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5cd0  pop
0x5cd1  ldstr    aModifiedon_1// "@modifiedOn"
0x5cd6  ldarg.0
0x5cd7  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x5cdc  box      [mscorlib]System.DateTime
0x5ce1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5ce6  pop
0x5ce7  ldarg.0
0x5ce8  ldloc.s  5
0x5cea  ldc.i4.1
0x5ceb  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x5cf0  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Nullable`1<int32>)
0x5cf5  pop
0x5cf6  ldarg.0
0x5cf7  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.RecurringSeriesExpansionDataAccess::_orgConfig
0x5cfc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x5d01  ldc.i4.s 0x15
0x5d03  ldstr    aRecurringserie_4// "RecurringSeriesExpansionOperation handl"...
0x5d08  ldc.i4.2
0x5d09  newarr   [mscorlib]System.Object
0x5d0e  dup
0x5d0f  ldc.i4.0
0x5d10  ldloc.s  4
0x5d12  box      [mscorlib]System.DateTime
0x5d17  stelem.ref
0x5d18  dup
0x5d19  ldc.i4.1
0x5d1a  ldarg.2
0x5d1b  box      [mscorlib]System.DateTime
0x5d20  stelem.ref
0x5d21  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5d26  leave.s  loc_5D3E
0x5d28  ldloc.s  5
0x5d2a  brfalse.s loc_5D33
0x5d2c  ldloc.s  5
0x5d2e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d33  endfinally
0x5d34  ldloc.1
0x5d35  brfalse.s loc_5D3D
0x5d37  ldloc.0
0x5d38  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x5d3d  endfinally
0x5d3e  ret
```
