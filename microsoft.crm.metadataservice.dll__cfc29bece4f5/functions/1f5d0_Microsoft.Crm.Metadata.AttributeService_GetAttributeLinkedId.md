# Microsoft.Crm.Metadata.AttributeService::GetAttributeLinkedId

- ea: `0x1f5d0`
- end: `0x1f667`
- name: `Microsoft.Crm.Metadata.AttributeService::GetAttributeLinkedId`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x757d0`

## callees

- `0x1f5d0`

## string_xrefs

- `0x1f5e2`: `linkedattributeid`
- `0x1f63e`: `linkedattributeid`
- `0x1f651`: `linkedattributeid`
- `0x1f62d`: `More that 1 link found`

## pseudocode

```c

```

## disassembly

```asm
0x1f5d0  ldstr    aAttribute// "Attribute"
0x1f5d5  ldarg.1
0x1f5d6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f5db  stloc.0
0x1f5dc  ldloc.0
0x1f5dd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x1f5e2  ldstr    aLinkedattribut// "linkedattributeid"
0x1f5e7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x1f5ec  ldloc.0
0x1f5ed  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x1f5f2  ldstr    aAttributeid// "attributeid"
0x1f5f7  ldc.i4.0
0x1f5f8  ldc.i4.1
0x1f5f9  newarr   [mscorlib]System.Guid
0x1f5fe  dup
0x1f5ff  ldc.i4.0
0x1f600  ldarg.0
0x1f601  stelem   [mscorlib]System.Guid
0x1f606  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator, class [mscorlib]System.Array)
0x1f60b  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x1f610  ldloc.0
0x1f611  ldarg.1
0x1f612  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1f617  stloc.1
0x1f618  ldloc.1
0x1f619  brfalse.s loc_1F661
0x1f61b  ldloc.1
0x1f61c  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x1f621  ldc.i4.0
0x1f622  ble.s    loc_1F661
0x1f624  ldloc.1
0x1f625  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x1f62a  ldc.i4.1
0x1f62b  ceq
0x1f62d  ldstr    aMoreThat1LinkF// "More that 1 link found"
0x1f632  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1f637  ldloc.1
0x1f638  ldc.i4.0
0x1f639  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x1f63e  ldstr    aLinkedattribut// "linkedattributeid"
0x1f643  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x1f648  brtrue.s loc_1F661
0x1f64a  ldloc.1
0x1f64b  ldc.i4.0
0x1f64c  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x1f651  ldstr    aLinkedattribut// "linkedattributeid"
0x1f656  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1f65b  unbox.any [mscorlib]System.Guid
0x1f660  ret
0x1f661  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f666  ret
```
