# Microsoft.Crm.Metadata.AttributeUninstallHandler::IsRootComponent

- ea: `0x5eb80`
- end: `0x5ec7d`
- name: `Microsoft.Crm.Metadata.AttributeUninstallHandler::IsRootComponent`
- size: `253`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x5e990`
- `0x5ec80`

## callees

- `0x5eb80`

## string_xrefs

- `0x5ec25`: `componenttype`
- `0x5ec4e`: `solutioncomponentid`

## pseudocode

```c

```

## disassembly

```asm
0x5eb80  ldarg.2
0x5eb81  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_Cache()
0x5eb86  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Attributes()
0x5eb8b  ldarg.1
0x5eb8c  box      [mscorlib]System.Guid
0x5eb91  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x5eb96  stloc.0
0x5eb97  ldloc.0
0x5eb98  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x5eb9d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5eba2  ldstr    aAppointment_0// "Appointment"
0x5eba7  callvirt instance bool [mscorlib]System.String::Equals(string)
0x5ebac  brtrue.s loc_5EBC7
0x5ebae  ldloc.0
0x5ebaf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x5ebb4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5ebb9  ldstr    aRecurringappoi_0// "RecurringAppointmentMaster"
0x5ebbe  callvirt instance bool [mscorlib]System.String::Equals(string)
0x5ebc3  brtrue.s loc_5EBC7
0x5ebc5  ldc.i4.0
0x5ebc6  ret
0x5ebc7  ldarg.2
0x5ebc8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x5ebcd  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SolutionComponent::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5ebd2  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentService::.ctor()
0x5ebd7  stloc.1
0x5ebd8  dup
0x5ebd9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x5ebde  ldarg.2
0x5ebdf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x5ebe4  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5ebe9  stloc.2
0x5ebea  ldloc.2
0x5ebeb  ldstr    aObjectid// "objectid"
0x5ebf0  ldc.i4.0
0x5ebf1  ldloc.0
0x5ebf2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_EntityId()
0x5ebf7  box      [mscorlib]System.Guid
0x5ebfc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5ec01  pop
0x5ec02  ldloc.2
0x5ec03  ldstr    aSolutionid// "solutionid"
0x5ec08  ldc.i4.0
0x5ec09  ldarg.2
0x5ec0a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x5ec0f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5ec14  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x5ec19  box      [mscorlib]System.Guid
0x5ec1e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5ec23  pop
0x5ec24  ldloc.2
0x5ec25  ldstr    aComponenttype// "componenttype"
0x5ec2a  ldc.i4.0
0x5ec2b  ldc.i4.1
0x5ec2c  box      [mscorlib]System.Int32
0x5ec31  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5ec36  pop
0x5ec37  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x5ec3c  ldarg.2
0x5ec3d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x5ec42  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x5ec47  stloc.3
0x5ec48  ldloc.3
0x5ec49  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5ec4e  ldstr    aSolutioncompon_0// "solutioncomponentid"
0x5ec53  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x5ec58  ldloc.3
0x5ec59  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5ec5e  ldloc.2
0x5ec5f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x5ec64  ldloc.1
0x5ec65  ldloc.3
0x5ec66  ldarg.2
0x5ec67  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x5ec6c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5ec71  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x5ec76  ldc.i4.0
0x5ec77  ble.s    loc_5EC7B
0x5ec79  ldc.i4.1
0x5ec7a  ret
0x5ec7b  ldc.i4.0
0x5ec7c  ret
```
