# Microsoft.Crm.BusinessEntities.CascadeEngine::RevokeInheritedAccessFromOldOwners

- ea: `0x5f900`
- end: `0x5fa2c`
- name: `Microsoft.Crm.BusinessEntities.CascadeEngine::RevokeInheritedAccessFromOldOwners`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x8d610`

## callees

- `0x5f900`
- `0x66ae0`
- `0x66b00`
- `0x78000`
- `0x78050`

## string_xrefs

- `0x5f900`: `UPDATE PrincipalObjectAccess SET InheritedAccessRightsMask = 0, ChangedOn=GETUTCDATE() WHERE ObjectId = @ObjectId AND ObjectTypeCode = @ObjectTypeCode`
- `0x5fa01`: `RevokeInheritedAccessFromOldOwners`

## pseudocode

```c

```

## disassembly

```asm
0x5f900  ldstr    aUpdatePrincipa// "UPDATE PrincipalObjectAccess SET Inheri"...
0x5f905  stloc.0
0x5f906  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x5f90b  stloc.1
0x5f90c  ldloc.1
0x5f90d  ldstr    aAndPrincipalid// " AND PrincipalId in ("
0x5f912  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5f917  pop
0x5f918  ldarg.1
0x5f919  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x5f91e  stloc.2
0x5f91f  br.s     loc_5F93B
0x5f921  ldloca.s 2
0x5f923  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x5f928  stloc.3
0x5f929  ldloc.1
0x5f92a  ldstr    a0D// "'{0:D}', "
0x5f92f  ldloc.3
0x5f930  box      [mscorlib]System.Guid
0x5f935  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x5f93a  pop
0x5f93b  ldloca.s 2
0x5f93d  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x5f942  brtrue.s loc_5F921
0x5f944  leave.s  loc_5F954
0x5f946  ldloca.s 2
0x5f948  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x5f94e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5f953  endfinally
0x5f954  ldloc.1
0x5f955  ldloc.1
0x5f956  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x5f95b  ldc.i4.2
0x5f95c  sub
0x5f95d  ldc.i4.2
0x5f95e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Remove(int32, int32)
0x5f963  pop
0x5f964  ldloc.1
0x5f965  ldstr    asc_CC192// ")"
0x5f96a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5f96f  pop
0x5f970  ldloc.0
0x5f971  ldloc.1
0x5f972  callvirt instance string [mscorlib]System.Object::ToString()
0x5f977  call     string [mscorlib]System.String::Concat(string, string)
0x5f97c  stloc.0
0x5f97d  ldarg.2
0x5f97e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x5f983  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x5f988  ldarg.2
0x5f989  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x5f98e  ldloc.0
0x5f98f  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x5f994  stloc.s  4
0x5f996  ldloc.s  4
0x5f998  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x5f99d  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x5f9a2  dup
0x5f9a3  ldstr    aObjectid_3// "@ObjectId"
0x5f9a8  ldarg.0
0x5f9a9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityAttributes::get_ObjectId()
0x5f9ae  box      [mscorlib]System.Guid
0x5f9b3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5f9b8  pop
0x5f9b9  ldstr    aObjecttypecode_86// "@ObjectTypeCode"
0x5f9be  ldarg.0
0x5f9bf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.SecurityAttributes::get_Metadata()
0x5f9c4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x5f9c9  brtrue.s loc_5F9D8
0x5f9cb  ldarg.0
0x5f9cc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.SecurityAttributes::get_Metadata()
0x5f9d1  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x5f9d6  br.s     loc_5F9DD
0x5f9d8  ldc.i4   0x1068
0x5f9dd  box      [mscorlib]System.Int32
0x5f9e2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5f9e7  pop
0x5f9e8  ldloc.s  4
0x5f9ea  ldarg.2
0x5f9eb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5f9f0  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_SqlTransaction()
0x5f9f5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::SetTransaction(class [System.Data]System.Data.IDbCommand, class [System.Data]System.Data.IDbTransaction)
0x5f9fa  ldloc.s  4
0x5f9fc  ldc.i4   0x7A8
0x5fa01  ldstr    aRevokeinherite// "RevokeInheritedAccessFromOldOwners"
0x5fa06  ldstr    aDA1SSrcManaged_13// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x5fa0b  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x5fa10  pop
0x5fa11  leave.s  loc_5FA2B
0x5fa13  ldloc.s  4
0x5fa15  brfalse.s loc_5FA1E
0x5fa17  ldloc.s  4
0x5fa19  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5fa1e  endfinally
0x5fa1f  ldarg.2
0x5fa20  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x5fa25  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x5fa2a  endfinally
0x5fa2b  ret
```
