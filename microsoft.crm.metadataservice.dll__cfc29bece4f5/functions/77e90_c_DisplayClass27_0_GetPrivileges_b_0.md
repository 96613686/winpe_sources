# <>c__DisplayClass27_0::<GetPrivileges>b__0

- ea: `0x77e90`
- end: `0x77f12`
- name: `<>c__DisplayClass27_0::<GetPrivileges>b__0`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x5a6d0`
- `0x77e90`

## string_xrefs

- `0x77ed3`: `privilegeid`
- `0x77ec1`: `accessright`

## pseudocode

```c

```

## disassembly

```asm
0x77e90  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrivilegeService::.ctor()
0x77e95  ldarg.0
0x77e96  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass27_0::context
0x77e9b  ldarg.0
0x77e9c  ldfld    int32 <>c__DisplayClass27_0::objectTypeCode
0x77ea1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOff>::RetrievePrivilegeSetForEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, int32)
0x77ea6  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType>>::.ctor()
0x77eab  stloc.0
0x77eac  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x77eb1  stloc.1
0x77eb2  br.s     loc_77EF2
0x77eb4  ldloc.1
0x77eb5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x77eba  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x77ebf  stloc.2
0x77ec0  ldloc.2
0x77ec1  ldstr    aAccessright// "accessright"
0x77ec6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x77ecb  unbox.any [mscorlib]System.Int32
0x77ed0  stloc.3
0x77ed1  ldloc.0
0x77ed2  ldloc.2
0x77ed3  ldstr    aPrivilegeid// "privilegeid"
0x77ed8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x77edd  unbox.any [mscorlib]System.Guid
0x77ee2  ldloc.3
0x77ee3  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType Microsoft.Crm.Metadata.SecurityHelper::GetPrivilegeType(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights accessRights)
0x77ee8  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType>::.ctor(var<u1>, !!T0)
0x77eed  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType>>::Add(var<u1>)
0x77ef2  ldloc.1
0x77ef3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x77ef8  brtrue.s loc_77EB4
0x77efa  leave.s  loc_77F10
0x77efc  ldloc.1
0x77efd  isinst   [mscorlib]System.IDisposable
0x77f02  stloc.s  4
0x77f04  ldloc.s  4
0x77f06  brfalse.s loc_77F0F
0x77f08  ldloc.s  4
0x77f0a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x77f0f  endfinally
0x77f10  ldloc.0
0x77f11  ret
```
