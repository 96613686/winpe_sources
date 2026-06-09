# Microsoft.Crm.ObjectModel.RoleServiceInternal`1::AddPrivilegesToUserRole

- ea: `0xd1a90`
- end: `0xd1c3f`
- name: `Microsoft.Crm.ObjectModel.RoleServiceInternal`1::AddPrivilegesToUserRole`
- size: `431`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0xd1a90`

## string_xrefs

- `0xd1aa8`: `AddPrivilegesToUserRole`
- `0xd1bb9`: `AddPrivilegesToUserRole`
- `0xd1aad`: `D:\a\1\s\src\Core\ObjectModel\Services\BusinessManagement\RoleService.cs`
- `0xd1bbe`: `D:\a\1\s\src\Core\ObjectModel\Services\BusinessManagement\RoleService.cs`
- `0xd1ac4`: `select RoleId from Role where BusinessUnitId = @BusinessUnitId and RoleTemplateId in (`
- `0xd1ad5`: `@TemplateId`
- `0xd1b5d`: `@TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0xd1a90  ldarg.3
0xd1a91  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0xd1a96  stloc.0
0xd1a97  ldloc.0
0xd1a98  ldstr    aSelectBusiness// "select BusinessUnitId from BusinessUnit"...
0xd1a9d  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xd1aa2  ldloc.0
0xd1aa3  ldc.i4   0x153
0xd1aa8  ldstr    aAddprivilegest// "AddPrivilegesToUserRole"
0xd1aad  ldstr    aDA1SSrcCoreObj_22// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0xd1ab2  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xd1ab7  unbox.any [mscorlib]System.Guid
0xd1abc  stloc.1
0xd1abd  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xd1ac2  stloc.2
0xd1ac3  ldloc.2
0xd1ac4  ldstr    aSelectRoleidFr// "select RoleId from Role where BusinessU"...
0xd1ac9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd1ace  pop
0xd1acf  ldc.i4.0
0xd1ad0  stloc.s  5
0xd1ad2  br.s     loc_D1B04
0xd1ad4  ldloc.2
0xd1ad5  ldstr    aTemplateid_0// "@TemplateId"
0xd1ada  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd1adf  pop
0xd1ae0  ldloc.2
0xd1ae1  ldloc.s  5
0xd1ae3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0xd1ae8  pop
0xd1ae9  ldloc.s  5
0xd1aeb  ldarg.2
0xd1aec  ldlen
0xd1aed  conv.i4
0xd1aee  ldc.i4.1
0xd1aef  sub
0xd1af0  beq.s    loc_D1AFE
0xd1af2  ldloc.2
0xd1af3  ldstr    asc_24F050// ","
0xd1af8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd1afd  pop
0xd1afe  ldloc.s  5
0xd1b00  ldc.i4.1
0xd1b01  add
0xd1b02  stloc.s  5
0xd1b04  ldloc.s  5
0xd1b06  ldarg.2
0xd1b07  ldlen
0xd1b08  conv.i4
0xd1b09  blt.s    loc_D1AD4
0xd1b0b  ldloc.2
0xd1b0c  ldstr    asc_24F202// ")"
0xd1b11  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd1b16  pop
0xd1b17  ldloc.0
0xd1b18  ldloc.2
0xd1b19  callvirt instance string [mscorlib]System.Object::ToString()
0xd1b1e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xd1b23  ldloc.0
0xd1b24  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xd1b29  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xd1b2e  stloc.3
0xd1b2f  ldloc.0
0xd1b30  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xd1b35  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xd1b3a  stloc.3
0xd1b3b  ldloc.3
0xd1b3c  ldstr    aBusinessunitid_0// "@BusinessUnitId"
0xd1b41  ldloc.1
0xd1b42  box      [mscorlib]System.Guid
0xd1b47  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd1b4c  pop
0xd1b4d  ldc.i4.0
0xd1b4e  stloc.s  6
0xd1b50  br.s     loc_D1B81
0xd1b52  ldarg.2
0xd1b53  ldloc.s  6
0xd1b55  ldelem   [mscorlib]System.Guid
0xd1b5a  stloc.s  7
0xd1b5c  ldloc.3
0xd1b5d  ldstr    aTemplateid_0// "@TemplateId"
0xd1b62  ldloc.s  6
0xd1b64  box      [mscorlib]System.Int32
0xd1b69  call     string [mscorlib]System.String::Concat(object, object)
0xd1b6e  ldloc.s  7
0xd1b70  box      [mscorlib]System.Guid
0xd1b75  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd1b7a  pop
0xd1b7b  ldloc.s  6
0xd1b7d  ldc.i4.1
0xd1b7e  add
0xd1b7f  stloc.s  6
0xd1b81  ldloc.s  6
0xd1b83  ldarg.2
0xd1b84  ldlen
0xd1b85  conv.i4
0xd1b86  blt.s    loc_D1B52
0xd1b88  ldarg.2
0xd1b89  ldlen
0xd1b8a  conv.i4
0xd1b8b  newarr   [mscorlib]System.Guid
0xd1b90  stloc.s  4
0xd1b92  ldc.i4.0
0xd1b93  stloc.s  8
0xd1b95  br.s     loc_D1BAB
0xd1b97  ldloc.s  4
0xd1b99  ldloc.s  8
0xd1b9b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd1ba0  stelem   [mscorlib]System.Guid
0xd1ba5  ldloc.s  8
0xd1ba7  ldc.i4.1
0xd1ba8  add
0xd1ba9  stloc.s  8
0xd1bab  ldloc.s  8
0xd1bad  ldloc.s  4
0xd1baf  ldlen
0xd1bb0  conv.i4
0xd1bb1  blt.s    loc_D1B97
0xd1bb3  ldloc.0
0xd1bb4  ldc.i4   0x175
0xd1bb9  ldstr    aAddprivilegest// "AddPrivilegesToUserRole"
0xd1bbe  ldstr    aDA1SSrcCoreObj_22// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0xd1bc3  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xd1bc8  stloc.s  9
0xd1bca  ldc.i4.0
0xd1bcb  stloc.s  0xA
0xd1bcd  br.s     loc_D1BEF
0xd1bcf  ldloc.s  4
0xd1bd1  ldloc.s  0xA
0xd1bd3  ldloc.s  9
0xd1bd5  ldstr    aRoleid_2// "RoleId"
0xd1bda  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xd1bdf  unbox.any [mscorlib]System.Guid
0xd1be4  stelem   [mscorlib]System.Guid
0xd1be9  ldloc.s  0xA
0xd1beb  ldc.i4.1
0xd1bec  add
0xd1bed  stloc.s  0xA
0xd1bef  ldloc.s  9
0xd1bf1  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xd1bf6  brtrue.s loc_D1BCF
0xd1bf8  leave.s  loc_D1C06
0xd1bfa  ldloc.s  9
0xd1bfc  brfalse.s loc_D1C05
0xd1bfe  ldloc.s  9
0xd1c00  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd1c05  endfinally
0xd1c06  ldloc.s  4
0xd1c08  stloc.s  0xB
0xd1c0a  ldc.i4.0
0xd1c0b  stloc.s  0xC
0xd1c0d  br.s     loc_D1C2A
0xd1c0f  ldloc.s  0xB
0xd1c11  ldloc.s  0xC
0xd1c13  ldelem   [mscorlib]System.Guid
0xd1c18  stloc.s  0xD
0xd1c1a  ldarg.0
0xd1c1b  ldloc.s  0xD
0xd1c1d  ldarg.1
0xd1c1e  ldarg.3
0xd1c1f  call     instance void class Microsoft.Crm.ObjectModel.RoleServiceInternal`1<var<u1>>::AddNewPrivilegesToExistingRole(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd1c24  ldloc.s  0xC
0xd1c26  ldc.i4.1
0xd1c27  add
0xd1c28  stloc.s  0xC
0xd1c2a  ldloc.s  0xC
0xd1c2c  ldloc.s  0xB
0xd1c2e  ldlen
0xd1c2f  conv.i4
0xd1c30  blt.s    loc_D1C0F
0xd1c32  leave.s  loc_D1C3E
0xd1c34  ldloc.0
0xd1c35  brfalse.s loc_D1C3D
0xd1c37  ldloc.0
0xd1c38  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd1c3d  endfinally
0xd1c3e  ret
```
