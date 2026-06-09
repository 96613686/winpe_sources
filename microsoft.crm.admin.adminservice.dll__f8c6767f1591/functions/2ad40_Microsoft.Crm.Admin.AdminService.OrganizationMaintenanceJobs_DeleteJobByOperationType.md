# Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::DeleteJobByOperationType

- ea: `0x2ad40`
- end: `0x2adea`
- name: `Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::DeleteJobByOperationType`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x2abd0`

## callees

- `0x2ad40`
- `0x2b770`

## string_xrefs

- `0x2ad57`: `DELETE FROM ScaleGroupOrganizationMaintenanceJobs WHERE OrganizationId = @OrganizationId and OperationType = @OperationType`
- `0x2ad9f`: `DeleteJobByOperationType`
- `0x2adce`: `Exception in DeleteJobByOperationType {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2ad40  ldarg.0
0x2ad41  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x2ad46  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0x2ad4b  call     class [System.Data]System.Data.IDbConnection Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::RetrieveDatabaseConnection(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid datacenterId)
0x2ad50  stloc.0
0x2ad51  ldloc.0
0x2ad52  callvirt instance void [System.Data]System.Data.IDbConnection::Open()
0x2ad57  ldstr    aDeleteFromScal_0// "DELETE FROM ScaleGroupOrganizationMaint"...
0x2ad5c  stloc.1
0x2ad5d  ldloc.0
0x2ad5e  callvirt instance class [System.Data]System.Data.IDbCommand [System.Data]System.Data.IDbConnection::CreateCommand()
0x2ad63  stloc.2
0x2ad64  ldloc.2
0x2ad65  ldloc.1
0x2ad66  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2ad6b  ldloc.2
0x2ad6c  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2ad71  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x2ad76  dup
0x2ad77  ldstr    aOrganizationid_3// "@OrganizationId"
0x2ad7c  ldarg.0
0x2ad7d  box      [mscorlib]System.Guid
0x2ad82  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2ad87  pop
0x2ad88  ldstr    aOperationtype_1// "@OperationType"
0x2ad8d  ldarg.1
0x2ad8e  box      [mscorlib]System.Int32
0x2ad93  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2ad98  pop
0x2ad99  ldloc.2
0x2ad9a  ldc.i4   0x1D8
0x2ad9f  ldstr    aDeletejobbyope// "DeleteJobByOperationType"
0x2ada4  ldstr    aDA1SSrcCrmlive_52// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x2ada9  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x2adae  pop
0x2adaf  leave.s  loc_2ADBB
0x2adb1  ldloc.2
0x2adb2  brfalse.s loc_2ADBA
0x2adb4  ldloc.2
0x2adb5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2adba  endfinally
0x2adbb  leave.s  loc_2ADC7
0x2adbd  ldloc.0
0x2adbe  brfalse.s loc_2ADC6
0x2adc0  ldloc.0
0x2adc1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2adc6  endfinally
0x2adc7  leave.s  loc_2ADE9
0x2adc9  stloc.3
0x2adca  ldloc.3
0x2adcb  ldarg.0
0x2adcc  ldc.i4.s 0x14
0x2adce  ldstr    aExceptionInDel_4// "Exception in DeleteJobByOperationType {"...
0x2add3  ldc.i4.1
0x2add4  newarr   [mscorlib]System.Object
0x2add9  dup
0x2adda  ldc.i4.0
0x2addb  ldloc.3
0x2addc  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2ade1  stelem.ref
0x2ade2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2ade7  rethrow
0x2ade9  ret
```
