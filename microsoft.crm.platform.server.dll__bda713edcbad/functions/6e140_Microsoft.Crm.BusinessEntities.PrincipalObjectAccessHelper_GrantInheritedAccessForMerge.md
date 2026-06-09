# Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::GrantInheritedAccessForMerge

- ea: `0x6e140`
- end: `0x6e329`
- name: `Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::GrantInheritedAccessForMerge`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x57e10`

## callees

- `0x61160`
- `0x61180`
- `0x6daa0`
- `0x6de20`
- `0x6e140`
- `0x6e330`

## string_xrefs

- `0x6e155`: `PrincipalObjectAccess`
- `0x6e233`: `PrincipalObjectAccess`
- `0x6e2b9`: `PrincipalObjectAccess`
- `0x6e25c`: `accessrightsmask`
- `0x6e26d`: `accessrightsmask`
- `0x6e2dd`: `accessrightsmask`
- `0x6e284`: `inheritedaccessrightsmask`
- `0x6e295`: `inheritedaccessrightsmask`
- `0x6e2e9`: `inheritedaccessrightsmask`

## pseudocode

```c

```

## disassembly

```asm
0x6e140  ldarg.s  5
0x6e142  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x6e147  ldarg.s  4
0x6e149  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x6e14e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e153  brfalse.s loc_6E193
0x6e155  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x6e15a  ldarg.s  6
0x6e15c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6e161  dup
0x6e162  ldarg.s  5
0x6e164  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x6e169  box      [mscorlib]System.Guid
0x6e16e  ldarg.s  5
0x6e170  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x6e175  box      [mscorlib]System.Int32
0x6e17a  ldarg.0
0x6e17b  ldarg.1
0x6e17c  ldc.i4.0
0x6e17d  box      [mscorlib]System.Int32
0x6e182  ldc.i4   0x80D0017
0x6e187  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::PopulatePOAProperties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity POA, object principalId, object principalTypeCode, valuetype [mscorlib]System.Guid referencingId, int32 referencingOTC, object accessRightsMask, int32 inheritedAccessRightsMask)
0x6e18c  ldarg.s  6
0x6e18e  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::GrantAccess(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6e193  ldarg.0
0x6e194  ldarg.1
0x6e195  ldarg.s  6
0x6e197  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::RetrieveMultiple(valuetype [mscorlib]System.Guid entityId, int32 objectTypeCode, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6e19c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::.ctor()
0x6e1a1  stloc.0
0x6e1a2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x6e1a7  stloc.1
0x6e1a8  br.s     loc_6E1CD
0x6e1aa  ldloc.1
0x6e1ab  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6e1b0  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x6e1b5  stloc.2
0x6e1b6  ldloc.0
0x6e1b7  ldloc.2
0x6e1b8  ldstr    aPrincipalid// "principalid"
0x6e1bd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e1c2  unbox.any [mscorlib]System.Guid
0x6e1c7  ldloc.2
0x6e1c8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::Add(var<u1>, !!T0)
0x6e1cd  ldloc.1
0x6e1ce  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6e1d3  brtrue.s loc_6E1AA
0x6e1d5  leave.s  loc_6E1E8
0x6e1d7  ldloc.1
0x6e1d8  isinst   [mscorlib]System.IDisposable
0x6e1dd  stloc.3
0x6e1de  ldloc.3
0x6e1df  brfalse.s loc_6E1E7
0x6e1e1  ldloc.3
0x6e1e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6e1e7  endfinally
0x6e1e8  ldarg.2
0x6e1e9  ldarg.3
0x6e1ea  ldarg.s  6
0x6e1ec  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::RetrieveMultiple(valuetype [mscorlib]System.Guid entityId, int32 objectTypeCode, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6e1f1  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x6e1f6  stloc.1
0x6e1f7  br       loc_6E30A
0x6e1fc  ldloc.1
0x6e1fd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6e202  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x6e207  stloc.s  4
0x6e209  ldloc.s  4
0x6e20b  ldstr    aPrincipalid// "principalid"
0x6e210  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e215  unbox.any [mscorlib]System.Guid
0x6e21a  stloc.s  5
0x6e21c  ldloc.0
0x6e21d  ldloc.s  5
0x6e21f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::ContainsKey(var<u1>)
0x6e224  brfalse  loc_6E2B9
0x6e229  ldloc.0
0x6e22a  ldloc.s  5
0x6e22c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::get_Item(void)
0x6e231  stloc.s  6
0x6e233  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x6e238  ldarg.s  6
0x6e23a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6e23f  dup
0x6e240  ldloc.s  6
0x6e242  ldstr    aPrincipalid// "principalid"
0x6e247  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e24c  ldloc.s  6
0x6e24e  ldstr    aPrincipaltypec// "principaltypecode"
0x6e253  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e258  ldarg.0
0x6e259  ldarg.1
0x6e25a  ldloc.s  6
0x6e25c  ldstr    aAccessrightsma// "accessrightsmask"
0x6e261  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e266  unbox.any [mscorlib]System.Int32
0x6e26b  ldloc.s  4
0x6e26d  ldstr    aAccessrightsma// "accessrightsmask"
0x6e272  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e277  unbox.any [mscorlib]System.Int32
0x6e27c  or
0x6e27d  box      [mscorlib]System.Int32
0x6e282  ldloc.s  6
0x6e284  ldstr    aInheritedacces// "inheritedaccessrightsmask"
0x6e289  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e28e  unbox.any [mscorlib]System.Int32
0x6e293  ldloc.s  4
0x6e295  ldstr    aInheritedacces// "inheritedaccessrightsmask"
0x6e29a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e29f  unbox.any [mscorlib]System.Int32
0x6e2a4  or
0x6e2a5  ldc.i4   0x8000000
0x6e2aa  or
0x6e2ab  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::PopulatePOAProperties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity POA, object principalId, object principalTypeCode, valuetype [mscorlib]System.Guid referencingId, int32 referencingOTC, object accessRightsMask, int32 inheritedAccessRightsMask)
0x6e2b0  ldarg.s  6
0x6e2b2  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::GrantAccess(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6e2b7  br.s     loc_6E30A
0x6e2b9  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x6e2be  ldarg.s  6
0x6e2c0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6e2c5  dup
0x6e2c6  ldloc.s  5
0x6e2c8  box      [mscorlib]System.Guid
0x6e2cd  ldloc.s  4
0x6e2cf  ldstr    aPrincipaltypec// "principaltypecode"
0x6e2d4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e2d9  ldarg.0
0x6e2da  ldarg.1
0x6e2db  ldloc.s  4
0x6e2dd  ldstr    aAccessrightsma// "accessrightsmask"
0x6e2e2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e2e7  ldloc.s  4
0x6e2e9  ldstr    aInheritedacces// "inheritedaccessrightsmask"
0x6e2ee  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e2f3  unbox.any [mscorlib]System.Int32
0x6e2f8  ldc.i4   0x8000000
0x6e2fd  or
0x6e2fe  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::PopulatePOAProperties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity POA, object principalId, object principalTypeCode, valuetype [mscorlib]System.Guid referencingId, int32 referencingOTC, object accessRightsMask, int32 inheritedAccessRightsMask)
0x6e303  ldarg.s  6
0x6e305  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::GrantAccess(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6e30a  ldloc.1
0x6e30b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6e310  brtrue   loc_6E1FC
0x6e315  leave.s  loc_6E328
0x6e317  ldloc.1
0x6e318  isinst   [mscorlib]System.IDisposable
0x6e31d  stloc.3
0x6e31e  ldloc.3
0x6e31f  brfalse.s loc_6E327
0x6e321  ldloc.3
0x6e322  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6e327  endfinally
0x6e328  ret
```
