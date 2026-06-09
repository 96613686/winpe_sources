# Microsoft.Crm.ObjectModel.OrganizationManagementHelper::UpdatePrincipalObjectAccess

- ea: `0xce780`
- end: `0xce812`
- name: `Microsoft.Crm.ObjectModel.OrganizationManagementHelper::UpdatePrincipalObjectAccess`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xce2e0`

## callees

- `0xce780`
- `0xced30`
- `0xced70`

## string_xrefs

- `0xce7fb`: `UpdateOrganizationReferences`
- `0xce7c2`: `D:\a\1\s\src\Core\ObjectModel\Services\BusinessManagement\OrganizationManagementHelper.cs`
- `0xce7e3`: `D:\a\1\s\src\Core\ObjectModel\Services\BusinessManagement\OrganizationManagementHelper.cs`
- `0xce781`: `UPDATE PrincipalObjectAccess SET PrincipalId = @newOrganizationId Where PrincipalId = @oldOrganizationId`
- `0xce7bd`: `UpdatePrincipalObjectAccess`
- `0xce7de`: `UpdatePrincipalObjectAccess`
- `0xce800`: `UpdatePrincipalObjectAccess`
- `0xce7ce`: `SELECT count(PrincipalId) RecordCount FROM PrincipalObjectAccess WHERE PrincipalId <> @newOrganizationId`
- `0xce805`: `PrincipalId not updated in PrincipalObjectAccess table.`

## pseudocode

```c

```

## disassembly

```asm
0xce780  ldarg.0
0xce781  ldstr    aUpdatePrincipa// "UPDATE PrincipalObjectAccess SET Princi"...
0xce786  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xce78b  ldarg.0
0xce78c  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::ClearParameters(class [System.Data]System.Data.IDbCommand command)
0xce791  ldarg.0
0xce792  ldarg.1
0xce793  box      [mscorlib]System.Guid
0xce798  ldstr    aNeworganizatio// "@newOrganizationId"
0xce79d  ldc.i4.s 9
0xce79f  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0xce7a4  ldarg.0
0xce7a5  ldarg.2
0xce7a6  box      [mscorlib]System.Guid
0xce7ab  ldstr    aOldorganizatio_0// "@oldOrganizationId"
0xce7b0  ldc.i4.s 9
0xce7b2  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0xce7b7  ldarg.0
0xce7b8  ldc.i4   0xA6
0xce7bd  ldstr    aUpdateprincipa_0// "UpdatePrincipalObjectAccess"
0xce7c2  ldstr    aDA1SSrcCoreObj_21// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0xce7c7  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xce7cc  pop
0xce7cd  ldarg.0
0xce7ce  ldstr    aSelectCountPri_0// "SELECT count(PrincipalId) RecordCount F"...
0xce7d3  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xce7d8  ldarg.0
0xce7d9  ldc.i4   0xAA
0xce7de  ldstr    aUpdateprincipa_0// "UpdatePrincipalObjectAccess"
0xce7e3  ldstr    aDA1SSrcCoreObj_21// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0xce7e8  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xce7ed  unbox.any [mscorlib]System.Int32
0xce7f2  ldc.i4.0
0xce7f3  ble.s    loc_CE811
0xce7f5  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.AuditHistory::NewService()
0xce7fa  ldarg.1
0xce7fb  ldstr    aUpdateorganiza// "UpdateOrganizationReferences"
0xce800  ldstr    aUpdateprincipa_0// "UpdatePrincipalObjectAccess"
0xce805  ldstr    aPrincipalidNot_0// "PrincipalId not updated in PrincipalObj"...
0xce80a  ldc.i4.1
0xce80b  ldarg.1
0xce80c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CreateCompletedEntry(valuetype [mscorlib]System.Guid, string, string, string, bool, valuetype [mscorlib]System.Guid)
0xce811  ret
```
