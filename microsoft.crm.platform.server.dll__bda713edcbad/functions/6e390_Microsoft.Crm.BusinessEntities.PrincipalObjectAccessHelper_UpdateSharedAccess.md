# Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::UpdateSharedAccess

- ea: `0x6e390`
- end: `0x6e57b`
- name: `Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::UpdateSharedAccess`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x57e10`

## callees

- `0x6daa0`
- `0x6de20`
- `0x6e390`

## string_xrefs

- `0x6e42e`: `PrincipalObjectAccess`
- `0x6e4d8`: `PrincipalObjectAccess`
- `0x6e48a`: `accessrightsmask`
- `0x6e491`: `accessrightsmask`
- `0x6e4a2`: `accessrightsmask`
- `0x6e52f`: `accessrightsmask`
- `0x6e536`: `accessrightsmask`
- `0x6e4bd`: `inheritedaccessrightsmask`
- `0x6e546`: `inheritedaccessrightsmask`

## pseudocode

```c

```

## disassembly

```asm
0x6e390  ldarg.1
0x6e391  ldarg.2
0x6e392  ldarg.3
0x6e393  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::RetrieveMultiple(valuetype [mscorlib]System.Guid entityId, int32 objectTypeCode, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6e398  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::.ctor()
0x6e39d  stloc.0
0x6e39e  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x6e3a3  stloc.1
0x6e3a4  br.s     loc_6E3C9
0x6e3a6  ldloc.1
0x6e3a7  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6e3ac  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x6e3b1  stloc.2
0x6e3b2  ldloc.0
0x6e3b3  ldloc.2
0x6e3b4  ldstr    aPrincipalid// "principalid"
0x6e3b9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e3be  unbox.any [mscorlib]System.Guid
0x6e3c3  ldloc.2
0x6e3c4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::Add(var<u1>, !!T0)
0x6e3c9  ldloc.1
0x6e3ca  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6e3cf  brtrue.s loc_6E3A6
0x6e3d1  leave.s  loc_6E3E4
0x6e3d3  ldloc.1
0x6e3d4  isinst   [mscorlib]System.IDisposable
0x6e3d9  stloc.3
0x6e3da  ldloc.3
0x6e3db  brfalse.s loc_6E3E3
0x6e3dd  ldloc.3
0x6e3de  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6e3e3  endfinally
0x6e3e4  ldarg.0
0x6e3e5  ldarg.2
0x6e3e6  ldarg.3
0x6e3e7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::RetrieveMultiple(valuetype [mscorlib]System.Guid entityId, int32 objectTypeCode, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6e3ec  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x6e3f1  stloc.1
0x6e3f2  br       loc_6E55C
0x6e3f7  ldloc.1
0x6e3f8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6e3fd  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x6e402  stloc.s  4
0x6e404  ldloc.s  4
0x6e406  ldstr    aPrincipalid// "principalid"
0x6e40b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e410  unbox.any [mscorlib]System.Guid
0x6e415  stloc.s  5
0x6e417  ldloc.0
0x6e418  ldloc.s  5
0x6e41a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::ContainsKey(var<u1>)
0x6e41f  brfalse  loc_6E4D8
0x6e424  ldloc.0
0x6e425  ldloc.s  5
0x6e427  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::get_Item(void)
0x6e42c  stloc.s  6
0x6e42e  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x6e433  ldarg.3
0x6e434  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6e439  dup
0x6e43a  ldstr    aPrincipalid// "principalid"
0x6e43f  ldloc.s  6
0x6e441  ldstr    aPrincipalid// "principalid"
0x6e446  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e44b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6e450  dup
0x6e451  ldstr    aPrincipaltypec// "principaltypecode"
0x6e456  ldloc.s  6
0x6e458  ldstr    aPrincipaltypec// "principaltypecode"
0x6e45d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e462  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6e467  dup
0x6e468  ldstr    aObjectid// "objectid"
0x6e46d  ldarg.1
0x6e46e  box      [mscorlib]System.Guid
0x6e473  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6e478  dup
0x6e479  ldstr    aObjecttypecode_81// "objecttypecode"
0x6e47e  ldarg.2
0x6e47f  box      [mscorlib]System.Int32
0x6e484  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6e489  dup
0x6e48a  ldstr    aAccessrightsma// "accessrightsmask"
0x6e48f  ldloc.s  6
0x6e491  ldstr    aAccessrightsma// "accessrightsmask"
0x6e496  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e49b  unbox.any [mscorlib]System.Int32
0x6e4a0  ldloc.s  4
0x6e4a2  ldstr    aAccessrightsma// "accessrightsmask"
0x6e4a7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e4ac  unbox.any [mscorlib]System.Int32
0x6e4b1  or
0x6e4b2  box      [mscorlib]System.Int32
0x6e4b7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6e4bc  dup
0x6e4bd  ldstr    aInheritedacces// "inheritedaccessrightsmask"
0x6e4c2  ldc.i4.0
0x6e4c3  box      [mscorlib]System.Int32
0x6e4c8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6e4cd  ldarg.3
0x6e4ce  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::GrantAccess(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6e4d3  br       loc_6E55C
0x6e4d8  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x6e4dd  ldarg.3
0x6e4de  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6e4e3  dup
0x6e4e4  ldstr    aPrincipalid// "principalid"
0x6e4e9  ldloc.s  5
0x6e4eb  box      [mscorlib]System.Guid
0x6e4f0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6e4f5  dup
0x6e4f6  ldstr    aPrincipaltypec// "principaltypecode"
0x6e4fb  ldloc.s  4
0x6e4fd  ldstr    aPrincipaltypec// "principaltypecode"
0x6e502  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e507  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6e50c  dup
0x6e50d  ldstr    aObjectid// "objectid"
0x6e512  ldarg.1
0x6e513  box      [mscorlib]System.Guid
0x6e518  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6e51d  dup
0x6e51e  ldstr    aObjecttypecode_81// "objecttypecode"
0x6e523  ldarg.2
0x6e524  box      [mscorlib]System.Int32
0x6e529  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6e52e  dup
0x6e52f  ldstr    aAccessrightsma// "accessrightsmask"
0x6e534  ldloc.s  4
0x6e536  ldstr    aAccessrightsma// "accessrightsmask"
0x6e53b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6e540  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6e545  dup
0x6e546  ldstr    aInheritedacces// "inheritedaccessrightsmask"
0x6e54b  ldc.i4.0
0x6e54c  box      [mscorlib]System.Int32
0x6e551  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6e556  ldarg.3
0x6e557  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::GrantAccess(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6e55c  ldloc.1
0x6e55d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6e562  brtrue   loc_6E3F7
0x6e567  leave.s  loc_6E57A
0x6e569  ldloc.1
0x6e56a  isinst   [mscorlib]System.IDisposable
0x6e56f  stloc.3
0x6e570  ldloc.3
0x6e571  brfalse.s loc_6E579
0x6e573  ldloc.3
0x6e574  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6e579  endfinally
0x6e57a  ret
```
