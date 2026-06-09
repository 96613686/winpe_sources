# Microsoft.Crm.Metadata.SecurityHelper::HasPrivilegesForVirtualEntity

- ea: `0x5a590`
- end: `0x5a69b`
- name: `Microsoft.Crm.Metadata.SecurityHelper::HasPrivilegesForVirtualEntity`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x5a590`
- `0x5a6a0`
- `0x77d70`
- `0x77df0`

## string_xrefs

- `0x5a5d4`: `Privileges missing For Entity ObjectTypeCode: {0}`
- `0x5a662`: `Role Privileges missing For Role {0} , Entity ObjectTypeCode: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x5a590  newobj   instance void <>c__DisplayClass26_0::.ctor()
0x5a595  stloc.0
0x5a596  ldloc.0
0x5a597  ldarg.0
0x5a598  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x5a59d  ldarg.1
0x5a59e  call     class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType>> Microsoft.Crm.Metadata.SecurityHelper::GetPrivileges(int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5a5a3  stfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType>> <>c__DisplayClass26_0::privileges
0x5a5a8  ldc.i4.3
0x5a5a9  newarr   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType
0x5a5ae  dup
0x5a5af  ldtoken  valuetype __StaticArrayInitTypeSize=12 <PrivateImplementationDetails>::FD07378070B2CE2D87115CFDB3FA18ECE10418A1
0x5a5b4  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x5a5b9  ldloc.0
0x5a5ba  ldftn    instance bool <>c__DisplayClass26_0::<HasPrivilegesForVirtualEntity>b__0(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType vp)
0x5a5c0  newobj   instance void class [mscorlib]System.Func`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, bool>::.ctor(object, native int)
0x5a5c5  call     T0x2B000048
0x5a5ca  brfalse.s loc_5A5F4
0x5a5cc  ldarg.1
0x5a5cd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5a5d2  ldc.i4.s 0x19
0x5a5d4  ldstr    aPrivilegesMiss// "Privileges missing For Entity ObjectTyp"...
0x5a5d9  ldc.i4.1
0x5a5da  newarr   [mscorlib]System.Object
0x5a5df  dup
0x5a5e0  ldc.i4.0
0x5a5e1  ldarg.0
0x5a5e2  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x5a5e7  box      [mscorlib]System.Int32
0x5a5ec  stelem.ref
0x5a5ed  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5a5f2  ldc.i4.0
0x5a5f3  ret
0x5a5f4  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RoleService::.ctor()
0x5a5f9  stloc.1
0x5a5fa  ldsfld   valuetype [mscorlib]System.Guid[] Microsoft.Crm.Metadata.SecurityHelper::adminRoleIds
0x5a5ff  stloc.2
0x5a600  ldc.i4.0
0x5a601  stloc.3
0x5a602  br       loc_5A690
0x5a607  ldloc.2
0x5a608  ldloc.3
0x5a609  ldelem   [mscorlib]System.Guid
0x5a60e  stloc.s  4
0x5a610  newobj   instance void <>c__DisplayClass26_2::.ctor()
0x5a615  stloc.s  5
0x5a617  ldloc.1
0x5a618  ldloc.s  4
0x5a61a  ldarg.1
0x5a61b  callvirt instance valuetype [mscorlib]System.Guid class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RoleServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOff>::GetRoleIdFromRoleTemplateId(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5a620  stloc.s  6
0x5a622  ldloc.s  6
0x5a624  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5a629  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5a62e  brtrue.s loc_5A68C
0x5a630  ldloc.s  5
0x5a632  ldloc.1
0x5a633  ldloc.s  6
0x5a635  ldarg.1
0x5a636  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RoleServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOff>::RetrieveRolePrivileges(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5a63b  stfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] <>c__DisplayClass26_2::rolePrivileges
0x5a640  ldloc.0
0x5a641  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType>> <>c__DisplayClass26_0::privileges
0x5a646  ldloc.s  5
0x5a648  ldftn    instance bool <>c__DisplayClass26_2::<HasPrivilegesForVirtualEntity>b__2(class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType> p)
0x5a64e  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType>, bool>::.ctor(object, native int)
0x5a653  call     T0x2B000049
0x5a658  brfalse.s loc_5A68C
0x5a65a  ldarg.1
0x5a65b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5a660  ldc.i4.s 0x19
0x5a662  ldstr    aRolePrivileges// "Role Privileges missing For Role {0} , "...
0x5a667  ldc.i4.2
0x5a668  newarr   [mscorlib]System.Object
0x5a66d  dup
0x5a66e  ldc.i4.0
0x5a66f  ldloc.s  4
0x5a671  box      [mscorlib]System.Guid
0x5a676  stelem.ref
0x5a677  dup
0x5a678  ldc.i4.1
0x5a679  ldarg.0
0x5a67a  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x5a67f  box      [mscorlib]System.Int32
0x5a684  stelem.ref
0x5a685  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5a68a  ldc.i4.0
0x5a68b  ret
0x5a68c  ldloc.3
0x5a68d  ldc.i4.1
0x5a68e  add
0x5a68f  stloc.3
0x5a690  ldloc.3
0x5a691  ldloc.2
0x5a692  ldlen
0x5a693  conv.i4
0x5a694  blt      loc_5A607
0x5a699  ldc.i4.1
0x5a69a  ret
```
