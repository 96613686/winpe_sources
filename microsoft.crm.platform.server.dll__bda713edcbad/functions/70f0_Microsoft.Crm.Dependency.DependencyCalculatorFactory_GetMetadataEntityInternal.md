# Microsoft.Crm.Dependency.DependencyCalculatorFactory::GetMetadataEntityInternal

- ea: `0x70f0`
- end: `0x71bc`
- name: `Microsoft.Crm.Dependency.DependencyCalculatorFactory::GetMetadataEntityInternal`
- size: `204`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x6f10`
- `0x6f90`
- `0x6fd0`

## callees

- `0x70f0`
- `0x444f0`
- `0x44620`
- `0x46010`
- `0x46250`
- `0x462a0`
- `0x46310`
- `0x46530`
- `0x465f0`
- `0x46630`
- `0x46640`
- `0x46a20`

## string_xrefs

- `0x7119`: `componentstate`
- `0x7196`: `componentstate`

## pseudocode

```c

```

## disassembly

```asm
0x70f0  ldarg.1
0x70f1  call     class Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataServiceFactory::CreateServiceProcessObject(string metadataEntityName)
0x70f6  stloc.0
0x70f7  ldarg.1
0x70f8  ldarg.s  4
0x70fa  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string metadataEntityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x70ff  stloc.1
0x7100  ldarg.3
0x7101  brfalse.s loc_7125
0x7103  ldarg.3
0x7104  ldlen
0x7105  brfalse.s loc_7125
0x7107  ldloc.1
0x7108  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x710d  ldarg.3
0x710e  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumns(string[] attributeNames)
0x7113  ldloc.1
0x7114  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x7119  ldstr    aComponentstate// "componentstate"
0x711e  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string attributeName)
0x7123  br.s     loc_7131
0x7125  ldloc.1
0x7126  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x712b  ldc.i4.1
0x712c  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddAllColumns(bool includeComponentState)
0x7131  ldloc.1
0x7132  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x7137  ldloc.1
0x7138  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleBasicQueryExpression::get_MetadataEntity()
0x713d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0x7142  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x7147  ldc.i4.0
0x7148  ldarg.0
0x7149  box      [mscorlib]System.Guid
0x714e  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string metadataAttributeName, valuetype Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator conditionOperator, object value)
0x7153  ldloc.1
0x7154  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleBasicQueryExpression::get_MetadataEntity()
0x7159  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_IsPublishable()
0x715e  ldarg.2
0x715f  and
0x7160  brtrue.s loc_716D
0x7162  ldloc.0
0x7163  ldloc.1
0x7164  ldarg.s  4
0x7166  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::RetrieveMultiple(class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression queryExpression, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x716b  br.s     loc_7176
0x716d  ldloc.0
0x716e  ldloc.1
0x716f  ldarg.s  4
0x7171  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::RetrieveMultipleAsIfPublished(class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression queryExpression, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7176  stloc.2
0x7177  ldloc.2
0x7178  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x717d  ldc.i4.0
0x717e  ble.s    loc_71BA
0x7180  ldloc.1
0x7181  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleBasicQueryExpression::get_MetadataEntity()
0x7186  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_IsPublishable()
0x718b  ldarg.2
0x718c  and
0x718d  brfalse.s loc_71B2
0x718f  ldloc.2
0x7190  ldc.i4.0
0x7191  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x7196  ldstr    aComponentstate// "componentstate"
0x719b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x71a0  unbox.any [mscorlib]System.Int32
0x71a5  ldc.i4.1
0x71a6  beq.s    loc_71AA
0x71a8  ldnull
0x71a9  ret
0x71aa  ldloc.2
0x71ab  ldc.i4.0
0x71ac  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x71b1  ret
0x71b2  ldloc.2
0x71b3  ldc.i4.0
0x71b4  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x71b9  ret
0x71ba  ldnull
0x71bb  ret
```
