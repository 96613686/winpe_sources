# Microsoft.Crm.Metadata.SecurityHelper::CreatePrivilegesForEntity

- ea: `0x59ab0`
- end: `0x59bd7`
- name: `Microsoft.Crm.Metadata.SecurityHelper::CreatePrivilegesForEntity`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x59990`

## callees

- `0x599e0`
- `0x59ab0`
- `0x5a390`
- `0x5a540`

## string_xrefs

- `0x59ae3`: `retrieveplugin`
- `0x59aeb`: `retrievemultipleplugin`
- `0x59af3`: `createplugin`
- `0x59afb`: `deleteplugin`
- `0x59b03`: `updateplugin`

## pseudocode

```c

```

## disassembly

```asm
0x59ab0  ldnull
0x59ab1  stloc.0
0x59ab2  ldarga.s 3
0x59ab4  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x59ab9  brfalse.s loc_59B2F
0x59abb  ldstr    aEntitydataprov// "EntityDataProvider"
0x59ac0  ldarg.s  6
0x59ac2  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x59ac7  stloc.2
0x59ac8  ldstr    aEntitydataprov// "EntityDataProvider"
0x59acd  ldarg.s  6
0x59acf  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x59ad4  stloc.3
0x59ad5  ldloc.3
0x59ad6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x59adb  ldc.i4.5
0x59adc  newarr   [mscorlib]System.String
0x59ae1  dup
0x59ae2  ldc.i4.0
0x59ae3  ldstr    aRetrieveplugin// "retrieveplugin"
0x59ae8  stelem.ref
0x59ae9  dup
0x59aea  ldc.i4.1
0x59aeb  ldstr    aRetrievemultip_0// "retrievemultipleplugin"
0x59af0  stelem.ref
0x59af1  dup
0x59af2  ldc.i4.2
0x59af3  ldstr    aCreateplugin// "createplugin"
0x59af8  stelem.ref
0x59af9  dup
0x59afa  ldc.i4.3
0x59afb  ldstr    aDeleteplugin// "deleteplugin"
0x59b00  stelem.ref
0x59b01  dup
0x59b02  ldc.i4.4
0x59b03  ldstr    aUpdateplugin// "updateplugin"
0x59b08  stelem.ref
0x59b09  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x59b0e  ldloc.2
0x59b0f  ldarga.s 3
0x59b11  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x59b16  ldstr    aEntitydataprov// "EntityDataProvider"
0x59b1b  ldarg.s  6
0x59b1d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x59b22  ldloc.3
0x59b23  ldarg.s  6
0x59b25  ldloca.s 0
0x59b27  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::TryRetrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity&)
0x59b2c  brtrue.s loc_59B2F
0x59b2e  ret
0x59b2f  ldarg.2
0x59b30  ldarg.0
0x59b31  call     valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth Microsoft.Crm.Metadata.SecurityHelper::GetDefaultDepth(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes ownershipTypeMask, string entityName)
0x59b36  stloc.1
0x59b37  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType
0x59b3c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x59b41  call     class [mscorlib]System.Array [mscorlib]System.Enum::GetValues(class [mscorlib]System.Type)
0x59b46  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Array::GetEnumerator()
0x59b4b  stloc.s  4
0x59b4d  br.s     loc_59BB6
0x59b4f  ldloc.s  4
0x59b51  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x59b56  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType
0x59b5b  stloc.s  5
0x59b5d  ldloc.s  5
0x59b5f  ldc.i4.m1
0x59b60  beq.s    loc_59BB6
0x59b62  ldloc.s  5
0x59b64  ldc.i4.s 9
0x59b66  beq.s    loc_59BB6
0x59b68  ldloc.s  5
0x59b6a  ldc.i4.4
0x59b6b  beq.s    loc_59B72
0x59b6d  ldloc.s  5
0x59b6f  ldc.i4.5
0x59b70  bne.un.s loc_59B76
0x59b72  ldc.i4.1
0x59b73  ldarg.2
0x59b74  bne.un.s loc_59BB6
0x59b76  ldarga.s 3
0x59b78  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x59b7d  brfalse.s loc_59B89
0x59b7f  ldloc.0
0x59b80  ldloc.s  5
0x59b82  call     bool Microsoft.Crm.Metadata.SecurityHelper::IsValidPrivilegeForVirtualEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity provider, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType t)
0x59b87  brfalse.s loc_59BB6
0x59b89  ldarg.2
0x59b8a  ldarg.1
0x59b8b  ldarg.0
0x59b8c  ldloc.s  5
0x59b8e  ldarg.s  6
0x59b90  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege Microsoft.Crm.Metadata.SecurityHelper::CreatePrivilege(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes ownershipTypeMask, int32 objectTypeCode, string entityName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType privilegeType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x59b95  stloc.s  6
0x59b97  ldloc.s  6
0x59b99  ldloc.1
0x59b9a  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::set_Depth(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth)
0x59b9f  ldarg.s  4
0x59ba1  ldloc.s  6
0x59ba3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege>::Add(var<u1>)
0x59ba8  ldloc.s  5
0x59baa  ldc.i4.1
0x59bab  bne.un.s loc_59BB6
0x59bad  ldarg.s  5
0x59baf  ldloc.s  6
0x59bb1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege>::Add(var<u1>)
0x59bb6  ldloc.s  4
0x59bb8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x59bbd  brtrue.s loc_59B4F
0x59bbf  leave.s  loc_59BD6
0x59bc1  ldloc.s  4
0x59bc3  isinst   [mscorlib]System.IDisposable
0x59bc8  stloc.s  7
0x59bca  ldloc.s  7
0x59bcc  brfalse.s loc_59BD5
0x59bce  ldloc.s  7
0x59bd0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x59bd5  endfinally
0x59bd6  ret
```
