# Microsoft.Crm.Metadata.AttributeUninstallHandler::CascadeUninstallToLinkAttributeComponent

- ea: `0x5ec80`
- end: `0x5ee6f`
- name: `Microsoft.Crm.Metadata.AttributeUninstallHandler::CascadeUninstallToLinkAttributeComponent`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x5e990`

## callees

- `0x5eb80`
- `0x5ec80`

## string_xrefs

- `0x5ed07`: `linkedattributeid`
- `0x5ed76`: `There should be only one attribute {0} as a linked attribute`

## pseudocode

```c

```

## disassembly

```asm
0x5ec80  ldarg.2
0x5ec81  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_Cache()
0x5ec86  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Attributes()
0x5ec8b  ldarg.1
0x5ec8c  box      [mscorlib]System.Guid
0x5ec91  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x5ec96  stloc.0
0x5ec97  ldloc.0
0x5ec98  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x5ec9d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5eca2  ldstr    aAppointment_0// "Appointment"
0x5eca7  callvirt instance bool [mscorlib]System.String::Equals(string)
0x5ecac  brtrue.s loc_5ECC6
0x5ecae  ldloc.0
0x5ecaf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x5ecb4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5ecb9  ldstr    aRecurringappoi_0// "RecurringAppointmentMaster"
0x5ecbe  callvirt instance bool [mscorlib]System.String::Equals(string)
0x5ecc3  brtrue.s loc_5ECC6
0x5ecc5  ret
0x5ecc6  ldloc.0
0x5ecc7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x5eccc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5ecd1  ldstr    aAppointment_0// "Appointment"
0x5ecd6  callvirt instance bool [mscorlib]System.String::Equals(string)
0x5ecdb  brfalse  loc_5EDCB
0x5ece0  ldstr    aAttribute// "Attribute"
0x5ece5  ldarg.2
0x5ece6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x5eceb  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5ecf0  stloc.1
0x5ecf1  ldloc.1
0x5ecf2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x5ecf7  ldstr    aAttributeid// "attributeid"
0x5ecfc  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x5ed01  ldloc.1
0x5ed02  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x5ed07  ldstr    aLinkedattribut// "linkedattributeid"
0x5ed0c  ldc.i4.0
0x5ed0d  ldc.i4.1
0x5ed0e  newarr   [mscorlib]System.Guid
0x5ed13  dup
0x5ed14  ldc.i4.0
0x5ed15  ldarg.1
0x5ed16  stelem   [mscorlib]System.Guid
0x5ed1b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator, class [mscorlib]System.Array)
0x5ed20  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x5ed25  ldloc.1
0x5ed26  ldarg.2
0x5ed27  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x5ed2c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5ed31  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x5ed36  stloc.2
0x5ed37  ldloc.2
0x5ed38  brfalse  loc_5EE6E
0x5ed3d  ldloc.2
0x5ed3e  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x5ed43  ldc.i4.0
0x5ed44  ble      loc_5EE6E
0x5ed49  ldloc.2
0x5ed4a  ldc.i4.0
0x5ed4b  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x5ed50  ldstr    aAttributeid// "attributeid"
0x5ed55  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x5ed5a  unbox.any [mscorlib]System.Guid
0x5ed5f  stloc.3
0x5ed60  ldarg.0
0x5ed61  ldloc.3
0x5ed62  ldarg.2
0x5ed63  call     instance bool Microsoft.Crm.Metadata.AttributeUninstallHandler::IsRootComponent(valuetype [mscorlib]System.Guid componentObjectId, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext solutionUninstallContext)
0x5ed68  brtrue   loc_5EE6E
0x5ed6d  ldloc.2
0x5ed6e  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x5ed73  ldc.i4.1
0x5ed74  ceq
0x5ed76  ldstr    aThereShouldBeO_2// "There should be only one attribute {0} "...
0x5ed7b  ldc.i4.1
0x5ed7c  newarr   [mscorlib]System.Object
0x5ed81  dup
0x5ed82  ldc.i4.0
0x5ed83  ldarg.1
0x5ed84  box      [mscorlib]System.Guid
0x5ed89  stelem.ref
0x5ed8a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x5ed8f  ldc.i4.1
0x5ed90  newarr   [mscorlib]System.String
0x5ed95  dup
0x5ed96  ldc.i4.0
0x5ed97  ldstr    aAttributeid// "attributeid"
0x5ed9c  stelem.ref
0x5ed9d  stloc.s  4
0x5ed9f  ldc.i4.1
0x5eda0  newarr   [mscorlib]System.Object
0x5eda5  dup
0x5eda6  ldc.i4.0
0x5eda7  ldloc.3
0x5eda8  box      [mscorlib]System.Guid
0x5edad  stelem.ref
0x5edae  stloc.s  5
0x5edb0  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData> [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::get_SolutionComponentTypeDictionary()
0x5edb5  ldc.i4.2
0x5edb6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData>::get_Item(void)
0x5edbb  stloc.s  6
0x5edbd  ldarg.0
0x5edbe  ldloc.s  6
0x5edc0  ldloc.s  4
0x5edc2  ldloc.s  5
0x5edc4  ldarg.2
0x5edc5  call     instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.UninstallHandler::CascadeUninstallToComponent(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData, string[], object[], class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext)
0x5edca  ret
0x5edcb  ldloc.0
0x5edcc  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LinkedAttributeId()
0x5edd1  stloc.s  7
0x5edd3  ldloca.s 7
0x5edd5  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x5edda  brfalse  loc_5EE6E
0x5eddf  ldloc.0
0x5ede0  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LinkedAttributeId()
0x5ede5  stloc.s  7
0x5ede7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5edec  stloc.s  8
0x5edee  ldloca.s 7
0x5edf0  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x5edf5  brtrue.s loc_5EDFA
0x5edf7  ldc.i4.1
0x5edf8  br.s     loc_5EE14
0x5edfa  ldloca.s 7
0x5edfc  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x5ee01  brtrue.s loc_5EE06
0x5ee03  ldc.i4.0
0x5ee04  br.s     loc_5EE14
0x5ee06  ldloca.s 7
0x5ee08  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x5ee0d  ldloc.s  8
0x5ee0f  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5ee14  brfalse.s loc_5EE6E
0x5ee16  ldarg.0
0x5ee17  ldloc.0
0x5ee18  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LinkedAttributeId()
0x5ee1d  stloc.s  7
0x5ee1f  ldloca.s 7
0x5ee21  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x5ee26  ldarg.2
0x5ee27  call     instance bool Microsoft.Crm.Metadata.AttributeUninstallHandler::IsRootComponent(valuetype [mscorlib]System.Guid componentObjectId, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext solutionUninstallContext)
0x5ee2c  brtrue.s loc_5EE6E
0x5ee2e  ldc.i4.1
0x5ee2f  newarr   [mscorlib]System.String
0x5ee34  dup
0x5ee35  ldc.i4.0
0x5ee36  ldstr    aAttributeid// "attributeid"
0x5ee3b  stelem.ref
0x5ee3c  stloc.s  9
0x5ee3e  ldc.i4.1
0x5ee3f  newarr   [mscorlib]System.Object
0x5ee44  dup
0x5ee45  ldc.i4.0
0x5ee46  ldloc.0
0x5ee47  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LinkedAttributeId()
0x5ee4c  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x5ee51  stelem.ref
0x5ee52  stloc.s  0xA
0x5ee54  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData> [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::get_SolutionComponentTypeDictionary()
0x5ee59  ldc.i4.2
0x5ee5a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData>::get_Item(void)
0x5ee5f  stloc.s  0xB
0x5ee61  ldarg.0
0x5ee62  ldloc.s  0xB
0x5ee64  ldloc.s  9
0x5ee66  ldloc.s  0xA
0x5ee68  ldarg.2
0x5ee69  call     instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.UninstallHandler::CascadeUninstallToComponent(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData, string[], object[], class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext)
0x5ee6e  ret
```
