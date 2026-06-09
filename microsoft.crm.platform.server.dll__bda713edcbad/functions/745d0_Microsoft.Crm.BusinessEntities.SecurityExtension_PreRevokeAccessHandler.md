# Microsoft.Crm.BusinessEntities.SecurityExtension::PreRevokeAccessHandler

- ea: `0x745d0`
- end: `0x74700`
- name: `Microsoft.Crm.BusinessEntities.SecurityExtension::PreRevokeAccessHandler`
- size: `304`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x61160`
- `0x62640`
- `0x628b0`
- `0x66b10`
- `0x688a0`
- `0x68910`
- `0x68960`
- `0x68a50`
- `0x6dce0`
- `0x745d0`
- `0x74d40`
- `0x77580`
- `0x77890`
- `0x77950`
- `0x78020`

## string_xrefs

- `0x746a7`: `PrincipalObjectAccess`
- `0x7464d`: `Only owner can revoke access to the owner. CallerId: {0}, OwnerId: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x745d0  ldarg.2
0x745d1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Moniker()
0x745d6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x745db  call     class Microsoft.Crm.BusinessEntities.SecurityTraits Microsoft.Crm.BusinessEntities.SecurityTraitsFactory::Get(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity)
0x745e0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.SecurityTraits::get_Metadata()
0x745e5  stloc.0
0x745e6  ldarg.2
0x745e7  callvirt instance class Microsoft.Crm.BusinessEntities.SecurityPrincipal Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Principal()
0x745ec  stloc.1
0x745ed  ldarg.2
0x745ee  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x745f3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x745f8  ldloc.0
0x745f9  ldc.i4.5
0x745fa  ldarg.2
0x745fb  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x74600  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid user, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType type, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x74605  ldloc.0
0x74606  ldarg.2
0x74607  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Moniker()
0x7460c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x74611  ldarg.2
0x74612  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x74617  newobj   instance void Microsoft.Crm.BusinessEntities.SecurityAttributes::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata, valuetype [mscorlib]System.Guid objectId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7461c  stloc.2
0x7461d  ldloc.2
0x7461e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityAttributes::get_OwnerId()
0x74623  ldloc.1
0x74624  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x74629  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7462e  brfalse.s loc_74689
0x74630  ldarg.2
0x74631  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x74636  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x7463b  ldloc.2
0x7463c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityAttributes::get_OwnerId()
0x74641  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x74646  brfalse.s loc_74689
0x74648  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7464d  ldstr    aOnlyOwnerCanRe// "Only owner can revoke access to the own"...
0x74652  ldc.i4.2
0x74653  newarr   [mscorlib]System.Object
0x74658  dup
0x74659  ldc.i4.0
0x7465a  ldarg.2
0x7465b  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x74660  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x74665  box      [mscorlib]System.Guid
0x7466a  stelem.ref
0x7466b  dup
0x7466c  ldc.i4.1
0x7466d  ldloc.2
0x7466e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityAttributes::get_OwnerId()
0x74673  box      [mscorlib]System.Guid
0x74678  stelem.ref
0x74679  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7467e  ldc.i4   0x80040223
0x74683  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmSecurityException::.ctor(string, int32)
0x74688  throw
0x74689  ldarg.0
0x7468a  ldarg.2
0x7468b  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x74690  ldloc.1
0x74691  call     instance void Microsoft.Crm.BusinessEntities.SecurityExtension::CheckListAccess(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.BusinessEntities.SecurityPrincipal principal)
0x74696  ldarg.2
0x74697  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x7469c  ldloc.2
0x7469d  ldc.i4   0x40000
0x746a2  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::AccessCheckEx(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.BusinessEntities.SecurityAttributes attributes, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights rights)
0x746a7  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x746ac  ldarg.2
0x746ad  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x746b2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x746b7  dup
0x746b8  ldstr    aPrincipalid// "principalid"
0x746bd  ldloc.1
0x746be  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x746c3  box      [mscorlib]System.Guid
0x746c8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x746cd  dup
0x746ce  ldstr    aObjectid// "objectid"
0x746d3  ldarg.2
0x746d4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Moniker()
0x746d9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x746de  box      [mscorlib]System.Guid
0x746e3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x746e8  ldarg.2
0x746e9  callvirt instance bool Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_RevokeInheritedAccess()
0x746ee  brtrue.s loc_746F3
0x746f0  ldc.i4.1
0x746f1  br.s     loc_746F4
0x746f3  ldc.i4.2
0x746f4  ldarg.2
0x746f5  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x746fa  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::RevokeAccess(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, valuetype Microsoft.Crm.BusinessEntities.AccessRightsType accessRightsType, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x746ff  ret
```
