# Microsoft.Crm.BusinessEntities.SecurityLibrary::GetOwningUserDataList

- ea: `0x64630`
- end: `0x64762`
- name: `Microsoft.Crm.BusinessEntities.SecurityLibrary::GetOwningUserDataList`
- size: `306`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x63a50`
- `0x64770`

## callees

- `0x61160`
- `0x64630`
- `0x67920`

## string_xrefs

- `0x64645`: `p_GetAccessRights`
- `0x64690`: `@AccessRights`
- `0x64724`: `AccessRights`

## pseudocode

```c

```

## disassembly

```asm
0x64630  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype OwningUserData>::.ctor()
0x64635  stloc.0
0x64636  ldarg.0
0x64637  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x6463c  stloc.1
0x6463d  ldloc.1
0x6463e  ldc.i4.4
0x6463f  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x64644  ldloc.1
0x64645  ldstr    aPGetaccessrigh// "p_GetAccessRights"
0x6464a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6464f  ldloc.1
0x64650  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x64655  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x6465a  dup
0x6465b  ldstr    aDoc// "@doc"
0x64660  ldarg.2
0x64661  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x64666  pop
0x64667  dup
0x64668  ldstr    aUserid_1// "@UserId"
0x6466d  ldarg.1
0x6466e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x64673  box      [mscorlib]System.Guid
0x64678  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6467d  pop
0x6467e  dup
0x6467f  ldstr    aObjecttypecode_86// "@ObjectTypeCode"
0x64684  ldarg.3
0x64685  box      [mscorlib]System.Int32
0x6468a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6468f  pop
0x64690  ldstr    aAccessrights// "@AccessRights"
0x64695  ldarg.s  4
0x64697  box      [mscorlib]System.Int32
0x6469c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x646a1  pop
0x646a2  ldloc.1
0x646a3  ldc.i4   0xCA5
0x646a8  ldstr    aGetowninguserd// "GetOwningUserDataList"
0x646ad  ldstr    aDA1SSrcManaged_15// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x646b2  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x646b7  stloc.2
0x646b8  br       loc_6473F
0x646bd  ldloca.s 3
0x646bf  initobj  OwningUserData
0x646c5  ldloca.s 3
0x646c7  ldloc.2
0x646c8  ldstr    aOwnerid_1// "OwnerId"
0x646cd  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x646d2  unbox.any [mscorlib]System.Guid
0x646d7  stfld    valuetype [mscorlib]System.Guid OwningUserData::OwnerId
0x646dc  ldloca.s 3
0x646de  ldloc.2
0x646df  ldstr    aOwneridtype_0// "OwnerIdType"
0x646e4  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x646e9  unbox.any [mscorlib]System.Int32
0x646ee  stfld    int32 OwningUserData::OwnerIdType
0x646f3  ldloca.s 3
0x646f5  ldloc.2
0x646f6  ldstr    aEntityid_2// "EntityId"
0x646fb  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x64700  unbox.any [mscorlib]System.Guid
0x64705  stfld    valuetype [mscorlib]System.Guid OwningUserData::EntityId
0x6470a  ldloca.s 3
0x6470c  ldloc.2
0x6470d  ldstr    aEntitybusiness// "EntityBusinessUnitId"
0x64712  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x64717  unbox.any [mscorlib]System.Guid
0x6471c  stfld    valuetype [mscorlib]System.Guid OwningUserData::EntityBusinessUnitId
0x64721  ldloca.s 3
0x64723  ldloc.2
0x64724  ldstr    aAccessrights_0// "AccessRights"
0x64729  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x6472e  unbox.any [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights
0x64733  stfld    valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights OwningUserData::AccessRightsRetrieved
0x64738  ldloc.0
0x64739  ldloc.3
0x6473a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype OwningUserData>::Add(var<u1>)
0x6473f  ldloc.2
0x64740  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x64745  brtrue   loc_646BD
0x6474a  leave.s  loc_64760
0x6474c  ldloc.2
0x6474d  brfalse.s loc_64755
0x6474f  ldloc.2
0x64750  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x64755  endfinally
0x64756  ldloc.1
0x64757  brfalse.s loc_6475F
0x64759  ldloc.1
0x6475a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6475f  endfinally
0x64760  ldloc.0
0x64761  ret
```
