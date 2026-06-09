# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::GetAllRoles

- ea: `0x1f5f0`
- end: `0x1f706`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::GetAllRoles`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1f5f0`

## string_xrefs

- `0x1f61e`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\OrganizationDatabaseAccess.cs`
- `0x1f651`: `RoleTemplateId`
- `0x1f658`: `RoleTemplateId`
- `0x1f666`: `RoleTemplateId`
- `0x1f683`: `RoleTemplateId`
- `0x1f5f6`: `SELECT RoleId, RoleTemplateId, Name, BusinessUnitId FROM RoleBase`

## pseudocode

```c

```

## disassembly

```asm
0x1f5f0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::.ctor()
0x1f5f5  stloc.0
0x1f5f6  ldstr    aSelectRoleidRo// "SELECT RoleId, RoleTemplateId, Name, Bu"...
0x1f5fb  stloc.1
0x1f5fc  ldarg.1
0x1f5fd  ldc.i4.0
0x1f5fe  ldc.i4.0
0x1f5ff  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1f604  stloc.2
0x1f605  ldloc.2
0x1f606  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1f60b  ldloc.2
0x1f60c  ldloc.1
0x1f60d  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x1f612  stloc.3
0x1f613  ldloc.3
0x1f614  ldc.i4   0xA91
0x1f619  ldstr    aGetallroles// "GetAllRoles"
0x1f61e  ldstr    aDDbsShDccm2110_31// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x1f623  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x1f628  stloc.s  4
0x1f62a  br       loc_1F6D6
0x1f62f  ldc.i4.1
0x1f630  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor(bool)
0x1f635  stloc.s  5
0x1f637  ldloc.s  5
0x1f639  ldstr    aRolename// "RoleName"
0x1f63e  ldloc.s  4
0x1f640  ldstr    aName// "Name"
0x1f645  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1f64a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1f64f  ldloc.s  5
0x1f651  ldstr    aRoletemplateid_2// "RoleTemplateId"
0x1f656  ldloc.s  4
0x1f658  ldstr    aRoletemplateid_2// "RoleTemplateId"
0x1f65d  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1f662  brfalse.s loc_1F68F
0x1f664  ldloc.s  4
0x1f666  ldstr    aRoletemplateid_2// "RoleTemplateId"
0x1f66b  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1f670  callvirt instance string [mscorlib]System.Object::ToString()
0x1f675  ldsfld   string [mscorlib]System.String::Empty
0x1f67a  call     bool [mscorlib]System.String::Equals(string, string)
0x1f67f  brtrue.s loc_1F68F
0x1f681  ldloc.s  4
0x1f683  ldstr    aRoletemplateid_2// "RoleTemplateId"
0x1f688  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1f68d  br.s     loc_1F699
0x1f68f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f694  box      [mscorlib]System.Guid
0x1f699  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1f69e  ldloc.s  5
0x1f6a0  ldstr    aRoleid// "RoleId"
0x1f6a5  ldloc.s  4
0x1f6a7  ldstr    aRoleid// "RoleId"
0x1f6ac  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1f6b1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1f6b6  ldloc.s  5
0x1f6b8  ldstr    aBusinessunitid_0// "BusinessUnitId"
0x1f6bd  ldloc.s  4
0x1f6bf  ldstr    aBusinessunitid_0// "BusinessUnitId"
0x1f6c4  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1f6c9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1f6ce  ldloc.0
0x1f6cf  ldloc.s  5
0x1f6d1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>)
0x1f6d6  ldloc.s  4
0x1f6d8  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x1f6dd  brtrue   loc_1F62F
0x1f6e2  leave.s  loc_1F704
0x1f6e4  ldloc.s  4
0x1f6e6  brfalse.s loc_1F6EF
0x1f6e8  ldloc.s  4
0x1f6ea  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f6ef  endfinally
0x1f6f0  ldloc.3
0x1f6f1  brfalse.s loc_1F6F9
0x1f6f3  ldloc.3
0x1f6f4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f6f9  endfinally
0x1f6fa  ldloc.2
0x1f6fb  brfalse.s loc_1F703
0x1f6fd  ldloc.2
0x1f6fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f703  endfinally
0x1f704  ldloc.0
0x1f705  ret
```
