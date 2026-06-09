# Microsoft.Crm.Service.ObjectModel.EntitlementService::GetEntitlementTemplateChannels

- ea: `0xc1a0`
- end: `0xc26d`
- name: `Microsoft.Crm.Service.ObjectModel.EntitlementService::GetEntitlementTemplateChannels`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xc1a0`

## string_xrefs

- `0xc1a6`: `EntitlementTemplateChannel`
- `0xc1ee`: `EntitlementTemplateChannel`
- `0xc20f`: `EntitlementTemplateChannel`
- `0xc1d4`: `entitlementtemplateid`

## pseudocode

```c

```

## disassembly

```asm
0xc1a0  ldarg.1
0xc1a1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc1a6  ldstr    aEntitlementtem_0// "EntitlementTemplateChannel"
0xc1ab  ldc.i4.0
0xc1ac  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xc1b1  stloc.0
0xc1b2  ldarg.1
0xc1b3  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xc1b8  stloc.1
0xc1b9  ldloc.1
0xc1ba  ldloc.0
0xc1bb  ldarg.2
0xc1bc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0xc1c1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::set_Attribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0xc1c6  ldloc.1
0xc1c7  ldc.i4.0
0xc1c8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::set_ConditionOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xc1cd  ldloc.1
0xc1ce  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::get_Values()
0xc1d3  ldarg.3
0xc1d4  ldstr    aEntitlementtem_1// "entitlementtemplateid"
0xc1d9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xc1de  unbox.any [mscorlib]System.Guid
0xc1e3  box      [mscorlib]System.Guid
0xc1e8  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc1ed  pop
0xc1ee  ldstr    aEntitlementtem_0// "EntitlementTemplateChannel"
0xc1f3  ldarg.1
0xc1f4  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xc1f9  stloc.2
0xc1fa  ldloc.2
0xc1fb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_Conditions()
0xc200  ldc.i4.1
0xc201  newarr   [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression
0xc206  dup
0xc207  ldc.i4.0
0xc208  ldloc.1
0xc209  stelem.ref
0xc20a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpressionCollection::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression>)
0xc20f  ldstr    aEntitlementtem_0// "EntitlementTemplateChannel"
0xc214  ldarg.1
0xc215  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xc21a  stloc.3
0xc21b  ldloc.3
0xc21c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xc221  ldloc.2
0xc222  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0xc227  ldloc.3
0xc228  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xc22d  ldstr    aChannel// "channel"
0xc232  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xc237  ldloc.3
0xc238  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xc23d  ldstr    aTotalterms// "totalterms"
0xc242  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xc247  ldnull
0xc248  stloc.s  4
0xc24a  ldarg.1
0xc24b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xc250  stloc.s  5
0xc252  ldarg.0
0xc253  ldloc.3
0xc254  ldarg.1
0xc255  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xc25a  stloc.s  4
0xc25c  leave.s  loc_C26A
0xc25e  ldloc.s  5
0xc260  brfalse.s loc_C269
0xc262  ldloc.s  5
0xc264  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc269  endfinally
0xc26a  ldloc.s  4
0xc26c  ret
```
