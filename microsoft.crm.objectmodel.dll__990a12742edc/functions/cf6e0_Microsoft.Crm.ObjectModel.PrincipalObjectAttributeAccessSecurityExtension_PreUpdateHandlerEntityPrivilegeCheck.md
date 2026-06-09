# Microsoft.Crm.ObjectModel.PrincipalObjectAttributeAccessSecurityExtension::PreUpdateHandlerEntityPrivilegeCheck

- ea: `0xcf6e0`
- end: `0xcf7b4`
- name: `Microsoft.Crm.ObjectModel.PrincipalObjectAttributeAccessSecurityExtension::PreUpdateHandlerEntityPrivilegeCheck`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0xcf6e0`
- `0xcf900`

## string_xrefs

- `0xcf6f9`: `readaccess`
- `0xcf724`: `readaccess`
- `0xcf731`: `readaccess`
- `0xcf748`: `readaccess`
- `0xcf706`: `updateaccess`
- `0xcf759`: `updateaccess`
- `0xcf766`: `updateaccess`
- `0xcf77d`: `updateaccess`

## pseudocode

```c

```

## disassembly

```asm
0xcf6e0  ldarg.0
0xcf6e1  ldarg.1
0xcf6e2  ldarg.2
0xcf6e3  ldarg.3
0xcf6e4  ldarg.s  4
0xcf6e6  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityExtension::PreUpdateHandlerEntityPrivilegeCheck(object, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityTraits, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityAttributes, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs)
0xcf6eb  ldarg.s  4
0xcf6ed  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0xcf6f2  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0xcf6f7  stloc.0
0xcf6f8  ldloc.0
0xcf6f9  ldstr    aReadaccess// "readaccess"
0xcf6fe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xcf703  brtrue.s loc_CF723
0xcf705  ldloc.0
0xcf706  ldstr    aUpdateaccess// "updateaccess"
0xcf70b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xcf710  brtrue.s loc_CF723
0xcf712  ldc.i4   0x8004F50A
0xcf717  ldc.i4.0
0xcf718  newarr   [mscorlib]System.Object
0xcf71d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xcf722  throw
0xcf723  ldloc.0
0xcf724  ldstr    aReadaccess// "readaccess"
0xcf729  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xcf72e  brfalse.s loc_CF742
0xcf730  ldloc.0
0xcf731  ldstr    aReadaccess// "readaccess"
0xcf736  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xcf73b  unbox.any [mscorlib]System.Boolean
0xcf740  br.s     loc_CF757
0xcf742  ldarg.3
0xcf743  callvirt instance class [mscorlib]System.Collections.Hashtable [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityAttributes::get_Values()
0xcf748  ldstr    aReadaccess// "readaccess"
0xcf74d  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xcf752  unbox.any [mscorlib]System.Boolean
0xcf757  stloc.1
0xcf758  ldloc.0
0xcf759  ldstr    aUpdateaccess// "updateaccess"
0xcf75e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xcf763  brfalse.s loc_CF777
0xcf765  ldloc.0
0xcf766  ldstr    aUpdateaccess// "updateaccess"
0xcf76b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xcf770  unbox.any [mscorlib]System.Boolean
0xcf775  br.s     loc_CF78C
0xcf777  ldarg.3
0xcf778  callvirt instance class [mscorlib]System.Collections.Hashtable [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityAttributes::get_Values()
0xcf77d  ldstr    aUpdateaccess// "updateaccess"
0xcf782  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xcf787  unbox.any [mscorlib]System.Boolean
0xcf78c  stloc.2
0xcf78d  ldloc.1
0xcf78e  ldc.i4.0
0xcf78f  ceq
0xcf791  ldloc.2
0xcf792  ldc.i4.0
0xcf793  ceq
0xcf795  and
0xcf796  brfalse.s loc_CF7A9
0xcf798  ldc.i4   0x8004F50A
0xcf79d  ldc.i4.0
0xcf79e  newarr   [mscorlib]System.Object
0xcf7a3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xcf7a8  throw
0xcf7a9  ldarg.0
0xcf7aa  ldarg.s  4
0xcf7ac  ldloc.1
0xcf7ad  ldloc.2
0xcf7ae  call     instance void Microsoft.Crm.ObjectModel.PrincipalObjectAttributeAccessSecurityExtension::SecurityChecks(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs e, bool readAccess, bool updateAccess)
0xcf7b3  ret
```
