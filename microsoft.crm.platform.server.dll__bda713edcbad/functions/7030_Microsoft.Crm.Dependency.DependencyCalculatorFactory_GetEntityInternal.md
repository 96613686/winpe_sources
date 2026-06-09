# Microsoft.Crm.Dependency.DependencyCalculatorFactory::GetEntityInternal

- ea: `0x7030`
- end: `0x70e9`
- name: `Microsoft.Crm.Dependency.DependencyCalculatorFactory::GetEntityInternal`
- size: `185`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x6f10`
- `0x6f90`
- `0x6fd0`

## callees

- `0x7030`
- `0x13b10`
- `0x13b90`
- `0x13ee0`
- `0x184b0`
- `0x18520`
- `0x18540`
- `0x18800`
- `0x1ae30`
- `0x58d20`
- `0x78470`

## string_xrefs

- `0x705e`: `componentstate`
- `0x70c3`: `componentstate`

## pseudocode

```c

```

## disassembly

```asm
0x7030  ldarg.1
0x7031  ldc.i4.1
0x7032  call     class Microsoft.Crm.BusinessEntities.BusinessProcessObject Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata, bool returnBaseServiceIfNoServiceFound)
0x7037  ldarg.1
0x7038  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x703d  ldarg.s  4
0x703f  newobj   instance void Microsoft.Crm.Query.EntityExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x7044  stloc.0
0x7045  ldarg.3
0x7046  brfalse.s loc_706A
0x7048  ldarg.3
0x7049  ldlen
0x704a  brfalse.s loc_706A
0x704c  ldloc.0
0x704d  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x7052  ldarg.3
0x7053  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[] attributePlatformNames)
0x7058  ldloc.0
0x7059  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x705e  ldstr    aComponentstate// "componentstate"
0x7063  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x7068  br.s     loc_7075
0x706a  ldloc.0
0x706b  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x7070  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x7075  ldloc.0
0x7076  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x707b  ldloc.0
0x707c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.EntityExpression::get_Entity()
0x7081  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x7086  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x708b  ldc.i4.0
0x708c  ldarg.0
0x708d  box      [mscorlib]System.Guid
0x7092  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x7097  pop
0x7098  ldloc.0
0x7099  ldarg.1
0x709a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsPublishable()
0x709f  ldarg.2
0x70a0  and
0x70a1  ldarg.s  4
0x70a3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveForDependencyCalculation(class Microsoft.Crm.Query.EntityExpression expression, bool retrieveUnpublished, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x70a8  stloc.1
0x70a9  ldloc.1
0x70aa  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x70af  ldc.i4.0
0x70b0  ble.s    loc_70E7
0x70b2  ldarg.1
0x70b3  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsPublishable()
0x70b8  ldarg.2
0x70b9  and
0x70ba  brfalse.s loc_70DF
0x70bc  ldloc.1
0x70bd  ldc.i4.0
0x70be  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x70c3  ldstr    aComponentstate// "componentstate"
0x70c8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x70cd  unbox.any [mscorlib]System.Int32
0x70d2  ldc.i4.1
0x70d3  beq.s    loc_70D7
0x70d5  ldnull
0x70d6  ret
0x70d7  ldloc.1
0x70d8  ldc.i4.0
0x70d9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x70de  ret
0x70df  ldloc.1
0x70e0  ldc.i4.0
0x70e1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x70e6  ret
0x70e7  ldnull
0x70e8  ret
```
