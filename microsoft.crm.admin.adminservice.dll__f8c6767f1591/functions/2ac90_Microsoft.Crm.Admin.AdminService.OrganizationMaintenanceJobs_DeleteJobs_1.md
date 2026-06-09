# Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::DeleteJobs_1

- ea: `0x2ac90`
- end: `0x2ad33`
- name: `Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::DeleteJobs_1`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x2ac80`

## callees

- `0x2ac90`
- `0x2b780`

## string_xrefs

- `0x2aca2`: `DeleteOrganizationDbMaintenanceJobs`
- `0x2acb2`: `DELETE FROM ScaleGroupOrganizationMaintenanceJobs WHERE OrganizationId = @OrganizationId`
- `0x2ace8`: `DeleteJobs`
- `0x2ad17`: `Exception in DeleteOrganizationDbMaintenanceJobs {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2ac90  ldarg.1
0x2ac91  ldarg.2
0x2ac92  ldarg.3
0x2ac93  call     class [System.Data]System.Data.IDbConnection Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::RetrieveDatabaseConnection(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid scaleGroupId, valuetype [mscorlib]System.Guid datacenterId)
0x2ac98  stloc.0
0x2ac99  ldloc.0
0x2ac9a  callvirt instance void [System.Data]System.Data.IDbConnection::Open()
0x2ac9f  ldarg.1
0x2aca0  ldc.i4.s 0x14
0x2aca2  ldstr    aDeleteorganiza_5// "DeleteOrganizationDbMaintenanceJobs"
0x2aca7  ldc.i4.0
0x2aca8  newarr   [mscorlib]System.Object
0x2acad  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2acb2  ldstr    aDeleteFromScal// "DELETE FROM ScaleGroupOrganizationMaint"...
0x2acb7  stloc.1
0x2acb8  ldloc.0
0x2acb9  callvirt instance class [System.Data]System.Data.IDbCommand [System.Data]System.Data.IDbConnection::CreateCommand()
0x2acbe  stloc.2
0x2acbf  ldloc.2
0x2acc0  ldloc.1
0x2acc1  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2acc6  ldloc.2
0x2acc7  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2accc  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x2acd1  ldstr    aOrganizationid_3// "@OrganizationId"
0x2acd6  ldarg.1
0x2acd7  box      [mscorlib]System.Guid
0x2acdc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2ace1  pop
0x2ace2  ldloc.2
0x2ace3  ldc.i4   0x1B7
0x2ace8  ldstr    aDeletejobs// "DeleteJobs"
0x2aced  ldstr    aDA1SSrcCrmlive_52// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x2acf2  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x2acf7  pop
0x2acf8  leave.s  loc_2AD04
0x2acfa  ldloc.2
0x2acfb  brfalse.s loc_2AD03
0x2acfd  ldloc.2
0x2acfe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ad03  endfinally
0x2ad04  leave.s  loc_2AD10
0x2ad06  ldloc.0
0x2ad07  brfalse.s loc_2AD0F
0x2ad09  ldloc.0
0x2ad0a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ad0f  endfinally
0x2ad10  leave.s  loc_2AD32
0x2ad12  stloc.3
0x2ad13  ldloc.3
0x2ad14  ldarg.1
0x2ad15  ldc.i4.s 0x14
0x2ad17  ldstr    aExceptionInDel_3// "Exception in DeleteOrganizationDbMainte"...
0x2ad1c  ldc.i4.1
0x2ad1d  newarr   [mscorlib]System.Object
0x2ad22  dup
0x2ad23  ldc.i4.0
0x2ad24  ldloc.3
0x2ad25  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2ad2a  stelem.ref
0x2ad2b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2ad30  rethrow
0x2ad32  ret
```
