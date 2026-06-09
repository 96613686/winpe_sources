# Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::UpdateOfficeAppsDeploymentMailbox

- ea: `0x73db0`
- end: `0x73eac`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::UpdateOfficeAppsDeploymentMailbox`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x42380`

## callees

- `0x41210`
- `0x71c20`
- `0x71d00`
- `0x73db0`

## string_xrefs

- `0x73dd8`: `UPDATE Mailbox SET`
- `0x73de4`: `OfficeAppsDeploymentScheduled=@officeAppsDeploymentScheduled,`
- `0x73dfc`: `OfficeAppsDeploymentCompleteOn=@officeAppsDeploymentCompleteOn,`
- `0x73e20`: `@officeAppsDeploymentScheduled`
- `0x73e49`: `@officeAppsDeploymentCompleteOn`

## pseudocode

```c

```

## disassembly

```asm
0x73db0  ldarg.1
0x73db1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x73db6  call     bool Microsoft.Crm.Asynchronous.EmailConnector.Utility::IsDbDeployedGreaterThanOrEqualToAra(valuetype [mscorlib]System.Guid organizationId)
0x73dbb  brfalse  loc_73EAB
0x73dc0  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x73dc5  stloc.0
0x73dc6  ldloc.0
0x73dc7  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x73dcc  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x73dd1  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x73dd6  stloc.1
0x73dd7  ldloc.1
0x73dd8  ldstr    aUpdateMailboxS// "UPDATE Mailbox SET"
0x73ddd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x73de2  pop
0x73de3  ldloc.1
0x73de4  ldstr    aOfficeappsdepl_3// "OfficeAppsDeploymentScheduled=@officeAp"...
0x73de9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x73dee  pop
0x73def  ldloc.1
0x73df0  ldstr    aOfficeappsdepl_4// "OfficeAppsDeploymentStatus=@officeAppsD"...
0x73df5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x73dfa  pop
0x73dfb  ldloc.1
0x73dfc  ldstr    aOfficeappsdepl_5// "OfficeAppsDeploymentCompleteOn=@officeA"...
0x73e01  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x73e06  pop
0x73e07  ldloc.1
0x73e08  ldstr    aOfficeappsdepl_6// "OfficeAppsDeploymentError=@OfficeAppsDe"...
0x73e0d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x73e12  pop
0x73e13  ldloc.1
0x73e14  ldstr    aWhereMailboxid// "WHERE MailboxId=@mailboxId"
0x73e19  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x73e1e  pop
0x73e1f  dup
0x73e20  ldstr    aOfficeappsdepl_7// "@officeAppsDeploymentScheduled"
0x73e25  ldc.i4.0
0x73e26  box      [mscorlib]System.Int32
0x73e2b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x73e30  pop
0x73e31  dup
0x73e32  ldstr    aOfficeappsdepl_8// "@officeAppsDeploymentStatus"
0x73e37  ldarg.1
0x73e38  ldstr    aOfficeappsdepl// "officeappsdeploymentstatus"
0x73e3d  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x73e42  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x73e47  pop
0x73e48  dup
0x73e49  ldstr    aOfficeappsdepl_9// "@officeAppsDeploymentCompleteOn"
0x73e4e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x73e53  box      [mscorlib]System.DateTime
0x73e58  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x73e5d  pop
0x73e5e  dup
0x73e5f  ldstr    aOfficeappsdepl_10// "@OfficeAppsDeploymentError"
0x73e64  ldarg.1
0x73e65  ldstr    aOfficeappsdepl_0// "officeappsdeploymenterror"
0x73e6a  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x73e6f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x73e74  pop
0x73e75  ldstr    aMailboxid_1// "@mailboxId"
0x73e7a  ldarg.1
0x73e7b  ldstr    aMailboxid// "mailboxid"
0x73e80  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x73e85  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x73e8a  pop
0x73e8b  ldloc.0
0x73e8c  ldloc.1
0x73e8d  callvirt instance string [mscorlib]System.Object::ToString()
0x73e92  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x73e97  ldarg.0
0x73e98  ldloc.0
0x73e99  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x73e9e  pop
0x73e9f  leave.s  loc_73EAB
0x73ea1  ldloc.0
0x73ea2  brfalse.s loc_73EAA
0x73ea4  ldloc.0
0x73ea5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x73eaa  endfinally
0x73eab  ret
```
