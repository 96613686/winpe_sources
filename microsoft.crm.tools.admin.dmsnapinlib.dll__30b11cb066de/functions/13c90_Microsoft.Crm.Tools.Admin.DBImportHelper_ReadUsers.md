# Microsoft.Crm.Tools.Admin.DBImportHelper::ReadUsers

- ea: `0x13c90`
- end: `0x13d90`
- name: `Microsoft.Crm.Tools.Admin.DBImportHelper::ReadUsers`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x12490`

## callees

- `0x13c90`
- `0x13d90`
- `0x13e80`
- `0x197b0`

## string_xrefs

- `0x13cc8`: `SELECT usr.SystemUserId AS SystemUserId,\n	   FirstName,\n	   LastName,\n	   FullName,\n	   r.Name + ' [' + bu.Name + ']' AS Role,\n	   DomainName,\n	   ActiveDirectoryGuid,\n	   usr.IsDisabled AS IsDisabled,\n	   AccessMode,\n	   IsActiveDirectoryUser,\n	   r.RoleTemplateId AS RoleTemplateId\nFROM SystemUserBase usr\nLEFT OUTER JOIN SystemUserRoles ur ON usr.SystemUserId = ur.SystemUserId\nLEFT OUTER JOIN ROLE r ON r.RoleId = ur.RoleId\nLEFT OUTER JOIN BusinessUnitBase bu ON r.Bus`

## pseudocode

```c

```

## disassembly

```asm
0x13c90  ldarg.1
0x13c91  conv.r8
0x13c92  ldc.r8   0.01
0x13c9b  mul
0x13c9c  call     int32 [mscorlib]System.Convert::ToInt32(float64)
0x13ca1  stloc.0
0x13ca2  ldloc.0
0x13ca3  ldc.i4.1
0x13ca4  blt.s    loc_13CA9
0x13ca6  ldloc.0
0x13ca7  br.s     loc_13CAA
0x13ca9  ldc.i4.1
0x13caa  stloc.0
0x13cab  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User>::.ctor()
0x13cb0  stloc.1
0x13cb1  ldarg.3
0x13cb2  ldarg.s  4
0x13cb4  call     class [System.Data]System.Data.SqlClient.SqlConnection [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.SqlUtility::GetConnection(string, string)
0x13cb9  stloc.2
0x13cba  ldloc.2
0x13cbb  callvirt instance void [System.Data]System.Data.Common.DbConnection::Open()
0x13cc0  ldloc.2
0x13cc1  callvirt instance class [System.Data]System.Data.SqlClient.SqlCommand [System.Data]System.Data.SqlClient.SqlConnection::CreateCommand()
0x13cc6  stloc.3
0x13cc7  ldloc.3
0x13cc8  ldstr    aSelectUsrSyste// "SELECT usr.SystemUserId AS SystemUserId"...
0x13ccd  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x13cd2  ldloc.3
0x13cd3  ldc.i4.1
0x13cd4  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x13cd9  ldloc.3
0x13cda  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0x13cdf  stloc.s  4
0x13ce1  ldc.i4.0
0x13ce2  stloc.s  5
0x13ce4  br.s     loc_13D4D
0x13ce6  ldloc.s  5
0x13ce8  ldc.i4.1
0x13ce9  add
0x13cea  stloc.s  5
0x13cec  ldloc.s  4
0x13cee  ldstr    aSystemuserid_0// "SystemUserId"
0x13cf3  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x13cf8  unbox.any [mscorlib]System.Guid
0x13cfd  stloc.s  6
0x13cff  ldloc.1
0x13d00  ldloc.s  6
0x13d02  ldloca.s 7
0x13d04  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User>::TryGetValue(var<u1>, !!T0)
0x13d09  brtrue.s loc_13D32
0x13d0b  ldloc.s  4
0x13d0d  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User Microsoft.Crm.Tools.Admin.DBImportHelper::ReadUser(class [System.Data]System.Data.IDataReader reader)
0x13d12  stloc.s  7
0x13d14  ldloc.s  7
0x13d16  ldloc.s  6
0x13d18  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_DBSystemUserId(valuetype [mscorlib]System.Guid)
0x13d1d  ldloc.1
0x13d1e  ldloc.s  6
0x13d20  ldloc.s  7
0x13d22  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User>::Add(var<u1>, !!T0)
0x13d27  ldarg.2
0x13d28  brfalse.s loc_13D32
0x13d2a  ldarg.2
0x13d2b  ldloc.s  7
0x13d2d  callvirt instance void UserAccountMapper::Invoke(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User user)
0x13d32  ldloc.s  4
0x13d34  ldloc.s  7
0x13d36  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::AppendRole(class [System.Data]System.Data.IDataReader reader, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User user)
0x13d3b  ldarg.0
0x13d3c  brfalse.s loc_13D4D
0x13d3e  ldloc.s  5
0x13d40  ldloc.0
0x13d41  blt.s    loc_13D4D
0x13d43  ldarg.0
0x13d44  ldloc.0
0x13d45  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::IncrementProgress(int32)
0x13d4a  ldc.i4.0
0x13d4b  stloc.s  5
0x13d4d  ldloc.s  4
0x13d4f  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x13d54  brtrue.s loc_13CE6
0x13d56  ldloc.s  4
0x13d58  callvirt instance void [System.Data]System.Data.IDataReader::Close()
0x13d5d  leave.s  loc_13D7F
0x13d5f  ldloc.s  4
0x13d61  brfalse.s loc_13D6A
0x13d63  ldloc.s  4
0x13d65  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13d6a  endfinally
0x13d6b  ldloc.3
0x13d6c  brfalse.s loc_13D74
0x13d6e  ldloc.3
0x13d6f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13d74  endfinally
0x13d75  ldloc.2
0x13d76  brfalse.s loc_13D7E
0x13d78  ldloc.2
0x13d79  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13d7e  endfinally
0x13d7f  ldloc.1
0x13d80  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User>::get_Values()
0x13d85  call     T0x2B000019
0x13d8a  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x13d8f  ret
```
