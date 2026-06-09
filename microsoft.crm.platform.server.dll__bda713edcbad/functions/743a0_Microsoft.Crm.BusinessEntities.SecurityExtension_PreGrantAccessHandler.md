# Microsoft.Crm.BusinessEntities.SecurityExtension::PreGrantAccessHandler

- ea: `0x743a0`
- end: `0x745c4`
- name: `Microsoft.Crm.BusinessEntities.SecurityExtension::PreGrantAccessHandler`
- size: `548`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x61160`
- `0x61180`
- `0x62640`
- `0x628b0`
- `0x66b10`
- `0x688a0`
- `0x68910`
- `0x68960`
- `0x68980`
- `0x689a0`
- `0x6daa0`
- `0x6dbd0`
- `0x6dce0`
- `0x743a0`
- `0x74d40`
- `0x77580`
- `0x77890`
- `0x77950`
- `0x78020`

## string_xrefs

- `0x743bd`: `PrincipalObjectAccess`
- `0x744c0`: `accessrightsmask`
- `0x744cd`: `accessrightsmask`
- `0x74562`: `accessrightsmask`
- `0x74575`: `accessrightsmask`
- `0x744df`: `inheritedaccessrightsmask`
- `0x744ee`: `inheritedaccessrightsmask`
- `0x7454c`: `inheritedaccessrightsmask`
- `0x7458b`: `inheritedaccessrightsmask`

## pseudocode

```c

```

## disassembly

```asm
0x743a0  ldarg.2
0x743a1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Moniker()
0x743a6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x743ab  call     class Microsoft.Crm.BusinessEntities.SecurityTraits Microsoft.Crm.BusinessEntities.SecurityTraitsFactory::Get(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity)
0x743b0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.SecurityTraits::get_Metadata()
0x743b5  stloc.0
0x743b6  ldarg.2
0x743b7  callvirt instance class Microsoft.Crm.BusinessEntities.SecurityPrincipal Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Principal()
0x743bc  stloc.1
0x743bd  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x743c2  ldarg.2
0x743c3  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x743c8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x743cd  stloc.2
0x743ce  ldloc.2
0x743cf  ldstr    aPrincipalid// "principalid"
0x743d4  ldloc.1
0x743d5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x743da  box      [mscorlib]System.Guid
0x743df  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x743e4  ldloc.2
0x743e5  ldstr    aPrincipaltypec// "principaltypecode"
0x743ea  ldloc.1
0x743eb  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x743f0  box      [mscorlib]System.Int32
0x743f5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x743fa  ldloc.2
0x743fb  ldstr    aObjectid// "objectid"
0x74400  ldarg.2
0x74401  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Moniker()
0x74406  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x7440b  box      [mscorlib]System.Guid
0x74410  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x74415  ldloc.2
0x74416  ldstr    aObjecttypecode_81// "objecttypecode"
0x7441b  ldloc.0
0x7441c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x74421  box      [mscorlib]System.Int32
0x74426  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x7442b  ldarg.2
0x7442c  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x74431  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x74436  ldloc.0
0x74437  ldc.i4.5
0x74438  ldarg.2
0x74439  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x7443e  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid user, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType type, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x74443  ldloc.0
0x74444  ldarg.2
0x74445  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Moniker()
0x7444a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x7444f  ldarg.2
0x74450  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x74455  newobj   instance void Microsoft.Crm.BusinessEntities.SecurityAttributes::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata, valuetype [mscorlib]System.Guid objectId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7445a  stloc.3
0x7445b  ldarg.0
0x7445c  ldarg.2
0x7445d  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x74462  ldloc.1
0x74463  call     instance void Microsoft.Crm.BusinessEntities.SecurityExtension::CheckListAccess(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.BusinessEntities.SecurityPrincipal principal)
0x74468  ldarg.2
0x74469  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x7446e  ldloc.3
0x7446f  ldc.i4   0x40000
0x74474  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::AccessCheckEx(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.BusinessEntities.SecurityAttributes attributes, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights rights)
0x74479  ldloc.1
0x7447a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x7447f  ldloc.3
0x74480  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityAttributes::get_OwnerId()
0x74485  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7448a  brfalse.s loc_7448D
0x7448c  ret
0x7448d  ldarg.2
0x7448e  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x74493  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x74498  ldloc.3
0x74499  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityAttributes::get_OwnerId()
0x7449e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x744a3  brfalse  loc_74536
0x744a8  ldarg.2
0x744a9  callvirt instance bool Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_ModifyAccess()
0x744ae  brfalse.s loc_74524
0x744b0  ldloc.2
0x744b1  ldarg.2
0x744b2  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x744b7  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x744bc  ldc.i4.0
0x744bd  stloc.s  5
0x744bf  ldloc.2
0x744c0  ldstr    aAccessrightsma// "accessrightsmask"
0x744c5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x744ca  brtrue.s loc_744DE
0x744cc  ldloc.2
0x744cd  ldstr    aAccessrightsma// "accessrightsmask"
0x744d2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x744d7  unbox.any [mscorlib]System.Int32
0x744dc  stloc.s  5
0x744de  ldloc.2
0x744df  ldstr    aInheritedacces// "inheritedaccessrightsmask"
0x744e4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x744e9  brtrue.s loc_74500
0x744eb  ldloc.s  5
0x744ed  ldloc.2
0x744ee  ldstr    aInheritedacces// "inheritedaccessrightsmask"
0x744f3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x744f8  unbox.any [mscorlib]System.Int32
0x744fd  or
0x744fe  stloc.s  5
0x74500  ldarg.2
0x74501  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_AccessMask()
0x74506  stloc.s  6
0x74508  ldloc.s  6
0x7450a  ldloc.s  5
0x7450c  not
0x7450d  and
0x7450e  stloc.s  6
0x74510  ldloc.s  6
0x74512  brfalse.s loc_74536
0x74514  ldarg.2
0x74515  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x7451a  ldloc.3
0x7451b  ldloc.s  6
0x7451d  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::AccessCheckEx(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.BusinessEntities.SecurityAttributes attributes, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights rights)
0x74522  br.s     loc_74536
0x74524  ldarg.2
0x74525  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x7452a  ldloc.3
0x7452b  ldarg.2
0x7452c  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_AccessMask()
0x74531  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::AccessCheckEx(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.BusinessEntities.SecurityAttributes attributes, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights rights)
0x74536  ldarg.2
0x74537  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_AccessMask()
0x7453c  ldc.i4   0x8000000
0x74541  and
0x74542  ldc.i4.0
0x74543  cgt.un
0x74545  stloc.s  4
0x74547  ldloc.s  4
0x74549  brfalse.s loc_74574
0x7454b  ldloc.2
0x7454c  ldstr    aInheritedacces// "inheritedaccessrightsmask"
0x74551  ldarg.2
0x74552  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_AccessMask()
0x74557  box      [mscorlib]System.Int32
0x7455c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x74561  ldloc.2
0x74562  ldstr    aAccessrightsma// "accessrightsmask"
0x74567  ldc.i4.0
0x74568  box      [mscorlib]System.Int32
0x7456d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x74572  br.s     loc_7459B
0x74574  ldloc.2
0x74575  ldstr    aAccessrightsma// "accessrightsmask"
0x7457a  ldarg.2
0x7457b  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_AccessMask()
0x74580  box      [mscorlib]System.Int32
0x74585  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x7458a  ldloc.2
0x7458b  ldstr    aInheritedacces// "inheritedaccessrightsmask"
0x74590  ldc.i4.0
0x74591  box      [mscorlib]System.Int32
0x74596  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x7459b  ldarg.2
0x7459c  callvirt instance bool Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_ModifyAccess()
0x745a1  brfalse.s loc_745B7
0x745a3  ldloc.2
0x745a4  ldloc.s  4
0x745a6  brtrue.s loc_745AB
0x745a8  ldc.i4.1
0x745a9  br.s     loc_745AC
0x745ab  ldc.i4.2
0x745ac  ldarg.2
0x745ad  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x745b2  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::RevokeAccess(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, valuetype Microsoft.Crm.BusinessEntities.AccessRightsType accessRightsType, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x745b7  ldloc.2
0x745b8  ldarg.2
0x745b9  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x745be  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::GrantAccess(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x745c3  ret
```
