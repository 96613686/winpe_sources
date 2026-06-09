# Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1::RetrievePrivilegeMaxDepthFromTeamRoles_1

- ea: `0xcfce0`
- end: `0xcfe57`
- name: `Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1::RetrievePrivilegeMaxDepthFromTeamRoles_1`
- size: `375`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0xcfce0`

## string_xrefs

- `0xcfdcd`: `privilegedepthmask`
- `0xcfd18`: `accessmode`
- `0xcfd85`: `privilegeid`
- `0xcfdb5`: `accessright`
- `0xcfd3e`: `exec p_RetrievePrivilegeMaxDepthFromTeamRoles @userId`
- `0xcfd8c`: `PrivilegeId`
- `0xcfdbc`: `AccessRight`
- `0xcfdd4`: `PrivilegeDepthMask`

## pseudocode

```c

```

## disassembly

```asm
0xcfce0  ldarg.1
0xcfce1  ldstr    aUserid_2// "userId"
0xcfce6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xcfceb  ldarg.2
0xcfcec  ldstr    aContext// "context"
0xcfcf1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xcfcf6  ldarga.s 3
0xcfcf8  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xcfcfd  brfalse.s loc_CFD08
0xcfcff  ldarga.s 3
0xcfd01  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xcfd06  brtrue.s loc_CFD2A
0xcfd08  ldc.i4.8
0xcfd09  ldarg.1
0xcfd0a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal::.ctor(int32, valuetype [mscorlib]System.Guid)
0xcfd0f  stloc.3
0xcfd10  ldarg.0
0xcfd11  ldloc.3
0xcfd12  ldarg.2
0xcfd13  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<var<u1>>::CheckReadPrivilegeAndAccess(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcfd18  ldstr    aAccessmode// "accessmode"
0xcfd1d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xcfd22  unbox.any [mscorlib]System.Int32
0xcfd27  stloc.0
0xcfd28  br.s     loc_CFD32
0xcfd2a  ldarga.s 3
0xcfd2c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xcfd31  stloc.0
0xcfd32  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::.ctor()
0xcfd37  stloc.1
0xcfd38  ldarg.2
0xcfd39  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0xcfd3e  ldstr    aExecPRetrievep_0// "exec p_RetrievePrivilegeMaxDepthFromTea"...
0xcfd43  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0xcfd48  stloc.s  4
0xcfd4a  ldloc.s  4
0xcfd4c  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xcfd51  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xcfd56  ldstr    aUserid// "@userId"
0xcfd5b  ldarg.1
0xcfd5c  box      [mscorlib]System.Guid
0xcfd61  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xcfd66  pop
0xcfd67  ldarg.2
0xcfd68  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0xcfd6d  ldloc.s  4
0xcfd6f  ldarg.2
0xcfd70  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteQuery(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection, class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcfd75  stloc.s  5
0xcfd77  br       loc_CFE19
0xcfd7c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xcfd81  stloc.s  6
0xcfd83  ldloc.s  6
0xcfd85  ldstr    aPrivilegeid// "privilegeid"
0xcfd8a  ldloc.s  5
0xcfd8c  ldstr    aPrivilegeid_0// "PrivilegeId"
0xcfd91  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xcfd96  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xcfd9b  ldloc.s  6
0xcfd9d  ldstr    aIsdisabledwhen// "isdisabledwhenintegrated"
0xcfda2  ldloc.s  5
0xcfda4  ldstr    aIsdisabledwhen_0// "IsDisabledWhenIntegrated"
0xcfda9  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xcfdae  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xcfdb3  ldloc.s  6
0xcfdb5  ldstr    aAccessright// "accessright"
0xcfdba  ldloc.s  5
0xcfdbc  ldstr    aAccessright_0// "AccessRight"
0xcfdc1  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xcfdc6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xcfdcb  ldloc.s  6
0xcfdcd  ldstr    aPrivilegedepth// "privilegedepthmask"
0xcfdd2  ldloc.s  5
0xcfdd4  ldstr    aPrivilegedepth_0// "PrivilegeDepthMask"
0xcfdd9  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xcfdde  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xcfde3  ldloc.s  6
0xcfde5  ldstr    aObjecttypecode// "objecttypecode"
0xcfdea  ldloc.s  5
0xcfdec  ldstr    aObjecttypecode_2// "ObjectTypeCode"
0xcfdf1  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xcfdf6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xcfdfb  ldloc.s  6
0xcfdfd  ldstr    aBusinessunitid// "businessunitid"
0xcfe02  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xcfe07  box      [mscorlib]System.Guid
0xcfe0c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xcfe11  ldloc.1
0xcfe12  ldloc.s  6
0xcfe14  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>)
0xcfe19  ldloc.s  5
0xcfe1b  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xcfe20  brtrue   loc_CFD7C
0xcfe25  leave.s  loc_CFE3F
0xcfe27  ldloc.s  5
0xcfe29  brfalse.s loc_CFE32
0xcfe2b  ldloc.s  5
0xcfe2d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcfe32  endfinally
0xcfe33  ldloc.s  4
0xcfe35  brfalse.s loc_CFE3E
0xcfe37  ldloc.s  4
0xcfe39  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcfe3e  endfinally
0xcfe3f  ldarg.0
0xcfe40  ldarg.1
0xcfe41  ldarg.2
0xcfe42  call     instance bool class Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<var<u1>>::CheckSpecialUser(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcfe47  stloc.2
0xcfe48  ldarg.0
0xcfe49  ldarg.2
0xcfe4a  ldloc.0
0xcfe4b  ldloc.2
0xcfe4c  ldloc.1
0xcfe4d  ldarg.s  4
0xcfe4f  ldarg.s  5
0xcfe51  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] class Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<var<u1>>::GetPrivilegeArrayFromCollection(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, int32, bool, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, bool, bool)
0xcfe56  ret
```
