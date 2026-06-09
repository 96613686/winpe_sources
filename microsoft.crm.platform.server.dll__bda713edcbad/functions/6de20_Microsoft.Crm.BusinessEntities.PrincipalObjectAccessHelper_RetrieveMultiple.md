# Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::RetrieveMultiple

- ea: `0x6de20`
- end: `0x6df91`
- name: `Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::RetrieveMultiple`
- size: `369`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x5cdf0`
- `0x5f770`
- `0x6e140`
- `0x6e390`

## callees

- `0x66af0`
- `0x66b00`
- `0x6de20`

## string_xrefs

- `0x6de36`: `PrincipalObjectAccess`
- `0x6deb8`: `PrincipalObjectAccess`
- `0x6df19`: `accessrightsmask`
- `0x6df3b`: `inheritedaccessrightsmask`
- `0x6dea7`: `D:\a\1\s\src\ManagedPlatform\Server\PrincipalObjectAccessHelper.cs`
- `0x6df20`: `AccessRightsMask`
- `0x6df42`: `InheritedAccessRightsMask`
- `0x6de4f`: `SELECT PrincipalId, PrincipalTypeCode, ObjectTypeCode, AccessRightsMask, InheritedAccessRightsMask FROM PrincipalObjectAccess\n					WHERE ObjectId = @ObjectId AND ObjectTypeCode = @ObjectTypeCode AND AccessRightsMask <> 0 AND AccessRightsMask IS NOT NULL`

## pseudocode

```c

```

## disassembly

```asm
0x6de20  ldarg.2
0x6de21  ldstr    aExecutionconte_3// "ExecutionContext"
0x6de26  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6de2b  ldarg.0
0x6de2c  ldstr    aEntityid// "entityId"
0x6de31  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x6de36  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x6de3b  ldarg.2
0x6de3c  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6de41  stloc.0
0x6de42  ldarg.2
0x6de43  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x6de48  stloc.1
0x6de49  ldloc.1
0x6de4a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x6de4f  ldstr    aSelectPrincipa// "SELECT PrincipalId, PrincipalTypeCode, "...
0x6de54  stloc.2
0x6de55  ldloc.1
0x6de56  ldloc.2
0x6de57  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x6de5c  stloc.3
0x6de5d  ldloc.3
0x6de5e  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x6de63  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x6de68  dup
0x6de69  ldstr    aObjectid_3// "@ObjectId"
0x6de6e  ldarg.0
0x6de6f  box      [mscorlib]System.Guid
0x6de74  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6de79  pop
0x6de7a  ldstr    aObjecttypecode_86// "@ObjectTypeCode"
0x6de7f  ldarg.1
0x6de80  box      [mscorlib]System.Int32
0x6de85  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6de8a  pop
0x6de8b  ldloc.3
0x6de8c  ldarg.2
0x6de8d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x6de92  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::get_SqlTrans()
0x6de97  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::SetTransaction(class [System.Data]System.Data.IDbCommand, class [System.Data]System.Data.IDbTransaction)
0x6de9c  ldloc.3
0x6de9d  ldc.i4   0xCE
0x6dea2  ldstr    aRetrievemultip_6// "RetrieveMultiple"
0x6dea7  ldstr    aDA1SSrcManaged_16// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x6deac  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x6deb1  stloc.s  4
0x6deb3  br       loc_6DF64
0x6deb8  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x6debd  ldarg.2
0x6debe  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6dec3  stloc.s  5
0x6dec5  ldloc.s  5
0x6dec7  ldstr    aPrincipalid// "principalid"
0x6decc  ldloc.s  4
0x6dece  ldstr    aPrincipalid_2// "PrincipalId"
0x6ded3  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x6ded8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6dedd  ldloc.s  5
0x6dedf  ldstr    aPrincipaltypec// "principaltypecode"
0x6dee4  ldloc.s  4
0x6dee6  ldstr    aPrincipaltypec_1// "PrincipalTypeCode"
0x6deeb  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x6def0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6def5  ldloc.s  5
0x6def7  ldstr    aObjecttypecode_81// "objecttypecode"
0x6defc  ldloc.s  4
0x6defe  ldstr    aObjecttypecode_85// "ObjectTypeCode"
0x6df03  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x6df08  unbox.any [mscorlib]System.Int32
0x6df0d  box      [mscorlib]System.Int32
0x6df12  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6df17  ldloc.s  5
0x6df19  ldstr    aAccessrightsma// "accessrightsmask"
0x6df1e  ldloc.s  4
0x6df20  ldstr    aAccessrightsma_1// "AccessRightsMask"
0x6df25  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x6df2a  unbox.any [mscorlib]System.Int32
0x6df2f  box      [mscorlib]System.Int32
0x6df34  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6df39  ldloc.s  5
0x6df3b  ldstr    aInheritedacces// "inheritedaccessrightsmask"
0x6df40  ldloc.s  4
0x6df42  ldstr    aInheritedacces_1// "InheritedAccessRightsMask"
0x6df47  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x6df4c  unbox.any [mscorlib]System.Int32
0x6df51  box      [mscorlib]System.Int32
0x6df56  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6df5b  ldloc.0
0x6df5c  ldloc.s  5
0x6df5e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x6df63  pop
0x6df64  ldloc.s  4
0x6df66  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x6df6b  brtrue   loc_6DEB8
0x6df70  leave.s  loc_6DF8F
0x6df72  ldloc.s  4
0x6df74  brfalse.s loc_6DF7D
0x6df76  ldloc.s  4
0x6df78  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6df7d  endfinally
0x6df7e  ldloc.3
0x6df7f  brfalse.s loc_6DF87
0x6df81  ldloc.3
0x6df82  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6df87  endfinally
0x6df88  ldloc.1
0x6df89  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x6df8e  endfinally
0x6df8f  ldloc.0
0x6df90  ret
```
