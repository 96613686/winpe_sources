# Microsoft.Crm.ObjectModel.OrganizationManagementHelper::UpdateSystemUserPrincipals

- ea: `0xce6e0`
- end: `0xce772`
- name: `Microsoft.Crm.ObjectModel.OrganizationManagementHelper::UpdateSystemUserPrincipals`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xce2e0`

## callees

- `0xce6e0`
- `0xced30`
- `0xced70`

## string_xrefs

- `0xce75b`: `UpdateOrganizationReferences`
- `0xce722`: `D:\a\1\s\src\Core\ObjectModel\Services\BusinessManagement\OrganizationManagementHelper.cs`
- `0xce743`: `D:\a\1\s\src\Core\ObjectModel\Services\BusinessManagement\OrganizationManagementHelper.cs`
- `0xce6e1`: `UPDATE SystemUserPrincipals SET PrincipalId = @newOrganizationId Where PrincipalId = @oldOrganizationId`
- `0xce71d`: `UpdateSystemUserPrincipals`
- `0xce73e`: `UpdateSystemUserPrincipals`
- `0xce760`: `UpdateSystemUserPrincipals`
- `0xce765`: `PrincipalId not updated in SystemUserPrincipals table.`

## pseudocode

```c

```

## disassembly

```asm
0xce6e0  ldarg.0
0xce6e1  ldstr    aUpdateSystemus// "UPDATE SystemUserPrincipals SET Princip"...
0xce6e6  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xce6eb  ldarg.0
0xce6ec  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::ClearParameters(class [System.Data]System.Data.IDbCommand command)
0xce6f1  ldarg.0
0xce6f2  ldarg.1
0xce6f3  box      [mscorlib]System.Guid
0xce6f8  ldstr    aNeworganizatio// "@newOrganizationId"
0xce6fd  ldc.i4.s 9
0xce6ff  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0xce704  ldarg.0
0xce705  ldarg.2
0xce706  box      [mscorlib]System.Guid
0xce70b  ldstr    aOldorganizatio_0// "@oldOrganizationId"
0xce710  ldc.i4.s 9
0xce712  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0xce717  ldarg.0
0xce718  ldc.i4   0x94
0xce71d  ldstr    aUpdatesystemus_0// "UpdateSystemUserPrincipals"
0xce722  ldstr    aDA1SSrcCoreObj_21// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0xce727  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xce72c  pop
0xce72d  ldarg.0
0xce72e  ldstr    aSelectCountPri// "SELECT count(PrincipalId) RecordCount F"...
0xce733  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xce738  ldarg.0
0xce739  ldc.i4   0x98
0xce73e  ldstr    aUpdatesystemus_0// "UpdateSystemUserPrincipals"
0xce743  ldstr    aDA1SSrcCoreObj_21// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0xce748  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xce74d  unbox.any [mscorlib]System.Int32
0xce752  ldc.i4.0
0xce753  ble.s    loc_CE771
0xce755  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.AuditHistory::NewService()
0xce75a  ldarg.1
0xce75b  ldstr    aUpdateorganiza// "UpdateOrganizationReferences"
0xce760  ldstr    aUpdatesystemus_0// "UpdateSystemUserPrincipals"
0xce765  ldstr    aPrincipalidNot// "PrincipalId not updated in SystemUserPr"...
0xce76a  ldc.i4.1
0xce76b  ldarg.1
0xce76c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CreateCompletedEntry(valuetype [mscorlib]System.Guid, string, string, string, bool, valuetype [mscorlib]System.Guid)
0xce771  ret
```
