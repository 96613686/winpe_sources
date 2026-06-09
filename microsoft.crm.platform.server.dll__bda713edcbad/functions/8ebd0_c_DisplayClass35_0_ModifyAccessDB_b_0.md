# <>c__DisplayClass35_0::<ModifyAccessDB>b__0

- ea: `0x8ebd0`
- end: `0x8ee4c`
- name: `<>c__DisplayClass35_0::<ModifyAccessDB>b__0`
- size: `636`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: ``

## callees

- `0x5f660`
- `0x60ab0`
- `0x60b40`
- `0x60bc0`
- `0x60fd0`
- `0x61160`
- `0x61180`
- `0x61190`
- `0x61300`
- `0x61320`
- `0x62640`
- `0x628b0`
- `0x66b10`
- `0x67ce0`
- `0x6dbd0`
- `0x77950`
- `0x78020`
- `0x78030`
- `0x8ebd0`

## string_xrefs

- `0x8ec40`: `PrincipalObjectAccess`
- `0x8ecdc`: `accessrightsmask`
- `0x8ece9`: `accessrightsmask`
- `0x8ecfb`: `inheritedaccessrightsmask`
- `0x8ed0a`: `inheritedaccessrightsmask`

## pseudocode

```c

```

## disassembly

```asm
0x8ebd0  ldstr    aShareCascadeTo// "Share Cascade Total execution time"
0x8ebd5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounterExecutionTimeContext::.ctor(string)
0x8ebda  stloc.0
0x8ebdb  ldarg.0
0x8ebdc  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker <>c__DisplayClass35_0::moniker
0x8ebe1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x8ebe6  ldarg.0
0x8ebe7  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker <>c__DisplayClass35_0::moniker
0x8ebec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x8ebf1  ldarg.0
0x8ebf2  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass35_0::context
0x8ebf7  newobj   instance void Microsoft.Crm.BusinessEntities.SecurityAttributes::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata, valuetype [mscorlib]System.Guid objectId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8ebfc  stloc.1
0x8ebfd  ldarg.0
0x8ebfe  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass35_0::context
0x8ec03  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x8ec08  ldarg.0
0x8ec09  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker <>c__DisplayClass35_0::moniker
0x8ec0e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x8ec13  ldc.i4.5
0x8ec14  ldarg.0
0x8ec15  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass35_0::context
0x8ec1a  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid user, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType type, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8ec1f  ldc.i4   0x40008
0x8ec24  stloc.2
0x8ec25  ldarg.0
0x8ec26  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass35_0::context
0x8ec2b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x8ec30  ldloc.1
0x8ec31  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityAttributes::get_OwnerId()
0x8ec36  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8ec3b  brfalse  loc_8ED3A
0x8ec40  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x8ec45  ldarg.0
0x8ec46  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass35_0::context
0x8ec4b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8ec50  stloc.3
0x8ec51  ldloc.3
0x8ec52  ldstr    aPrincipalid// "principalid"
0x8ec57  ldarg.0
0x8ec58  ldfld    class Microsoft.Crm.BusinessEntities.PrincipalAccess <>c__DisplayClass35_0::grantee
0x8ec5d  callvirt instance class Microsoft.Crm.BusinessEntities.SecurityPrincipal Microsoft.Crm.BusinessEntities.PrincipalAccess::get_Principal()
0x8ec62  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x8ec67  box      [mscorlib]System.Guid
0x8ec6c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8ec71  ldloc.3
0x8ec72  ldstr    aPrincipaltypec// "principaltypecode"
0x8ec77  ldarg.0
0x8ec78  ldfld    class Microsoft.Crm.BusinessEntities.PrincipalAccess <>c__DisplayClass35_0::grantee
0x8ec7d  callvirt instance class Microsoft.Crm.BusinessEntities.SecurityPrincipal Microsoft.Crm.BusinessEntities.PrincipalAccess::get_Principal()
0x8ec82  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x8ec87  box      [mscorlib]System.Int32
0x8ec8c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8ec91  ldloc.3
0x8ec92  ldstr    aObjectid// "objectid"
0x8ec97  ldarg.0
0x8ec98  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker <>c__DisplayClass35_0::moniker
0x8ec9d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x8eca2  box      [mscorlib]System.Guid
0x8eca7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8ecac  ldloc.3
0x8ecad  ldstr    aObjecttypecode_81// "objecttypecode"
0x8ecb2  ldarg.0
0x8ecb3  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker <>c__DisplayClass35_0::moniker
0x8ecb8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x8ecbd  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x8ecc2  box      [mscorlib]System.Int32
0x8ecc7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8eccc  ldloc.3
0x8eccd  ldarg.0
0x8ecce  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass35_0::context
0x8ecd3  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8ecd8  ldc.i4.0
0x8ecd9  stloc.s  4
0x8ecdb  ldloc.3
0x8ecdc  ldstr    aAccessrightsma// "accessrightsmask"
0x8ece1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x8ece6  brtrue.s loc_8ECFA
0x8ece8  ldloc.3
0x8ece9  ldstr    aAccessrightsma// "accessrightsmask"
0x8ecee  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8ecf3  unbox.any [mscorlib]System.Int32
0x8ecf8  stloc.s  4
0x8ecfa  ldloc.3
0x8ecfb  ldstr    aInheritedacces// "inheritedaccessrightsmask"
0x8ed00  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x8ed05  brtrue.s loc_8ED1C
0x8ed07  ldloc.s  4
0x8ed09  ldloc.3
0x8ed0a  ldstr    aInheritedacces// "inheritedaccessrightsmask"
0x8ed0f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8ed14  unbox.any [mscorlib]System.Int32
0x8ed19  or
0x8ed1a  stloc.s  4
0x8ed1c  ldarg.0
0x8ed1d  ldfld    class Microsoft.Crm.BusinessEntities.PrincipalAccess <>c__DisplayClass35_0::grantee
0x8ed22  callvirt instance int32 Microsoft.Crm.BusinessEntities.PrincipalAccess::get_AccessMask()
0x8ed27  stloc.s  5
0x8ed29  ldloc.s  5
0x8ed2b  ldloc.s  4
0x8ed2d  not
0x8ed2e  and
0x8ed2f  stloc.s  5
0x8ed31  ldloc.s  5
0x8ed33  brfalse.s loc_8ED3A
0x8ed35  ldloc.2
0x8ed36  ldloc.s  5
0x8ed38  or
0x8ed39  stloc.2
0x8ed3a  ldarg.0
0x8ed3b  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass35_0::context
0x8ed40  ldloc.1
0x8ed41  ldloc.2
0x8ed42  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::AccessCheckEx(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.BusinessEntities.SecurityAttributes attributes, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights rights)
0x8ed47  ldarg.0
0x8ed48  ldfld    class Microsoft.Crm.BusinessEntities.PrincipalAccess <>c__DisplayClass35_0::grantee
0x8ed4d  callvirt instance class Microsoft.Crm.BusinessEntities.SecurityPrincipal Microsoft.Crm.BusinessEntities.PrincipalAccess::get_Principal()
0x8ed52  ldarg.0
0x8ed53  ldfld    class Microsoft.Crm.BusinessEntities.PrincipalAccess <>c__DisplayClass35_0::grantee
0x8ed58  callvirt instance class Microsoft.Crm.BusinessEntities.SecurityPrincipal Microsoft.Crm.BusinessEntities.PrincipalAccess::get_Principal()
0x8ed5d  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x8ed62  call     int32 Microsoft.Crm.BusinessEntities.CascadeEngine::ConvertSecurityPrincipalTypeCode(int32 sptCode)
0x8ed67  callvirt instance void Microsoft.Crm.BusinessEntities.SecurityPrincipal::set_Type(int32 value)
0x8ed6c  ldarg.0
0x8ed6d  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass35_0::context
0x8ed72  newobj   instance void Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8ed77  stloc.s  6
0x8ed79  ldarg.0
0x8ed7a  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass35_0::context
0x8ed7f  newobj   instance void Microsoft.Crm.BusinessEntities.CrmCascadeDBCollection::.ctor(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8ed84  stloc.s  7
0x8ed86  ldstr    aShareCascadeCo// "Share Cascade Collect execution time"
0x8ed8b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounterExecutionTimeContext::.ctor(string)
0x8ed90  stloc.s  8
0x8ed92  ldloc.s  7
0x8ed94  ldc.i4.3
0x8ed95  ldarg.0
0x8ed96  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker <>c__DisplayClass35_0::moniker
0x8ed9b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x8eda0  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x8eda5  ldarg.0
0x8eda6  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker <>c__DisplayClass35_0::moniker
0x8edab  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x8edb0  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x8edb5  ldloc.1
0x8edb6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityAttributes::get_OwnerId()
0x8edbb  ldloc.1
0x8edbc  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityAttributes::get_OwnerIdType()
0x8edc1  callvirt instance void Microsoft.Crm.BusinessEntities.CrmCascadeDBCollection::Collect(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeActionType actionType, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> entityId, int32 entityOtc, valuetype [mscorlib]System.Guid ownerId, int32 ownerIdType)
0x8edc6  leave.s  loc_8EDD4
0x8edc8  ldloc.s  8
0x8edca  brfalse.s loc_8EDD3
0x8edcc  ldloc.s  8
0x8edce  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8edd3  endfinally
0x8edd4  ldstr    aShareCascadeEx// "Share Cascade Execute execution time"
0x8edd9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounterExecutionTimeContext::.ctor(string)
0x8edde  stloc.s  8
0x8ede0  ldarg.0
0x8ede1  ldfld    class Microsoft.Crm.BusinessEntities.PrincipalAccess <>c__DisplayClass35_0::grantee
0x8ede6  ldarg.0
0x8ede7  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker <>c__DisplayClass35_0::moniker
0x8edec  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x8edf1  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x8edf6  ldarg.0
0x8edf7  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker <>c__DisplayClass35_0::moniker
0x8edfc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x8ee01  ldarg.0
0x8ee02  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass35_0::context
0x8ee07  call     void Microsoft.Crm.BusinessEntities.CrmCascadeDBHandler::ModifyAccess(class Microsoft.Crm.BusinessEntities.PrincipalAccess grantee, int32 rootEntityOtc, valuetype [mscorlib]System.Guid rootEntityId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8ee0c  leave.s  loc_8EE1A
0x8ee0e  ldloc.s  8
0x8ee10  brfalse.s loc_8EE19
0x8ee12  ldloc.s  8
0x8ee14  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ee19  endfinally
0x8ee1a  leave.s  loc_8EE4B
0x8ee1c  stloc.s  9
0x8ee1e  ldloc.s  7
0x8ee20  ldloc.s  9
0x8ee22  callvirt instance void Microsoft.Crm.BusinessEntities.CrmCascadeDBCollection::DetectIsDeadLockVictim(class [mscorlib]System.Exception exception)
0x8ee27  rethrow
0x8ee29  ldloc.s  7
0x8ee2b  brfalse.s loc_8EE34
0x8ee2d  ldloc.s  7
0x8ee2f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ee34  endfinally
0x8ee35  ldloc.s  6
0x8ee37  brfalse.s loc_8EE40
0x8ee39  ldloc.s  6
0x8ee3b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ee40  endfinally
0x8ee41  ldloc.0
0x8ee42  brfalse.s loc_8EE4A
0x8ee44  ldloc.0
0x8ee45  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ee4a  endfinally
0x8ee4b  ret
```
