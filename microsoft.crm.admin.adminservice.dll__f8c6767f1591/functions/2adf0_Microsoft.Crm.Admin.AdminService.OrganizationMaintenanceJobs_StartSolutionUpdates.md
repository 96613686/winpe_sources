# Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::StartSolutionUpdates

- ea: `0x2adf0`
- end: `0x2b04a`
- name: `Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::StartSolutionUpdates`
- size: `602`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1ea10`
- `0x25a40`
- `0x276a0`
- `0x28620`
- `0x2adf0`

## string_xrefs

- `0x2ae5c`: `StartSolutionUpdates`
- `0x2af3b`: `StartSolutionUpdates`
- `0x2aed3`: `UPDATE ScaleGroupOrganizationMaintenanceJobs SET NextRunTime = @nextRunTime , JobParameters = @uninstall WHERE OperationType = @operationType AND State = 0`
- `0x2af1a`: `@uninstall`
- `0x2af29`: `uninstall`

## pseudocode

```c

```

## disassembly

```asm
0x2adf0  ldarg.1
0x2adf1  ldstr    aScalegroupname// "scaleGroupName"
0x2adf6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x2adfb  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid>::.ctor()
0x2ae00  stloc.0
0x2ae01  ldarg.1
0x2ae02  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::RetrieveScaleGroupIdFromName(string scaleGroupName)
0x2ae07  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService(valuetype [mscorlib]System.Guid)
0x2ae0c  stloc.1
0x2ae0d  ldloc.1
0x2ae0e  ldc.i4.1
0x2ae0f  callvirt instance class [System.Data]System.Data.IDbConnection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::NewConnection(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope)
0x2ae14  stloc.3
0x2ae15  ldloc.3
0x2ae16  callvirt instance void [System.Data]System.Data.IDbConnection::Open()
0x2ae1b  ldloc.3
0x2ae1c  callvirt instance class [System.Data]System.Data.IDbCommand [System.Data]System.Data.IDbConnection::CreateCommand()
0x2ae21  stloc.s  4
0x2ae23  ldloc.s  4
0x2ae25  ldstr    aSelectOrganiza// "SELECT OrganizationId FROM ScaleGroupOr"...
0x2ae2a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2ae2f  ldloc.s  4
0x2ae31  ldc.i4.1
0x2ae32  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x2ae37  ldloc.s  4
0x2ae39  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2ae3e  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x2ae43  ldstr    aOperationtype// "@operationType"
0x2ae48  ldc.i4.s 0x2D
0x2ae4a  box      [mscorlib]System.Int32
0x2ae4f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2ae54  pop
0x2ae55  ldloc.s  4
0x2ae57  ldc.i4   0x200
0x2ae5c  ldstr    aStartsolutionu// "StartSolutionUpdates"
0x2ae61  ldstr    aDA1SSrcCrmlive_52// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x2ae66  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x2ae6b  stloc.s  5
0x2ae6d  br.s     loc_2AE7D
0x2ae6f  ldloc.0
0x2ae70  ldloc.s  5
0x2ae72  ldc.i4.0
0x2ae73  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x2ae78  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x2ae7d  ldloc.s  5
0x2ae7f  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x2ae84  brtrue.s loc_2AE6F
0x2ae86  leave.s  loc_2AEAA
0x2ae88  ldloc.s  5
0x2ae8a  brfalse.s loc_2AE93
0x2ae8c  ldloc.s  5
0x2ae8e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ae93  endfinally
0x2ae94  ldloc.s  4
0x2ae96  brfalse.s loc_2AE9F
0x2ae98  ldloc.s  4
0x2ae9a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ae9f  endfinally
0x2aea0  ldloc.3
0x2aea1  brfalse.s loc_2AEA9
0x2aea3  ldloc.3
0x2aea4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2aea9  endfinally
0x2aeaa  ldarg.1
0x2aeab  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::RetrieveScaleGroupIdFromName(string scaleGroupName)
0x2aeb0  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService(valuetype [mscorlib]System.Guid)
0x2aeb5  stloc.s  6
0x2aeb7  ldloc.s  6
0x2aeb9  ldc.i4.1
0x2aeba  callvirt instance class [System.Data]System.Data.IDbConnection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::NewConnection(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope)
0x2aebf  stloc.s  7
0x2aec1  ldloc.s  7
0x2aec3  callvirt instance void [System.Data]System.Data.IDbConnection::Open()
0x2aec8  ldloc.s  7
0x2aeca  callvirt instance class [System.Data]System.Data.IDbCommand [System.Data]System.Data.IDbConnection::CreateCommand()
0x2aecf  stloc.s  8
0x2aed1  ldloc.s  8
0x2aed3  ldstr    aUpdateScalegro_0// "UPDATE ScaleGroupOrganizationMaintenanc"...
0x2aed8  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2aedd  ldloc.s  8
0x2aedf  ldc.i4.1
0x2aee0  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x2aee5  ldloc.s  8
0x2aee7  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2aeec  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x2aef1  dup
0x2aef2  ldstr    aNextruntime// "@nextRunTime"
0x2aef7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2aefc  box      [mscorlib]System.DateTime
0x2af01  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2af06  pop
0x2af07  dup
0x2af08  ldstr    aOperationtype// "@operationType"
0x2af0d  ldc.i4.s 0x2D
0x2af0f  box      [mscorlib]System.Int32
0x2af14  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2af19  pop
0x2af1a  ldstr    aUninstall// "@uninstall"
0x2af1f  ldarg.2
0x2af20  brtrue.s loc_2AF29
0x2af22  ldsfld   string [mscorlib]System.String::Empty
0x2af27  br.s     loc_2AF2E
0x2af29  ldstr    aUninstall_0// "uninstall"
0x2af2e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2af33  pop
0x2af34  ldloc.s  8
0x2af36  ldc.i4   0x21B
0x2af3b  ldstr    aStartsolutionu// "StartSolutionUpdates"
0x2af40  ldstr    aDA1SSrcCrmlive_52// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x2af45  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x2af4a  pop
0x2af4b  leave.s  loc_2AF71
0x2af4d  ldloc.s  8
0x2af4f  brfalse.s loc_2AF58
0x2af51  ldloc.s  8
0x2af53  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2af58  endfinally
0x2af59  ldloc.s  7
0x2af5b  brfalse.s loc_2AF64
0x2af5d  ldloc.s  7
0x2af5f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2af64  endfinally
0x2af65  ldloc.s  6
0x2af67  brfalse.s loc_2AF70
0x2af69  ldloc.s  6
0x2af6b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2af70  endfinally
0x2af71  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x2af76  stloc.2
0x2af77  ldloc.0
0x2af78  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid>::get_Count()
0x2af7d  ldc.i4.0
0x2af7e  ble      loc_2B033
0x2af83  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x2af88  stloc.s  9
0x2af8a  ldloc.0
0x2af8b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x2af90  stloc.s  0xA
0x2af92  br       loc_2B019
0x2af97  ldloc.s  0xA
0x2af99  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0x2af9e  stloc.s  0xB
0x2afa0  ldloc.s  9
0x2afa2  ldloc.s  0xB
0x2afa4  callvirt instance class Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Retrieve(valuetype [mscorlib]System.Guid organizationId)
0x2afa9  stloc.s  0xC
0x2afab  ldloc.2
0x2afac  ldloc.s  0xC
0x2afae  callvirt instance string Microsoft.Crm.Admin.AdminService.OrganizationData::get_UniqueName()
0x2afb3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2afb8  leave.s  loc_2B019
0x2afba  stloc.s  0xD
0x2afbc  ldloc.s  0xD
0x2afbe  ldloc.s  0xD
0x2afc0  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2afc5  ldc.i4.0
0x2afc6  newarr   [mscorlib]System.Object
0x2afcb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x2afd0  ldloc.s  0xD
0x2afd2  ldstr    a0FailedToRetri// "{0} : Failed to retrieve Organization U"...
0x2afd7  ldc.i4.1
0x2afd8  newarr   [mscorlib]System.Object
0x2afdd  dup
0x2afde  ldc.i4.0
0x2afdf  ldloca.s 0xB
0x2afe1  constrained. [mscorlib]System.Guid
0x2afe7  callvirt instance string [mscorlib]System.Object::ToString()
0x2afec  stelem.ref
0x2afed  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x2aff2  ldloc.2
0x2aff3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2aff8  ldstr    aErrorRetrievin_0// "Error retrieving UniqueName for Organiz"...
0x2affd  ldc.i4.1
0x2affe  newarr   [mscorlib]System.Object
0x2b003  dup
0x2b004  ldc.i4.0
0x2b005  ldloc.s  0xB
0x2b007  box      [mscorlib]System.Guid
0x2b00c  stelem.ref
0x2b00d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2b012  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2b017  leave.s  loc_2B019
0x2b019  ldloc.s  0xA
0x2b01b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2b020  brtrue   loc_2AF97
0x2b025  leave.s  loc_2B033
0x2b027  ldloc.s  0xA
0x2b029  brfalse.s loc_2B032
0x2b02b  ldloc.s  0xA
0x2b02d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b032  endfinally
0x2b033  ldloc.2
0x2b034  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x2b039  stloc.s  0xE
0x2b03b  leave.s  loc_2B047
0x2b03d  ldloc.1
0x2b03e  brfalse.s loc_2B046
0x2b040  ldloc.1
0x2b041  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b046  endfinally
0x2b047  ldloc.s  0xE
0x2b049  ret
```
