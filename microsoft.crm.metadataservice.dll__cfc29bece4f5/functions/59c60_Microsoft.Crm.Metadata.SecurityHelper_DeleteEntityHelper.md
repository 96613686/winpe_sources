# Microsoft.Crm.Metadata.SecurityHelper::DeleteEntityHelper

- ea: `0x59c60`
- end: `0x59d1e`
- name: `Microsoft.Crm.Metadata.SecurityHelper::DeleteEntityHelper`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x31b10`

## callees

- `0x59c60`
- `0x59d20`
- `0x59d80`

## string_xrefs

- `0x59cb6`: `privilegeid`
- `0x59c7f`: `PrivilegeObjectTypeCodes`
- `0x59cfd`: `PrivilegeObjectTypeCodes`
- `0x59cee`: `RolePrivileges`
- `0x59d0e`: `Privilege`

## pseudocode

```c

```

## disassembly

```asm
0x59c60  ldstr    aPrincipalentit// "PrincipalEntityMap"
0x59c65  ldarg.0
0x59c66  ldc.i4.0
0x59c67  ldarg.3
0x59c68  call     int32 Microsoft.Crm.Metadata.SecurityHelper::DeleteByObjectTypeCode(string platformName, int32 objectTypeCode, bool throwIfRowCountZero, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x59c6d  pop
0x59c6e  ldstr    aSystemuserbusi// "SystemUserBusinessUnitEntityMap"
0x59c73  ldarg.0
0x59c74  ldc.i4.0
0x59c75  ldarg.3
0x59c76  call     int32 Microsoft.Crm.Metadata.SecurityHelper::DeleteByObjectTypeCode(string platformName, int32 objectTypeCode, bool throwIfRowCountZero, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x59c7b  pop
0x59c7c  ldarg.1
0x59c7d  brfalse.s loc_59C8E
0x59c7f  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCodes"
0x59c84  ldarg.0
0x59c85  ldc.i4.1
0x59c86  ldarg.3
0x59c87  call     int32 Microsoft.Crm.Metadata.SecurityHelper::DeleteByObjectTypeCode(string platformName, int32 objectTypeCode, bool throwIfRowCountZero, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x59c8c  pop
0x59c8d  ret
0x59c8e  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisionPrivilegeService::.ctor()
0x59c93  ldarg.3
0x59c94  ldarg.0
0x59c95  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOn>::RetrievePrivilegeSetForEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, int32)
0x59c9a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x59c9f  stloc.0
0x59ca0  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x59ca5  stloc.1
0x59ca6  br.s     loc_59CCA
0x59ca8  ldloc.1
0x59ca9  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x59cae  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x59cb3  stloc.2
0x59cb4  ldloc.0
0x59cb5  ldloc.2
0x59cb6  ldstr    aPrivilegeid// "privilegeid"
0x59cbb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x59cc0  unbox.any [mscorlib]System.Guid
0x59cc5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x59cca  ldloc.1
0x59ccb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x59cd0  brtrue.s loc_59CA8
0x59cd2  leave.s  loc_59CE5
0x59cd4  ldloc.1
0x59cd5  isinst   [mscorlib]System.IDisposable
0x59cda  stloc.3
0x59cdb  ldloc.3
0x59cdc  brfalse.s loc_59CE4
0x59cde  ldloc.3
0x59cdf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x59ce4  endfinally
0x59ce5  ldloc.0
0x59ce6  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x59ceb  ldc.i4.0
0x59cec  ble.s    loc_59D1D
0x59cee  ldstr    aRoleprivileges// "RolePrivileges"
0x59cf3  ldloc.0
0x59cf4  ldc.i4.1
0x59cf5  ldarg.3
0x59cf6  ldarg.0
0x59cf7  call     int32 Microsoft.Crm.Metadata.SecurityHelper::DeletePrivilegesByIds(string platformName, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> allPrivileges, bool throwIfRowCountZero, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] int32 objectTypeCode)
0x59cfc  pop
0x59cfd  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCodes"
0x59d02  ldarg.0
0x59d03  ldarg.2
0x59d04  ldc.i4.0
0x59d05  ceq
0x59d07  ldarg.3
0x59d08  call     int32 Microsoft.Crm.Metadata.SecurityHelper::DeleteByObjectTypeCode(string platformName, int32 objectTypeCode, bool throwIfRowCountZero, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x59d0d  pop
0x59d0e  ldstr    aPrivilege// "Privilege"
0x59d13  ldloc.0
0x59d14  ldc.i4.1
0x59d15  ldarg.3
0x59d16  ldc.i4.m1
0x59d17  call     int32 Microsoft.Crm.Metadata.SecurityHelper::DeletePrivilegesByIds(string platformName, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> allPrivileges, bool throwIfRowCountZero, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] int32 objectTypeCode)
0x59d1c  pop
0x59d1d  ret
```
