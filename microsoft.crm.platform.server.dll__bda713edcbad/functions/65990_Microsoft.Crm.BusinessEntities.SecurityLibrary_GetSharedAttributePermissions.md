# Microsoft.Crm.BusinessEntities.SecurityLibrary::GetSharedAttributePermissions

- ea: `0x65990`
- end: `0x65aad`
- name: `Microsoft.Crm.BusinessEntities.SecurityLibrary::GetSharedAttributePermissions`
- size: `285`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x653e0`
- `0x657f0`

## callees

- `0x5d570`
- `0x61160`
- `0x611a0`
- `0x65990`
- `0x66b00`

## string_xrefs

- `0x65998`: `select poaa.ReadAccess, poaa.UpdateAccess\nfrom PrincipalObjectAttributeAccessBase poaa with (nolock)\nwhere poaa.ObjectId = @ObjectId and poaa.ObjectTypeCode = @ObjectTypeCode\n   and poaa.AttributeId = @AttributeId	\n   and poaa.PrincipalId = @PrincipalId`
- `0x6599f`: `select cast(MAX(cast(poaa.ReadAccess as tinyint)) as bit) as ReadAccess, \n		cast(MAX(cast(poaa.UpdateAccess as tinyint)) as bit) as UpdateAccess  \nfrom PrincipalObjectAttributeAccessBase poaa with (nolock)\njoin SystemUserPrincipals sup with (nolock) on sup.PrincipalId = poaa.PrincipalId\nwhere poaa.ObjectId = @ObjectId and poaa.ObjectTypeCode = @ObjectTypeCode\n   and poaa.AttributeId = @AttributeId	\n   and sup.SystemUserId = @PrincipalId`
- `0x65a22`: `readaccess`
- `0x65a2f`: `readaccess`
- `0x65a48`: `updateaccess`
- `0x65a55`: `updateaccess`

## pseudocode

```c

```

## disassembly

```asm
0x65990  ldarg.0
0x65991  callvirt instance bool Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_IsUserPrincipal()
0x65996  brtrue.s loc_6599F
0x65998  ldstr    aSelectPoaaRead// "select poaa.ReadAccess, poaa.UpdateAcce"...
0x6599d  br.s     loc_659A4
0x6599f  ldstr    aSelectCastMaxC// "select cast(MAX(cast(poaa.ReadAccess as"...
0x659a4  stloc.0
0x659a5  ldarg.s  4
0x659a7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x659ac  ldloc.0
0x659ad  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x659b2  stloc.1
0x659b3  ldloc.1
0x659b4  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x659b9  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x659be  dup
0x659bf  ldstr    aObjectid_3// "@ObjectId"
0x659c4  ldarg.1
0x659c5  box      [mscorlib]System.Guid
0x659ca  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x659cf  pop
0x659d0  dup
0x659d1  ldstr    aObjecttypecode_86// "@ObjectTypeCode"
0x659d6  ldarg.2
0x659d7  box      [mscorlib]System.Int32
0x659dc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x659e1  pop
0x659e2  dup
0x659e3  ldstr    aAttributeid_2// "@AttributeId"
0x659e8  ldarg.3
0x659e9  box      [mscorlib]System.Guid
0x659ee  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x659f3  pop
0x659f4  ldstr    aPrincipalid_1// "@PrincipalId"
0x659f9  ldarg.0
0x659fa  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x659ff  box      [mscorlib]System.Guid
0x65a04  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x65a09  pop
0x65a0a  ldarg.s  4
0x65a0c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x65a11  ldloc.1
0x65a12  ldarg.s  4
0x65a14  call     class [System.Data]System.Data.IDataReader Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteQuery(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection dbConnection, class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x65a19  stloc.2
0x65a1a  br.s     loc_65A82
0x65a1c  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x65a21  ldloc.2
0x65a22  ldstr    aReadaccess// "readaccess"
0x65a27  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x65a2c  beq.s    loc_65A40
0x65a2e  ldloc.2
0x65a2f  ldstr    aReadaccess// "readaccess"
0x65a34  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x65a39  unbox.any [mscorlib]System.Boolean
0x65a3e  br.s     loc_65A41
0x65a40  ldc.i4.0
0x65a41  stloc.3
0x65a42  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x65a47  ldloc.2
0x65a48  ldstr    aUpdateaccess// "updateaccess"
0x65a4d  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x65a52  beq.s    loc_65A66
0x65a54  ldloc.2
0x65a55  ldstr    aUpdateaccess// "updateaccess"
0x65a5a  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x65a5f  unbox.any [mscorlib]System.Boolean
0x65a64  br.s     loc_65A67
0x65a66  ldc.i4.0
0x65a67  stloc.s  4
0x65a69  ldc.i4.0
0x65a6a  ldloc.3
0x65a6b  brtrue.s loc_65A70
0x65a6d  ldc.i4.0
0x65a6e  br.s     loc_65A71
0x65a70  ldc.i4.4
0x65a71  ldloc.s  4
0x65a73  brtrue.s loc_65A78
0x65a75  ldc.i4.0
0x65a76  br.s     loc_65A79
0x65a78  ldc.i4.4
0x65a79  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.AttributePermissions::.ctor(int32, int32, int32)
0x65a7e  stloc.s  5
0x65a80  leave.s  loc_65AAA
0x65a82  ldloc.2
0x65a83  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x65a88  brtrue.s loc_65A1C
0x65a8a  ldc.i4.0
0x65a8b  ldc.i4.0
0x65a8c  ldc.i4.0
0x65a8d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.AttributePermissions::.ctor(int32, int32, int32)
0x65a92  stloc.s  5
0x65a94  leave.s  loc_65AAA
0x65a96  ldloc.2
0x65a97  brfalse.s loc_65A9F
0x65a99  ldloc.2
0x65a9a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x65a9f  endfinally
0x65aa0  ldloc.1
0x65aa1  brfalse.s loc_65AA9
0x65aa3  ldloc.1
0x65aa4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x65aa9  endfinally
0x65aaa  ldloc.s  5
0x65aac  ret
```
