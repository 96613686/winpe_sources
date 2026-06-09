# Microsoft.Crm.ObjectModel.OrganizationManagementHelper::RemoveOldOrg

- ea: `0xce660`
- end: `0xce6df`
- name: `Microsoft.Crm.ObjectModel.OrganizationManagementHelper::RemoveOldOrg`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0xce2e0`

## callees

- `0xce660`
- `0xced30`
- `0xced70`

## string_xrefs

- `0xce6c8`: `UpdateOrganizationReferences`
- `0xce661`: `DELETE FROM OrganizationBase WHERE OrganizationId <> @newOrganizationId `
- `0xce68a`: `RemoveOldOrg`
- `0xce6ab`: `RemoveOldOrg`
- `0xce6cd`: `RemoveOldOrg`
- `0xce68f`: `D:\a\1\s\src\Core\ObjectModel\Services\BusinessManagement\OrganizationManagementHelper.cs`
- `0xce6b0`: `D:\a\1\s\src\Core\ObjectModel\Services\BusinessManagement\OrganizationManagementHelper.cs`
- `0xce6d2`: `Old Org not removed from OrganizationBase table.`

## pseudocode

```c

```

## disassembly

```asm
0xce660  ldarg.0
0xce661  ldstr    aDeleteFromOrga// "DELETE FROM OrganizationBase WHERE Orga"...
0xce666  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xce66b  ldarg.0
0xce66c  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::ClearParameters(class [System.Data]System.Data.IDbCommand command)
0xce671  ldarg.0
0xce672  ldarg.1
0xce673  box      [mscorlib]System.Guid
0xce678  ldstr    aNeworganizatio// "@newOrganizationId"
0xce67d  ldc.i4.s 9
0xce67f  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0xce684  ldarg.0
0xce685  ldc.i4   0x81
0xce68a  ldstr    aRemoveoldorg// "RemoveOldOrg"
0xce68f  ldstr    aDA1SSrcCoreObj_21// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0xce694  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xce699  pop
0xce69a  ldarg.0
0xce69b  ldstr    aSelectCountOrg// "SELECT count(OrganizationId) RecordCoun"...
0xce6a0  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xce6a5  ldarg.0
0xce6a6  ldc.i4   0x85
0xce6ab  ldstr    aRemoveoldorg// "RemoveOldOrg"
0xce6b0  ldstr    aDA1SSrcCoreObj_21// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0xce6b5  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xce6ba  unbox.any [mscorlib]System.Int32
0xce6bf  ldc.i4.0
0xce6c0  ble.s    loc_CE6DE
0xce6c2  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.AuditHistory::NewService()
0xce6c7  ldarg.1
0xce6c8  ldstr    aUpdateorganiza// "UpdateOrganizationReferences"
0xce6cd  ldstr    aRemoveoldorg// "RemoveOldOrg"
0xce6d2  ldstr    aOldOrgNotRemov// "Old Org not removed from OrganizationBa"...
0xce6d7  ldc.i4.1
0xce6d8  ldarg.1
0xce6d9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CreateCompletedEntry(valuetype [mscorlib]System.Guid, string, string, string, bool, valuetype [mscorlib]System.Guid)
0xce6de  ret
```
