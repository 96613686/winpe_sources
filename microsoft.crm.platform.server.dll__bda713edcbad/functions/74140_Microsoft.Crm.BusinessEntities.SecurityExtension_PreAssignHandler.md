# Microsoft.Crm.BusinessEntities.SecurityExtension::PreAssignHandler

- ea: `0x74140`
- end: `0x743a0`
- name: `Microsoft.Crm.BusinessEntities.SecurityExtension::PreAssignHandler`
- size: `608`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x61160`
- `0x61180`
- `0x61de0`
- `0x62640`
- `0x626a0`
- `0x628b0`
- `0x66b10`
- `0x688c0`
- `0x68910`
- `0x68960`
- `0x68a40`
- `0x6daa0`
- `0x73a40`
- `0x74140`
- `0x74d40`
- `0x77580`
- `0x77890`
- `0x77cd0`
- `0x78020`
- `0x78030`

## string_xrefs

- `0x742ea`: `PrincipalObjectAccess`
- `0x7435d`: `accessrightsmask`
- `0x74372`: `inheritedaccessrightsmask`

## pseudocode

```c

```

## disassembly

```asm
0x74140  ldarg.2
0x74141  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x74146  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x7414b  call     class Microsoft.Crm.BusinessEntities.SecurityTraits Microsoft.Crm.BusinessEntities.SecurityTraitsFactory::Get(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity)
0x74150  dup
0x74151  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.SecurityTraits::get_Metadata()
0x74156  stloc.0
0x74157  ldarg.2
0x74158  callvirt instance class Microsoft.Crm.BusinessEntities.SecurityPrincipal Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Principal()
0x7415d  stloc.1
0x7415e  ldarg.2
0x7415f  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x74164  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x74169  ldloc.0
0x7416a  ldc.i4.4
0x7416b  ldarg.2
0x7416c  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x74171  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid user, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType type, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x74176  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0x7417b  brtrue.s loc_7418B
0x7417d  ldloc.1
0x7417e  ldloc.0
0x7417f  ldc.i4.1
0x74180  ldarg.2
0x74181  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x74186  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(class Microsoft.Crm.BusinessEntities.SecurityPrincipal principal, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType type, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7418b  ldarg.2
0x7418c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x74191  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x74196  newobj   instance void Microsoft.Crm.BusinessEntities.SecurityAttributes::.ctor(class Microsoft.Crm.BusinessEntities.SecurityTraits traits, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity)
0x7419b  stloc.2
0x7419c  ldarg.2
0x7419d  ldloc.2
0x7419e  callvirt instance void Microsoft.Crm.BusinessEntities.ExtensionEventArgs::set_ReferencingAttributes(class Microsoft.Crm.BusinessEntities.SecurityAttributes value)
0x741a3  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0x741a8  brtrue.s loc_741B7
0x741aa  ldarg.0
0x741ab  ldarg.2
0x741ac  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x741b1  ldloc.1
0x741b2  call     instance void Microsoft.Crm.BusinessEntities.SecurityExtension::CheckListAccess(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.BusinessEntities.SecurityPrincipal principal)
0x741b7  ldarg.2
0x741b8  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x741bd  ldloc.2
0x741be  ldc.i4   0x80000
0x741c3  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::AccessCheckEx(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.BusinessEntities.SecurityAttributes attributes, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights rights)
0x741c8  ldloc.2
0x741c9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityAttributes::get_OwnerId()
0x741ce  ldloc.1
0x741cf  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x741d4  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x741d9  brfalse.s loc_741DC
0x741db  ret
0x741dc  ldarg.2
0x741dd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x741e2  ldstr    aOwnerid// "ownerid"
0x741e7  ldloc.1
0x741e8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x741ed  box      [mscorlib]System.Guid
0x741f2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x741f7  ldarg.2
0x741f8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x741fd  ldstr    aOwneridtype// "owneridtype"
0x74202  ldloc.1
0x74203  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x74208  box      [mscorlib]System.Int32
0x7420d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x74212  ldloc.1
0x74213  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x74218  ldc.i4.8
0x74219  bne.un.s loc_74238
0x7421b  ldarg.2
0x7421c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x74221  ldstr    aOwninguser// "owninguser"
0x74226  ldloc.1
0x74227  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x7422c  box      [mscorlib]System.Guid
0x74231  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x74236  br.s     loc_74299
0x74238  ldloc.1
0x74239  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x7423e  ldc.i4.s 9
0x74240  bne.un.s loc_74270
0x74242  ldarg.2
0x74243  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x74248  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x7424d  ldstr    aOwninguser// "owninguser"
0x74252  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x74257  brfalse.s loc_74299
0x74259  ldarg.2
0x7425a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x7425f  ldstr    aOwninguser// "owninguser"
0x74264  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x74269  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x7426e  br.s     loc_74299
0x74270  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x74275  ldstr    aInvalidAssigne// "Invalid assignee.Type={0}."
0x7427a  ldc.i4.1
0x7427b  newarr   [mscorlib]System.Object
0x74280  dup
0x74281  ldc.i4.0
0x74282  ldloc.1
0x74283  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x74288  box      [mscorlib]System.Int32
0x7428d  stelem.ref
0x7428e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x74293  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentOutOfRangeException::.ctor(string)
0x74298  throw
0x74299  ldarg.2
0x7429a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x7429f  ldstr    aOwningbusiness// "owningbusinessunit"
0x742a4  ldloc.1
0x742a5  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x742aa  ldloc.1
0x742ab  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x742b0  ldarg.2
0x742b1  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x742b6  call     valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityLibrary::GetOwnerBusinessId(int32 ownerIdType, valuetype [mscorlib]System.Guid ownerId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x742bb  box      [mscorlib]System.Guid
0x742c0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x742c5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x742ca  ldarg.2
0x742cb  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x742d0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x742d5  ldarg.2
0x742d6  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x742db  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x742e0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_ShareToPreviousOwnerOnAssign()
0x742e5  brfalse  loc_7438D
0x742ea  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x742ef  ldarg.2
0x742f0  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x742f5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x742fa  dup
0x742fb  ldstr    aPrincipalid// "principalid"
0x74300  ldloc.2
0x74301  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityAttributes::get_OwnerId()
0x74306  box      [mscorlib]System.Guid
0x7430b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x74310  dup
0x74311  ldstr    aPrincipaltypec// "principaltypecode"
0x74316  ldloc.2
0x74317  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityAttributes::get_OwnerIdType()
0x7431c  box      [mscorlib]System.Int32
0x74321  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x74326  dup
0x74327  ldstr    aObjectid// "objectid"
0x7432c  ldarg.2
0x7432d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x74332  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x74337  unbox.any [mscorlib]System.Guid
0x7433c  box      [mscorlib]System.Guid
0x74341  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x74346  dup
0x74347  ldstr    aObjecttypecode_81// "objecttypecode"
0x7434c  ldloc.0
0x7434d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x74352  box      [mscorlib]System.Int32
0x74357  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x7435c  dup
0x7435d  ldstr    aAccessrightsma// "accessrightsmask"
0x74362  ldc.i4   0xD0037
0x74367  box      [mscorlib]System.Int32
0x7436c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x74371  dup
0x74372  ldstr    aInheritedacces// "inheritedaccessrightsmask"
0x74377  ldc.i4.0
0x74378  box      [mscorlib]System.Int32
0x7437d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x74382  ldarg.2
0x74383  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x74388  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::GrantAccess(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7438d  ldarg.0
0x7438e  ldarg.2
0x7438f  ldarg.2
0x74390  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x74395  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x7439a  call     instance void Microsoft.Crm.BusinessEntities.SecurityExtension::SaveSecurityAttributesKey(class Microsoft.Crm.BusinessEntities.ExtensionEventArgs e, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity)
0x7439f  ret
```
