# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::ReadFromOrganizationDatabase

- ea: `0x1d040`
- end: `0x1d228`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::ReadFromOrganizationDatabase`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1cf40`

## callees

- `0x70e0`
- `0x70f0`
- `0x7100`
- `0x7110`
- `0x7130`
- `0x7150`
- `0x7170`
- `0x7190`
- `0x71a0`
- `0x1d040`

## string_xrefs

- `0x1d0ac`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\OrganizationDatabaseAccess.cs`
- `0x1d063`: `@AdminRoleTemplateId`
- `0x1d0a7`: `ReadFromOrganizationDatabase`

## pseudocode

```c

```

## disassembly

```asm
0x1d040  ldarg.0
0x1d041  ldc.i4.0
0x1d042  ldc.i4.0
0x1d043  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1d048  stloc.0
0x1d049  ldloc.0
0x1d04a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1d04f  ldloc.0
0x1d050  ldarg.2
0x1d051  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x1d056  stloc.1
0x1d057  ldloc.1
0x1d058  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1d05d  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1d062  dup
0x1d063  ldstr    aAdminroletempl// "@AdminRoleTemplateId"
0x1d068  ldstr    a627090ff40a340_0// "627090FF-40A3-4053-8790-584EDC5BE201"
0x1d06d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1d072  box      [mscorlib]System.Guid
0x1d077  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d07c  pop
0x1d07d  dup
0x1d07e  ldstr    aUserinvitation// "@UserInvitationStatus"
0x1d083  ldc.i4.4
0x1d084  box      [mscorlib]System.Int32
0x1d089  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d08e  pop
0x1d08f  ldstr    aOrganizationid_2// "@OrganizationId"
0x1d094  ldarg.0
0x1d095  box      [mscorlib]System.Guid
0x1d09a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d09f  pop
0x1d0a0  ldloc.1
0x1d0a1  ldc.i4.1
0x1d0a2  ldc.i4   0x366
0x1d0a7  ldstr    aReadfromorgani// "ReadFromOrganizationDatabase"
0x1d0ac  ldstr    aDDbsShDccm2110_31// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x1d0b1  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, bool, int32, string, string)
0x1d0b6  stloc.2
0x1d0b7  br       loc_1D1F4
0x1d0bc  ldloc.2
0x1d0bd  ldstr    aFirstname_0// "FirstName"
0x1d0c2  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1d0c7  stloc.3
0x1d0c8  ldloc.2
0x1d0c9  ldstr    aLastname_0// "LastName"
0x1d0ce  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1d0d3  stloc.s  4
0x1d0d5  ldloc.2
0x1d0d6  ldstr    aInternalemaila_0// "InternalEmailAddress"
0x1d0db  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1d0e0  stloc.s  5
0x1d0e2  ldloc.2
0x1d0e3  ldstr    aWindowsliveid_0// "WindowsLiveId"
0x1d0e8  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1d0ed  stloc.s  6
0x1d0ef  ldloc.2
0x1d0f0  ldstr    aUilanguageid// "UILanguageId"
0x1d0f5  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1d0fa  stloc.s  7
0x1d0fc  ldloc.2
0x1d0fd  ldstr    aLanguagecode// "LanguageCode"
0x1d102  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1d107  stloc.s  8
0x1d109  ldloc.2
0x1d10a  ldstr    aSystemuserid// "SystemUserId"
0x1d10f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1d114  stloc.s  9
0x1d116  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::.ctor()
0x1d11b  stloc.s  0xA
0x1d11d  ldloc.3
0x1d11e  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1d123  beq.s    loc_1D132
0x1d125  ldloc.s  0xA
0x1d127  ldloc.3
0x1d128  castclass [mscorlib]System.String
0x1d12d  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::set_FirstName(string value)
0x1d132  ldloc.s  4
0x1d134  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1d139  beq.s    loc_1D149
0x1d13b  ldloc.s  0xA
0x1d13d  ldloc.s  4
0x1d13f  castclass [mscorlib]System.String
0x1d144  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::set_LastName(string value)
0x1d149  ldloc.s  5
0x1d14b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1d150  beq.s    loc_1D160
0x1d152  ldloc.s  0xA
0x1d154  ldloc.s  5
0x1d156  castclass [mscorlib]System.String
0x1d15b  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::set_EmailAddress(string value)
0x1d160  ldloc.s  6
0x1d162  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1d167  beq.s    loc_1D177
0x1d169  ldloc.s  0xA
0x1d16b  ldloc.s  6
0x1d16d  castclass [mscorlib]System.String
0x1d172  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::set_WindowsLiveId(string value)
0x1d177  ldloc.s  7
0x1d179  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1d17e  beq.s    loc_1D199
0x1d180  ldloc.s  7
0x1d182  unbox.any [mscorlib]System.Int32
0x1d187  brfalse.s loc_1D199
0x1d189  ldloc.s  0xA
0x1d18b  ldloc.s  7
0x1d18d  unbox.any [mscorlib]System.Int32
0x1d192  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::set_LocaleId(int32 value)
0x1d197  br.s     loc_1D1D5
0x1d199  ldloc.s  8
0x1d19b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1d1a0  beq.s    loc_1D1B2
0x1d1a2  ldloc.s  0xA
0x1d1a4  ldloc.s  8
0x1d1a6  unbox.any [mscorlib]System.Int32
0x1d1ab  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::set_LocaleId(int32 value)
0x1d1b0  br.s     loc_1D1D5
0x1d1b2  ldstr    aCouldNotFindLo// "Could not find locale for user : "
0x1d1b7  ldloc.s  0xA
0x1d1b9  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::get_FirstName()
0x1d1be  ldstr    asc_35406// " "
0x1d1c3  ldloc.s  0xA
0x1d1c5  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::get_LastName()
0x1d1ca  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1d1cf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1d1d4  throw
0x1d1d5  ldloc.s  9
0x1d1d7  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1d1dc  beq.s    loc_1D1EC
0x1d1de  ldloc.s  0xA
0x1d1e0  ldloc.s  9
0x1d1e2  unbox.any [mscorlib]System.Guid
0x1d1e7  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::set_SystemUserId(valuetype [mscorlib]System.Guid value)
0x1d1ec  ldarg.1
0x1d1ed  ldloc.s  0xA
0x1d1ef  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo>::Add(var<u1>)
0x1d1f4  ldloc.2
0x1d1f5  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x1d1fa  brtrue   loc_1D0BC
0x1d1ff  leave.s  loc_1D215
0x1d201  ldloc.2
0x1d202  brfalse.s loc_1D20A
0x1d204  ldloc.2
0x1d205  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d20a  endfinally
0x1d20b  ldloc.1
0x1d20c  brfalse.s loc_1D214
0x1d20e  ldloc.1
0x1d20f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d214  endfinally
0x1d215  ldloc.0
0x1d216  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x1d21b  leave.s  loc_1D227
0x1d21d  ldloc.0
0x1d21e  brfalse.s loc_1D226
0x1d220  ldloc.0
0x1d221  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d226  endfinally
0x1d227  ret
```
