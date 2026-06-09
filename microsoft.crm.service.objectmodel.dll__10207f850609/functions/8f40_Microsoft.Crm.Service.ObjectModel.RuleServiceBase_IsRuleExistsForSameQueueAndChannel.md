# Microsoft.Crm.Service.ObjectModel.RuleServiceBase::IsRuleExistsForSameQueueAndChannel

- ea: `0x8f40`
- end: `0x900c`
- name: `Microsoft.Crm.Service.ObjectModel.RuleServiceBase::IsRuleExistsForSameQueueAndChannel`
- size: `204`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x4fe0`
- `0x8a40`

## callees

- `0x8f40`
- `0x9010`

## pseudocode

```c

```

## disassembly

```asm
0x8f40  ldnull
0x8f41  stloc.0
0x8f42  ldarg.1
0x8f43  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x8f48  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x8f4d  ldarg.3
0x8f4e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x8f53  stloc.1
0x8f54  ldloc.1
0x8f55  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x8f5a  ldstr    aConvertruleid_0// "convertruleid"
0x8f5f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x8f64  ldarg.2
0x8f65  brfalse.s loc_8FBC
0x8f67  ldarg.1
0x8f68  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0x8f6d  ldstr    aQueueid// "queueid"
0x8f72  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x8f77  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x8f7c  callvirt instance string [mscorlib]System.Object::ToString()
0x8f81  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8f86  brfalse.s loc_8F8A
0x8f88  ldc.i4.0
0x8f89  ret
0x8f8a  ldloc.1
0x8f8b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x8f90  ldstr    aConvertruleid_0// "convertruleid"
0x8f95  ldc.i4.1
0x8f96  ldarg.1
0x8f97  ldstr    aConvertruleid_0// "convertruleid"
0x8f9c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x8fa1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x8fa6  pop
0x8fa7  ldarg.0
0x8fa8  ldloc.1
0x8fa9  ldarg.1
0x8faa  ldarg.2
0x8fab  ldarg.3
0x8fac  call     instance void Microsoft.Crm.Service.ObjectModel.RuleServiceBase::AddCondition(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression entityExpression, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity preImage, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8fb1  ldarg.0
0x8fb2  ldloc.1
0x8fb3  ldarg.3
0x8fb4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8fb9  stloc.0
0x8fba  br.s     loc_8FFC
0x8fbc  ldarg.1
0x8fbd  ldstr    aQueueid// "queueid"
0x8fc2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x8fc7  brtrue.s loc_8FFC
0x8fc9  ldarg.1
0x8fca  ldstr    aSourcetypecode// "sourcetypecode"
0x8fcf  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x8fd4  brtrue.s loc_8FFC
0x8fd6  ldarg.0
0x8fd7  ldloc.1
0x8fd8  ldarg.1
0x8fd9  ldarg.1
0x8fda  ldarg.3
0x8fdb  call     instance void Microsoft.Crm.Service.ObjectModel.RuleServiceBase::AddCondition(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression entityExpression, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity preImage, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8fe0  ldarg.3
0x8fe1  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8fe6  stloc.2
0x8fe7  ldarg.0
0x8fe8  ldloc.1
0x8fe9  ldarg.3
0x8fea  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8fef  stloc.0
0x8ff0  leave.s  loc_8FFC
0x8ff2  ldloc.2
0x8ff3  brfalse.s loc_8FFB
0x8ff5  ldloc.2
0x8ff6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ffb  endfinally
0x8ffc  ldloc.0
0x8ffd  brfalse.s loc_900A
0x8fff  ldloc.0
0x9000  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x9005  ldc.i4.0
0x9006  ble.s    loc_900A
0x9008  ldc.i4.1
0x9009  ret
0x900a  ldc.i4.0
0x900b  ret
```
