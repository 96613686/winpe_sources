# Microsoft.Crm.Service.ObjectModel.SLAService::Create

- ea: `0x9cc0`
- end: `0x9e68`
- name: `Microsoft.Crm.Service.ObjectModel.SLAService::Create`
- size: `424`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x9cc0`
- `0xa950`
- `0xa980`
- `0xa9a0`

## pseudocode

```c

```

## disassembly

```asm
0x9cc0  ldarg.1
0x9cc1  ldstr    aEntity// "entity"
0x9cc6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9ccb  ldarg.2
0x9ccc  ldstr    aContext// "context"
0x9cd1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9cd6  ldarg.1
0x9cd7  ldstr    aSlatype// "slatype"
0x9cdc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x9ce1  brtrue.s loc_9D26
0x9ce3  ldarg.1
0x9ce4  ldstr    aAllowpauseresu// "allowpauseresume"
0x9ce9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x9cee  brtrue.s loc_9D26
0x9cf0  ldarg.1
0x9cf1  ldstr    aSlatype// "slatype"
0x9cf6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x9cfb  unbox.any [mscorlib]System.Int32
0x9d00  ldc.i4.1
0x9d01  beq.s    loc_9D26
0x9d03  ldarg.1
0x9d04  ldstr    aAllowpauseresu// "allowpauseresume"
0x9d09  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x9d0e  unbox.any [mscorlib]System.Boolean
0x9d13  brfalse.s loc_9D26
0x9d15  ldc.i4   0x80045000
0x9d1a  ldc.i4.0
0x9d1b  newarr   [mscorlib]System.Object
0x9d20  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x9d25  throw
0x9d26  ldarg.1
0x9d27  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x9d2c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x9d31  ldstr    aPrimaryentityo// "primaryentityotc"
0x9d36  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(object)
0x9d3b  brtrue.s loc_9D54
0x9d3d  ldarg.1
0x9d3e  ldstr    aObjecttypecode// "objecttypecode"
0x9d43  ldc.i4.s 0x70
0x9d45  box      [mscorlib]System.Int32
0x9d4a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x9d4f  br       loc_9E1E
0x9d54  ldarg.1
0x9d55  ldstr    aPrimaryentityo// "primaryentityotc"
0x9d5a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x9d5f  brfalse.s loc_9D86
0x9d61  ldarg.1
0x9d62  ldstr    aObjecttypecode// "objecttypecode"
0x9d67  ldarg.1
0x9d68  ldstr    aPrimaryentityo// "primaryentityotc"
0x9d6d  ldc.i4.s 0x70
0x9d6f  box      [mscorlib]System.Int32
0x9d74  dup
0x9d75  stloc.0
0x9d76  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x9d7b  ldloc.0
0x9d7c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x9d81  br       loc_9E1E
0x9d86  ldarg.2
0x9d87  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsSLAFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9d8c  brtrue.s loc_9DD5
0x9d8e  ldarg.1
0x9d8f  ldstr    aPrimaryentityo// "primaryentityotc"
0x9d94  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x9d99  unbox.any [mscorlib]System.Int32
0x9d9e  ldc.i4.s 0x70
0x9da0  bne.un.s loc_9DC4
0x9da2  ldarg.1
0x9da3  ldstr    aObjecttypecode// "objecttypecode"
0x9da8  ldarg.1
0x9da9  ldstr    aPrimaryentityo// "primaryentityotc"
0x9dae  ldc.i4.s 0x70
0x9db0  box      [mscorlib]System.Int32
0x9db5  dup
0x9db6  stloc.0
0x9db7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x9dbc  ldloc.0
0x9dbd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x9dc2  br.s     loc_9E1E
0x9dc4  ldc.i4   0x80055005
0x9dc9  ldc.i4.0
0x9dca  newarr   [mscorlib]System.Object
0x9dcf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x9dd4  throw
0x9dd5  ldarg.1
0x9dd6  ldstr    aObjecttypecode// "objecttypecode"
0x9ddb  ldarg.1
0x9ddc  ldstr    aPrimaryentityo// "primaryentityotc"
0x9de1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x9de6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x9deb  ldarg.0
0x9dec  ldarg.1
0x9ded  ldstr    aPrimaryentityo// "primaryentityotc"
0x9df2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x9df7  unbox.any [mscorlib]System.Int32
0x9dfc  ldarg.2
0x9dfd  call     instance bool Microsoft.Crm.Service.ObjectModel.SLAService::IsSlaEnabledForEntity(int32 regardingObjectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9e02  brtrue.s loc_9E1E
0x9e04  ldarg.0
0x9e05  ldarg.2
0x9e06  call     instance bool Microsoft.Crm.Service.ObjectModel.SLAService::IsContextOfTypeSolutionImport(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9e0b  brtrue.s loc_9E1E
0x9e0d  ldc.i4   0x80055005
0x9e12  ldc.i4.0
0x9e13  newarr   [mscorlib]System.Object
0x9e18  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x9e1d  throw
0x9e1e  ldarg.2
0x9e1f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsSLAFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9e24  brfalse.s loc_9E57
0x9e26  ldarg.1
0x9e27  ldstr    aObjecttypecode// "objecttypecode"
0x9e2c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x9e31  unbox.any [mscorlib]System.Int32
0x9e36  ldc.i4.s 0x70
0x9e38  beq.s    loc_9E57
0x9e3a  ldarg.1
0x9e3b  ldstr    aSlatype// "slatype"
0x9e40  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x9e45  unbox.any [mscorlib]System.Int32
0x9e4a  brtrue.s loc_9E57
0x9e4c  ldstr    aStandardSlaTyp// "Standard SLA type is not applicable for"...
0x9e51  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x9e56  throw
0x9e57  ldarg.0
0x9e58  ldarg.1
0x9e59  ldarg.2
0x9e5a  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x9e5f  ldarg.0
0x9e60  ldarg.1
0x9e61  ldarg.2
0x9e62  call     instance void Microsoft.Crm.Service.ObjectModel.SLAService::AddDependency(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9e67  ret
```
