# Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::GrantInheritedAccess_0

- ea: `0x6dff0`
- end: `0x6e131`
- name: `Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::GrantInheritedAccess_0`
- size: `321`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x57a40`
- `0x6dfa0`

## callees

- `0x61160`
- `0x61180`
- `0x61240`
- `0x66ae0`
- `0x66b00`
- `0x6daa0`
- `0x6dff0`

## string_xrefs

- `0x6e0a7`: `PrincipalObjectAccess`
- `0x6e104`: `accessrightsmask`
- `0x6e115`: `inheritedaccessrightsmask`
- `0x6e07b`: `D:\a\1\s\src\ManagedPlatform\Server\PrincipalObjectAccessHelper.cs`
- `0x6dff0`: `exec p_GrantInheritedAccess @referencingId, @referencingOTC, @referencedId, @referencedOTC`
- `0x6e076`: `GrantInheritedAccess`

## pseudocode

```c

```

## disassembly

```asm
0x6dff0  ldstr    aExecPGrantinhe// "exec p_GrantInheritedAccess @referencin"...
0x6dff5  stloc.0
0x6dff6  ldarg.s  6
0x6dff8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x6dffd  stloc.1
0x6dffe  ldloc.1
0x6dfff  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x6e004  ldloc.1
0x6e005  ldloc.0
0x6e006  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x6e00b  stloc.2
0x6e00c  ldloc.2
0x6e00d  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x6e012  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x6e017  dup
0x6e018  ldstr    aReferencingid// "@referencingId"
0x6e01d  ldarg.0
0x6e01e  box      [mscorlib]System.Guid
0x6e023  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6e028  pop
0x6e029  dup
0x6e02a  ldstr    aReferencingotc// "@referencingOTC"
0x6e02f  ldarg.1
0x6e030  box      [mscorlib]System.Int32
0x6e035  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6e03a  pop
0x6e03b  dup
0x6e03c  ldstr    aReferencedid// "@referencedId"
0x6e041  ldarg.2
0x6e042  box      [mscorlib]System.Guid
0x6e047  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6e04c  pop
0x6e04d  ldstr    aReferencedotc// "@referencedOTC"
0x6e052  ldarg.3
0x6e053  box      [mscorlib]System.Int32
0x6e058  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6e05d  pop
0x6e05e  ldloc.2
0x6e05f  ldarg.s  6
0x6e061  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x6e066  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_SqlTransaction()
0x6e06b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::SetTransaction(class [System.Data]System.Data.IDbCommand, class [System.Data]System.Data.IDbTransaction)
0x6e070  ldloc.2
0x6e071  ldc.i4   0x107
0x6e076  ldstr    aGrantinherited// "GrantInheritedAccess"
0x6e07b  ldstr    aDA1SSrcManaged_16// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x6e080  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x6e085  pop
0x6e086  leave.s  loc_6E099
0x6e088  ldloc.2
0x6e089  brfalse.s loc_6E091
0x6e08b  ldloc.2
0x6e08c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6e091  endfinally
0x6e092  ldloc.1
0x6e093  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x6e098  endfinally
0x6e099  ldarg.s  5
0x6e09b  ldarg.s  4
0x6e09d  call     bool Microsoft.Crm.BusinessEntities.SecurityPrincipal::IsEqual(class Microsoft.Crm.BusinessEntities.SecurityPrincipal principalOne, class Microsoft.Crm.BusinessEntities.SecurityPrincipal principalTwo)
0x6e0a2  brtrue   loc_6E130
0x6e0a7  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x6e0ac  ldarg.s  6
0x6e0ae  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6e0b3  dup
0x6e0b4  ldstr    aPrincipalid// "principalid"
0x6e0b9  ldarg.s  5
0x6e0bb  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x6e0c0  box      [mscorlib]System.Guid
0x6e0c5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6e0ca  dup
0x6e0cb  ldstr    aPrincipaltypec// "principaltypecode"
0x6e0d0  ldarg.s  5
0x6e0d2  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x6e0d7  box      [mscorlib]System.Int32
0x6e0dc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6e0e1  dup
0x6e0e2  ldstr    aObjectid// "objectid"
0x6e0e7  ldarg.0
0x6e0e8  box      [mscorlib]System.Guid
0x6e0ed  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6e0f2  dup
0x6e0f3  ldstr    aObjecttypecode_81// "objecttypecode"
0x6e0f8  ldarg.1
0x6e0f9  box      [mscorlib]System.Int32
0x6e0fe  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6e103  dup
0x6e104  ldstr    aAccessrightsma// "accessrightsmask"
0x6e109  ldc.i4.0
0x6e10a  box      [mscorlib]System.Int32
0x6e10f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6e114  dup
0x6e115  ldstr    aInheritedacces// "inheritedaccessrightsmask"
0x6e11a  ldc.i4   0x80D0017
0x6e11f  box      [mscorlib]System.Int32
0x6e124  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6e129  ldarg.s  6
0x6e12b  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::GrantAccess(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6e130  ret
```
