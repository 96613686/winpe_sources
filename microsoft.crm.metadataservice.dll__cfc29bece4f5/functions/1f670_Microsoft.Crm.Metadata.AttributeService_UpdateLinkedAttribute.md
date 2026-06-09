# Microsoft.Crm.Metadata.AttributeService::UpdateLinkedAttribute

- ea: `0x1f670`
- end: `0x1f6f9`
- name: `Microsoft.Crm.Metadata.AttributeService::UpdateLinkedAttribute`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x757d0`

## callees

- `0x1f670`
- `0x1f780`

## string_xrefs

- `0x1f692`: `linkedattributeid`
- `0x1f6cd`: `More that 1 link found`

## pseudocode

```c

```

## disassembly

```asm
0x1f670  ldstr    aAttribute// "Attribute"
0x1f675  ldarg.3
0x1f676  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f67b  stloc.0
0x1f67c  ldloc.0
0x1f67d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x1f682  ldstr    aAttributeid// "attributeid"
0x1f687  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x1f68c  ldloc.0
0x1f68d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x1f692  ldstr    aLinkedattribut// "linkedattributeid"
0x1f697  ldc.i4.0
0x1f698  ldc.i4.1
0x1f699  newarr   [mscorlib]System.Guid
0x1f69e  dup
0x1f69f  ldc.i4.0
0x1f6a0  ldarg.0
0x1f6a1  stelem   [mscorlib]System.Guid
0x1f6a6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator, class [mscorlib]System.Array)
0x1f6ab  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x1f6b0  ldloc.0
0x1f6b1  ldarg.3
0x1f6b2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1f6b7  stloc.1
0x1f6b8  ldloc.1
0x1f6b9  brfalse.s loc_1F6F7
0x1f6bb  ldloc.1
0x1f6bc  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x1f6c1  ldc.i4.0
0x1f6c2  ble.s    loc_1F6F7
0x1f6c4  ldloc.1
0x1f6c5  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x1f6ca  ldc.i4.1
0x1f6cb  ceq
0x1f6cd  ldstr    aMoreThat1LinkF// "More that 1 link found"
0x1f6d2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1f6d7  ldloc.1
0x1f6d8  ldc.i4.0
0x1f6d9  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x1f6de  ldstr    aAttributeid// "attributeid"
0x1f6e3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1f6e8  unbox.any [mscorlib]System.Guid
0x1f6ed  ldarg.1
0x1f6ee  ldarg.2
0x1f6ef  ldarg.3
0x1f6f0  call     void Microsoft.Crm.Metadata.AttributeService::AddAttributeDescriptionForUpdate(valuetype [mscorlib]System.Guid attributeId, class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1f6f5  ldc.i4.1
0x1f6f6  ret
0x1f6f7  ldc.i4.0
0x1f6f8  ret
```
