# Microsoft.Crm.Service.ObjectModel.EntitlementService::RenewChannels

- ea: `0xbca0`
- end: `0xbe23`
- name: `Microsoft.Crm.Service.ObjectModel.EntitlementService::RenewChannels`
- size: `387`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xb480`
- `0xbca0`

## pseudocode

```c

```

## disassembly

```asm
0xbca0  ldarg.3
0xbca1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbca6  ldstr    aEntitlementcha// "EntitlementChannel"
0xbcab  ldc.i4.0
0xbcac  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xbcb1  stloc.0
0xbcb2  ldarg.3
0xbcb3  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xbcb8  stloc.1
0xbcb9  ldloc.1
0xbcba  ldloc.0
0xbcbb  ldstr    aEntitlementid// "entitlementid"
0xbcc0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0xbcc5  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::set_Attribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0xbcca  ldloc.1
0xbccb  ldc.i4.0
0xbccc  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::set_ConditionOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xbcd1  ldloc.1
0xbcd2  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::get_Values()
0xbcd7  ldarg.1
0xbcd8  box      [mscorlib]System.Guid
0xbcdd  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xbce2  pop
0xbce3  ldstr    aEntitlementcha// "EntitlementChannel"
0xbce8  ldarg.3
0xbce9  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xbcee  stloc.2
0xbcef  ldloc.2
0xbcf0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_Conditions()
0xbcf5  ldc.i4.1
0xbcf6  newarr   [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression
0xbcfb  dup
0xbcfc  ldc.i4.0
0xbcfd  ldloc.1
0xbcfe  stelem.ref
0xbcff  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpressionCollection::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression>)
0xbd04  ldstr    aEntitlementcha// "EntitlementChannel"
0xbd09  ldarg.3
0xbd0a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xbd0f  stloc.3
0xbd10  ldloc.3
0xbd11  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xbd16  ldloc.2
0xbd17  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0xbd1c  ldloc.3
0xbd1d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xbd22  ldstr    aTotalterms// "totalterms"
0xbd27  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xbd2c  ldloc.3
0xbd2d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xbd32  ldstr    aChannel// "channel"
0xbd37  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xbd3c  ldarg.3
0xbd3d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xbd42  stloc.s  4
0xbd44  ldarg.0
0xbd45  ldloc.3
0xbd46  ldarg.3
0xbd47  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xbd4c  stloc.s  5
0xbd4e  newobj   instance void Microsoft.Crm.Service.ObjectModel.EntitlementChannelService::.ctor()
0xbd53  stloc.s  6
0xbd55  ldloc.s  5
0xbd57  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xbd5c  ldc.i4.0
0xbd5d  ble      loc_BE14
0xbd62  ldloc.s  5
0xbd64  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xbd69  stloc.s  7
0xbd6b  br       loc_BDF1
0xbd70  ldloc.s  7
0xbd72  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xbd77  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0xbd7c  stloc.s  8
0xbd7e  ldarg.3
0xbd7f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xbd84  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.EntitlementChannel::.ctor(valuetype [mscorlib]System.Guid)
0xbd89  stloc.s  9
0xbd8b  ldloc.s  9
0xbd8d  ldstr    aEntitlementid// "entitlementid"
0xbd92  ldarg.2
0xbd93  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xbd98  box      [mscorlib]System.Guid
0xbd9d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xbda2  ldloc.s  9
0xbda4  ldstr    aTotalterms// "totalterms"
0xbda9  ldloc.s  8
0xbdab  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0xbdb0  ldstr    aTotalterms// "totalterms"
0xbdb5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0xbdba  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0xbdbf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xbdc4  ldloc.s  9
0xbdc6  ldstr    aChannel// "channel"
0xbdcb  ldloc.s  8
0xbdcd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0xbdd2  ldstr    aChannel// "channel"
0xbdd7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0xbddc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0xbde1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xbde6  ldloc.s  6
0xbde8  ldloc.s  9
0xbdea  ldarg.3
0xbdeb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xbdf0  pop
0xbdf1  ldloc.s  7
0xbdf3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbdf8  brtrue   loc_BD70
0xbdfd  leave.s  loc_BE22
0xbdff  ldloc.s  7
0xbe01  isinst   [mscorlib]System.IDisposable
0xbe06  stloc.s  0xA
0xbe08  ldloc.s  0xA
0xbe0a  brfalse.s loc_BE13
0xbe0c  ldloc.s  0xA
0xbe0e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbe13  endfinally
0xbe14  leave.s  loc_BE22
0xbe16  ldloc.s  4
0xbe18  brfalse.s loc_BE21
0xbe1a  ldloc.s  4
0xbe1c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbe21  endfinally
0xbe22  ret
```
