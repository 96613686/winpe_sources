# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateSystemUserReferences_0

- ea: `0x201a0`
- end: `0x20544`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateSystemUserReferences_0`
- size: `932`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2710`
- `0x20140`

## callees

- `0x540`
- `0x580`
- `0x126a0`
- `0x126e0`
- `0x1d810`
- `0x201a0`
- `0x20550`

## string_xrefs

- `0x201c2`: `\n						select SystemUserId,FullName\n						from SystemUserBase\n						where IsDisabled = 0 AND AccessMode != 3\n						`
- `0x20271`: `UpdateSystemUserReferences : originalFullName : `
- `0x202aa`: `UPDATE OwnerBase set Name=@NewFullName, YomiName=@NewFullName WHERE OwnerId=@OwnerId`
- `0x20308`: `ActiveDirectoryGuid`
- `0x203a9`: `update ReportBase set OwnerId = @new where OwnerId = @old;`
- `0x203bb`: `update SystemUserPrincipals set PrincipalId = @new where PrincipalId = @old;`
- `0x203d2`: `update PrincipalObjectAccess set PrincipalId = @new where PrincipalId = @old;`
- `0x203e9`: `update PrincipalObjectAccess set ObjectId = @new where ObjectId = @old;`
- `0x20400`: `update EmailSearch set ParentObjectId = @new where ParentObjectId = @old;`
- `0x20501`: `OrganizationDatabaseAccess`
- `0x20506`: `UpdateSystemUserReferences`
- `0x20512`: `AttemptProvisioningActions`

## pseudocode

```c

```

## disassembly

```asm
0x201a0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::.ctor()
0x201a5  stloc.1
0x201a6  ldarg.0
0x201a7  ldc.i4.0
0x201a8  ldc.i4.0
0x201a9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x201ae  stloc.s  4
0x201b0  ldloc.s  4
0x201b2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x201b7  ldloc.s  4
0x201b9  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x201be  stloc.s  5
0x201c0  ldloc.s  5
0x201c2  ldstr    aSelectSystemus_3// "\r\n\t\t\t\t\t\tselect SystemUserId,Ful"...
0x201c7  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x201cc  ldloc.s  5
0x201ce  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0x201d3  stloc.s  6
0x201d5  br.s     loc_201F5
0x201d7  ldloc.s  6
0x201d9  ldc.i4.0
0x201da  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x201df  stloc.s  7
0x201e1  ldarg.1
0x201e2  brfalse.s loc_201F5
0x201e4  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x201e9  stloc.s  8
0x201eb  ldloc.1
0x201ec  ldloc.s  7
0x201ee  ldloc.s  8
0x201f0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::set_Item(var<u1>, !!T0)
0x201f5  ldloc.s  6
0x201f7  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x201fc  brtrue.s loc_201D7
0x201fe  leave.s  loc_20218
0x20200  ldloc.s  6
0x20202  brfalse.s loc_2020B
0x20204  ldloc.s  6
0x20206  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2020b  endfinally
0x2020c  ldloc.s  5
0x2020e  brfalse.s loc_20217
0x20210  ldloc.s  5
0x20212  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20217  endfinally
0x20218  ldloc.s  4
0x2021a  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x2021f  stloc.s  9
0x20221  ldloc.s  9
0x20223  ldstr    aSelectFullname// "SELECT FullName FROM SystemUserBase WHE"...
0x20228  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2022d  ldloc.s  9
0x2022f  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x20234  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x20239  ldstr    aUserid_1// "@userId"
0x2023e  ldarg.2
0x2023f  box      [mscorlib]System.Guid
0x20244  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x20249  pop
0x2024a  ldloc.s  9
0x2024c  callvirt instance object [System.Data]System.Data.IDbCommand::ExecuteScalar()
0x20251  castclass [mscorlib]System.String
0x20256  stloc.0
0x20257  leave.s  loc_20271
0x20259  ldloc.s  9
0x2025b  brfalse.s loc_20264
0x2025d  ldloc.s  9
0x2025f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20264  endfinally
0x20265  ldloc.s  4
0x20267  brfalse.s loc_20270
0x20269  ldloc.s  4
0x2026b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20270  endfinally
0x20271  ldstr    aUpdatesystemus// "UpdateSystemUserReferences : originalFu"...
0x20276  ldloc.0
0x20277  call     string [mscorlib]System.String::Concat(string, string)
0x2027c  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x20281  ldarg.0
0x20282  ldarg.2
0x20283  ldarg.3
0x20284  ldarg.s  4
0x20286  ldarg.s  5
0x20288  call     string Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateInitialUserUsingSql(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid systemUserId, string firstName, string lastName, string userEmail)
0x2028d  stloc.2
0x2028e  ldarg.0
0x2028f  ldc.i4.0
0x20290  ldc.i4.0
0x20291  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x20296  stloc.s  0xA
0x20298  ldloc.s  0xA
0x2029a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x2029f  ldloc.s  0xA
0x202a1  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x202a6  stloc.s  0xB
0x202a8  ldloc.s  0xB
0x202aa  ldstr    aUpdateOwnerbas_0// "UPDATE OwnerBase set Name=@NewFullName,"...
0x202af  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x202b4  ldloc.s  0xB
0x202b6  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x202bb  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x202c0  dup
0x202c1  ldstr    aNewfullname// "@NewFullName"
0x202c6  ldloc.2
0x202c7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x202cc  pop
0x202cd  ldstr    aOwnerid_0// "@OwnerId"
0x202d2  ldarg.2
0x202d3  box      [mscorlib]System.Guid
0x202d8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x202dd  pop
0x202de  ldloc.s  0xB
0x202e0  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x202e5  pop
0x202e6  leave.s  loc_20300
0x202e8  ldloc.s  0xB
0x202ea  brfalse.s loc_202F3
0x202ec  ldloc.s  0xB
0x202ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x202f3  endfinally
0x202f4  ldloc.s  0xA
0x202f6  brfalse.s loc_202FF
0x202f8  ldloc.s  0xA
0x202fa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x202ff  endfinally
0x20300  ldc.i4.1
0x20301  newarr   [mscorlib]System.String
0x20306  dup
0x20307  ldc.i4.0
0x20308  ldstr    aActivedirector_0// "ActiveDirectoryGuid"
0x2030d  stelem.ref
0x2030e  stloc.3
0x2030f  ldloc.1
0x20310  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::GetEnumerator()
0x20315  stloc.s  0xC
0x20317  br       loc_20431
0x2031c  ldloca.s 0xC
0x2031e  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Current()
0x20323  stloc.s  0xD
0x20325  ldarg.0
0x20326  ldc.i4.0
0x20327  ldc.i4.0
0x20328  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x2032d  stloc.s  0xE
0x2032f  ldloc.s  0xE
0x20331  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x20336  ldloca.s 0xD
0x20338  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Key()
0x2033d  stloc.s  0xF
0x2033f  ldloca.s 0xD
0x20341  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Value()
0x20346  stloc.s  0x10
0x20348  ldloc.s  0xE
0x2034a  ldloc.3
0x2034b  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection, string[] uniqueIndexFields)
0x20350  dup
0x20351  ldstr    aSystemuser_0// "systemuser"
0x20356  ldloc.s  0xF
0x20358  ldloc.s  0x10
0x2035a  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::ChangePrimaryKey(string entityName, valuetype [mscorlib]System.Guid oldId, valuetype [mscorlib]System.Guid newId)
0x2035f  ldstr    aOwner// "owner"
0x20364  ldloc.s  0xF
0x20366  ldloc.s  0x10
0x20368  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::ChangePrimaryKey(string entityName, valuetype [mscorlib]System.Guid oldId, valuetype [mscorlib]System.Guid newId)
0x2036d  ldloc.s  0xE
0x2036f  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x20374  stloc.s  0x11
0x20376  ldloc.s  0x11
0x20378  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2037d  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x20382  dup
0x20383  ldstr    aNew// "new"
0x20388  ldloc.s  0x10
0x2038a  box      [mscorlib]System.Guid
0x2038f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x20394  pop
0x20395  ldstr    aOld_0// "old"
0x2039a  ldloc.s  0xF
0x2039c  box      [mscorlib]System.Guid
0x203a1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x203a6  pop
0x203a7  ldloc.s  0x11
0x203a9  ldstr    aUpdateReportba// "update ReportBase set OwnerId = @new wh"...
0x203ae  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x203b3  ldloc.s  0x11
0x203b5  dup
0x203b6  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x203bb  ldstr    aUpdateSystemus_4// "update SystemUserPrincipals set Princip"...
0x203c0  call     string [mscorlib]System.String::Concat(string, string)
0x203c5  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x203ca  ldloc.s  0x11
0x203cc  dup
0x203cd  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x203d2  ldstr    aUpdatePrincipa_0// "update PrincipalObjectAccess set Princi"...
0x203d7  call     string [mscorlib]System.String::Concat(string, string)
0x203dc  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x203e1  ldloc.s  0x11
0x203e3  dup
0x203e4  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x203e9  ldstr    aUpdatePrincipa_1// "update PrincipalObjectAccess set Object"...
0x203ee  call     string [mscorlib]System.String::Concat(string, string)
0x203f3  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x203f8  ldloc.s  0x11
0x203fa  dup
0x203fb  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x20400  ldstr    aUpdateEmailsea_0// "update EmailSearch set ParentObjectId ="...
0x20405  call     string [mscorlib]System.String::Concat(string, string)
0x2040a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2040f  ldloc.s  0x11
0x20411  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x20416  pop
0x20417  leave.s  loc_20431
0x20419  ldloc.s  0x11
0x2041b  brfalse.s loc_20424
0x2041d  ldloc.s  0x11
0x2041f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20424  endfinally
0x20425  ldloc.s  0xE
0x20427  brfalse.s loc_20430
0x20429  ldloc.s  0xE
0x2042b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20430  endfinally
0x20431  ldloca.s 0xC
0x20433  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::MoveNext()
0x20438  brtrue   loc_2031C
0x2043d  leave.s  loc_2044D
0x2043f  ldloca.s 0xC
0x20441  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>
0x20447  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2044c  endfinally
0x2044d  ldarg.0
0x2044e  ldc.i4.0
0x2044f  ldc.i4.0
0x20450  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x20455  stloc.s  0x12
0x20457  ldloc.s  0x12
0x20459  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x2045e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::.ctor()
0x20463  stloc.s  0x13
0x20465  ldloc.s  0x12
0x20467  ldstr    aSelectPostidTe// "SELECT PostId,Text FROM PostBase"
0x2046c  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x20471  stloc.s  0x14
0x20473  ldloc.s  0x14
0x20475  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0x2047a  stloc.s  0x15
0x2047c  br.s     loc_204A2
0x2047e  ldloc.s  0x15
0x20480  ldc.i4.0
0x20481  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x20486  stloc.s  0x16
0x20488  ldloc.s  0x15
0x2048a  ldc.i4.1
0x2048b  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x20490  stloc.s  0x17
0x20492  ldloc.s  0x13
0x20494  ldloc.s  0x16
0x20496  ldloc.s  0x17
0x20498  call     T0x2B000099
0x2049d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::Add(var<u1>)
0x204a2  ldloc.s  0x15
0x204a4  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x204a9  brtrue.s loc_2047E
0x204ab  leave.s  loc_204C5
0x204ad  ldloc.s  0x15
0x204af  brfalse.s loc_204B8
0x204b1  ldloc.s  0x15
0x204b3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x204b8  endfinally
0x204b9  ldloc.s  0x14
0x204bb  brfalse.s loc_204C4
0x204bd  ldloc.s  0x14
0x204bf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x204c4  endfinally
0x204c5  ldloc.s  0x13
0x204c7  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::GetEnumerator()
0x204cc  stloc.s  0x18
0x204ce  br.s     loc_2051E
0x204d0  ldloca.s 0x18
0x204d2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::get_Current()
0x204d7  stloc.s  0x19
0x204d9  ldloc.s  0x19
0x204db  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::get_Item1()
0x204e0  ldloc.s  0x19
0x204e2  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::get_Item2()
0x204e7  ldloc.0
0x204e8  ldloc.2
0x204e9  ldloc.s  0x12
0x204eb  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::FixPost(valuetype [mscorlib]System.Guid postId, string text, string originalFullName, string newFullName, class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection)
0x204f0  leave.s  loc_2051E
0x204f2  stloc.s  0x1A
0x204f4  call     class Microsoft.Crm.CrmLive.Telemetry.ProvisioningLogEventSource Microsoft.Crm.CrmLive.Telemetry.ProvisioningLogEventSource::get_Instance()
0x204f9  ldarg.0
0x204fa  ldarg.s  6
0x204fc  ldstr    a01FailedWithEx// "{0}.{1} failed with exception {2}"
0x20501  ldstr    aOrganizationda_2// "OrganizationDatabaseAccess"
0x20506  ldstr    aUpdatesystemus_0// "UpdateSystemUserReferences"
0x2050b  ldloc.s  0x1A
0x2050d  call     string [mscorlib]System.String::Format(string, object, object, object)
0x20512  ldstr    aAttemptprovisi_0// "AttemptProvisioningActions"
  ... truncated ...
```
