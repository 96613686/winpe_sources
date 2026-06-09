# Microsoft.Crm.Service.ObjectModel.EntitlementTemplateChannelService::VerifyDuplicateChannel

- ea: `0xc630`
- end: `0xc7b0`
- name: `Microsoft.Crm.Service.ObjectModel.EntitlementTemplateChannelService::VerifyDuplicateChannel`
- size: `384`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xc630`

## string_xrefs

- `0xc636`: `EntitlementTemplateChannel`
- `0xc6b0`: `EntitlementTemplateChannel`
- `0xc733`: `EntitlementTemplateChannel`
- `0xc749`: `EntitlementTemplateChannel`
- `0xc6d6`: `entitlementtemplatechannelid`
- `0xc6ed`: `entitlementtemplatechannelid`
- `0xc70c`: `entitlementtemplatechannelid`
- `0xc791`: `An entitlement template channel term with the same channel already exists. Specify a different channel and try again.`

## pseudocode

```c

```

## disassembly

```asm
0xc630  ldarg.1
0xc631  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc636  ldstr    aEntitlementtem_0// "EntitlementTemplateChannel"
0xc63b  ldc.i4.0
0xc63c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xc641  stloc.0
0xc642  ldarg.1
0xc643  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xc648  stloc.1
0xc649  ldloc.1
0xc64a  ldloc.0
0xc64b  ldarg.3
0xc64c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0xc651  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::set_Attribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0xc656  ldloc.1
0xc657  ldc.i4.0
0xc658  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::set_ConditionOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xc65d  ldloc.1
0xc65e  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::get_Values()
0xc663  ldarg.2
0xc664  ldarg.3
0xc665  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xc66a  unbox.any [mscorlib]System.Guid
0xc66f  box      [mscorlib]System.Guid
0xc674  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc679  pop
0xc67a  ldarg.1
0xc67b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xc680  stloc.2
0xc681  ldloc.2
0xc682  ldloc.0
0xc683  ldstr    aChannel// "channel"
0xc688  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0xc68d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::set_Attribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0xc692  ldloc.2
0xc693  ldc.i4.0
0xc694  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::set_ConditionOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xc699  ldloc.2
0xc69a  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::get_Values()
0xc69f  ldarg.2
0xc6a0  ldstr    aChannel// "channel"
0xc6a5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xc6aa  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc6af  pop
0xc6b0  ldstr    aEntitlementtem_0// "EntitlementTemplateChannel"
0xc6b5  ldarg.1
0xc6b6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xc6bb  stloc.3
0xc6bc  ldloc.3
0xc6bd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_Conditions()
0xc6c2  ldc.i4.2
0xc6c3  newarr   [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression
0xc6c8  dup
0xc6c9  ldc.i4.0
0xc6ca  ldloc.1
0xc6cb  stelem.ref
0xc6cc  dup
0xc6cd  ldc.i4.1
0xc6ce  ldloc.2
0xc6cf  stelem.ref
0xc6d0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpressionCollection::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression>)
0xc6d5  ldarg.2
0xc6d6  ldstr    aEntitlementtem_2// "entitlementtemplatechannelid"
0xc6db  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xc6e0  brfalse.s loc_C733
0xc6e2  ldarg.1
0xc6e3  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xc6e8  stloc.s  6
0xc6ea  ldloc.s  6
0xc6ec  ldloc.0
0xc6ed  ldstr    aEntitlementtem_2// "entitlementtemplatechannelid"
0xc6f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0xc6f7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::set_Attribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0xc6fc  ldloc.s  6
0xc6fe  ldc.i4.1
0xc6ff  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::set_ConditionOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xc704  ldloc.s  6
0xc706  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::get_Values()
0xc70b  ldarg.2
0xc70c  ldstr    aEntitlementtem_2// "entitlementtemplatechannelid"
0xc711  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xc716  unbox.any [mscorlib]System.Guid
0xc71b  box      [mscorlib]System.Guid
0xc720  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc725  pop
0xc726  ldloc.3
0xc727  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_Conditions()
0xc72c  ldloc.s  6
0xc72e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpressionCollection::Add(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression)
0xc733  ldstr    aEntitlementtem_0// "EntitlementTemplateChannel"
0xc738  ldc.i4.0
0xc739  ldarg.1
0xc73a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xc73f  stloc.s  4
0xc741  ldloc.s  4
0xc743  ldloc.3
0xc744  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0xc749  ldstr    aEntitlementtem_0// "EntitlementTemplateChannel"
0xc74e  ldarg.1
0xc74f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xc754  stloc.s  5
0xc756  ldloc.s  5
0xc758  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xc75d  ldstr    aChannel// "channel"
0xc762  ldc.i4.s 0xD
0xc764  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xc769  pop
0xc76a  ldloc.s  5
0xc76c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xc771  ldloc.s  4
0xc773  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0xc778  ldarg.1
0xc779  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xc77e  stloc.s  7
0xc780  ldarg.0
0xc781  ldloc.s  5
0xc783  ldarg.1
0xc784  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xc789  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xc78e  ldc.i4.0
0xc78f  ble.s    loc_C7A1
0xc791  ldstr    aAnEntitlementT// "An entitlement template channel term wi"...
0xc796  ldc.i4   0x80060602
0xc79b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xc7a0  throw
0xc7a1  leave.s  loc_C7AF
0xc7a3  ldloc.s  7
0xc7a5  brfalse.s loc_C7AE
0xc7a7  ldloc.s  7
0xc7a9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc7ae  endfinally
0xc7af  ret
```
