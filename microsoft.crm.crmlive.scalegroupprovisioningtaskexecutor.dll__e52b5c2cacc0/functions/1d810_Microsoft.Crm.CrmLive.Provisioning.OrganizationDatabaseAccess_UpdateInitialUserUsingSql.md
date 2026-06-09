# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateInitialUserUsingSql

- ea: `0x1d810`
- end: `0x1d904`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateInitialUserUsingSql`
- size: `244`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1d7e0`
- `0x201a0`

## callees

- `0x1d810`
- `0x1d910`
- `0x207d0`
- `0x20980`

## string_xrefs

- `0x1d898`: `emailrouteraccessapproval`
- `0x1d8c8`: `UPDATE SystemUserBase SET FirstName=@firstName, LastName=@lastName, InternalEmailAddress=@internalemailaddress, DomainName=@domainname, WindowsLiveId=@windowsliveid, OrganizationId=@organizationid, EmailRouterAccessApproval=@emailrouteraccessapproval, FullName=@fullname, YomiFullName=@fullname where SystemUserId=@systemuserid`

## pseudocode

```c

```

## disassembly

```asm
0x1d810  ldc.i4.1
0x1d811  stloc.0
0x1d812  ldarg.0
0x1d813  ldarg.2
0x1d814  ldsfld   string [mscorlib]System.String::Empty
0x1d819  ldarg.3
0x1d81a  call     string Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::GenerateFullName(valuetype [mscorlib]System.Guid organizationId, string firstName, string middleName, string lastName)
0x1d81f  stloc.1
0x1d820  ldarg.0
0x1d821  ldc.i4.0
0x1d822  ldc.i4.0
0x1d823  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1d828  stloc.2
0x1d829  ldloc.2
0x1d82a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1d82f  ldloc.2
0x1d830  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1d835  stloc.3
0x1d836  ldloc.3
0x1d837  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1d83c  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1d841  dup
0x1d842  ldstr    aFirstname_1// "firstName"
0x1d847  ldarg.2
0x1d848  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d84d  pop
0x1d84e  dup
0x1d84f  ldstr    aLastname_1// "lastName"
0x1d854  ldarg.3
0x1d855  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d85a  pop
0x1d85b  dup
0x1d85c  ldstr    aInternalemaila// "internalemailaddress"
0x1d861  ldarg.s  4
0x1d863  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d868  pop
0x1d869  dup
0x1d86a  ldstr    aDomainname_0// "domainname"
0x1d86f  ldarg.s  4
0x1d871  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d876  pop
0x1d877  dup
0x1d878  ldstr    aWindowsliveid// "windowsliveid"
0x1d87d  ldarg.s  4
0x1d87f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d884  pop
0x1d885  dup
0x1d886  ldstr    aOrganizationid_1// "organizationid"
0x1d88b  ldarg.0
0x1d88c  box      [mscorlib]System.Guid
0x1d891  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d896  pop
0x1d897  dup
0x1d898  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x1d89d  ldloc.0
0x1d89e  box      [mscorlib]System.Int32
0x1d8a3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d8a8  pop
0x1d8a9  dup
0x1d8aa  ldstr    aFullname// "fullname"
0x1d8af  ldloc.1
0x1d8b0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d8b5  pop
0x1d8b6  ldstr    aSystemuserid_0// "systemuserid"
0x1d8bb  ldarg.1
0x1d8bc  box      [mscorlib]System.Guid
0x1d8c1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d8c6  pop
0x1d8c7  ldloc.3
0x1d8c8  ldstr    aUpdateSystemus// "UPDATE SystemUserBase SET FirstName=@fi"...
0x1d8cd  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1d8d2  ldloc.3
0x1d8d3  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x1d8d8  pop
0x1d8d9  leave.s  loc_1D8EF
0x1d8db  ldloc.3
0x1d8dc  brfalse.s loc_1D8E4
0x1d8de  ldloc.3
0x1d8df  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d8e4  endfinally
0x1d8e5  ldloc.2
0x1d8e6  brfalse.s loc_1D8EE
0x1d8e8  ldloc.2
0x1d8e9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d8ee  endfinally
0x1d8ef  ldarg.s  4
0x1d8f1  ldarg.0
0x1d8f2  ldarg.1
0x1d8f3  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpsertUserEmail(string userEmail, valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid systemUserId)
0x1d8f8  ldarg.0
0x1d8f9  ldarg.1
0x1d8fa  ldloc.1
0x1d8fb  ldarg.s  4
0x1d8fd  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateMailboxNames(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid systemUserId, string fullName, string userEmail)
0x1d902  ldloc.1
0x1d903  ret
```
