# Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::UpdateWithInvocationSource

- ea: `0x5930`
- end: `0x5a8f`
- name: `Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::UpdateWithInvocationSource`
- size: `351`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5920`
- `0x5c40`

## callees

- `0x5930`
- `0x5bb0`
- `0x6120`
- `0x6140`
- `0x6160`

## string_xrefs

- `0x5948`: `Update`
- `0x59f8`: `Update`
- `0x59fd`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0x5930  ldarg.1
0x5931  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_RelatedEntities()
0x5936  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection>>::get_Count()
0x593b  ldc.i4.0
0x593c  ble.s    loc_5948
0x593e  ldarg.0
0x593f  ldarg.1
0x5940  ldarg.s  4
0x5942  call     instance void Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::UpdateWithRelatedEntities(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5947  ret
0x5948  ldstr    aUpdate// "Update"
0x594d  ldarg.1
0x594e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x5953  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x5958  ldc.i4.0
0x5959  stloc.s  4
0x595b  ldloca.s 4
0x595d  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Extensibility.EntityName
0x5963  callvirt instance string [mscorlib]System.Object::ToString()
0x5968  ldarg.3
0x5969  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MessageProcessorKey::.ctor(string, string, string, int32)
0x596e  stloc.0
0x596f  ldarg.0
0x5970  ldloc.0
0x5971  ldarg.s  4
0x5973  call     instance bool Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::IsPipelineDefined(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MessageProcessorKey key, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5978  brtrue.s loc_598A
0x597a  ldarg.0
0x597b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IPlatformMessageDispatcher Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::_backupDispatcher
0x5980  ldarg.1
0x5981  ldarg.2
0x5982  ldarg.s  4
0x5984  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IPlatformMessageDispatcher::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5989  ret
0x598a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection::.ctor()
0x598f  stloc.1
0x5990  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityToEntityConverter::.ctor()
0x5995  stloc.2
0x5996  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionContextFactory [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionContextFactory::get_Instance()
0x599b  ldarg.s  4
0x599d  ldarg.3
0x599e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionContextFactory::CreateInstance(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, int32)
0x59a3  stloc.3
0x59a4  ldloc.1
0x59a5  ldstr    aTarget// "Target"
0x59aa  ldloc.2
0x59ab  ldloc.3
0x59ac  ldarg.1
0x59ad  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityToEntityConverter::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity)
0x59b2  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x59b7  ldarg.s  4
0x59b9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x59be  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x59c3  ldstr    aConcurrencybeh// "ConcurrencyBehavior"
0x59c8  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x59cd  brfalse.s loc_59F0
0x59cf  ldloc.1
0x59d0  ldstr    aConcurrencybeh// "ConcurrencyBehavior"
0x59d5  ldarg.s  4
0x59d7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x59dc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x59e1  ldstr    aConcurrencybeh// "ConcurrencyBehavior"
0x59e6  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x59eb  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x59f0  ldarg.0
0x59f1  ldarg.s  4
0x59f3  call     instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::GetInternalServiceFactoryFromContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x59f8  ldstr    aUpdate// "Update"
0x59fd  ldstr    aUpdate// "Update"
0x5a02  ldc.i4.0
0x5a03  ldarg.1
0x5a04  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x5a09  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x5a0e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_ObjectTypeCode()
0x5a13  ldc.i4.0
0x5a14  ldloc.1
0x5a15  ldarg.3
0x5a16  ldarg.s  4
0x5a18  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::.ctor(class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory, string, string, int32, int32, int32, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5a1d  stloc.s  5
0x5a1f  ldloc.s  5
0x5a21  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_InternalSharedVariables()
0x5a26  ldstr    aFilter// "Filter"
0x5a2b  ldarg.2
0x5a2c  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x5a31  ldarg.0
0x5a32  ldloc.s  5
0x5a34  call     instance void Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::Execute(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pluginContext)
0x5a39  ldloc.s  5
0x5a3b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_InputParameters()
0x5a40  ldstr    aTarget// "Target"
0x5a45  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x5a4a  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x5a4f  stloc.s  6
0x5a51  ldloc.3
0x5a52  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext::get_OrganizationId()
0x5a57  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x5a5c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5a61  ldloc.s  6
0x5a63  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x5a68  ldc.i4.1
0x5a69  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x5a6e  stloc.s  7
0x5a70  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityToBusinessEntityConverter::.ctor()
0x5a75  ldloc.s  7
0x5a77  ldloc.3
0x5a78  ldloc.s  6
0x5a7a  ldarg.1
0x5a7b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityToBusinessEntityConverter::ConvertUsingExistingBusinessEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity)
0x5a80  leave.s  loc_5A8E
0x5a82  ldloc.s  5
0x5a84  brfalse.s loc_5A8D
0x5a86  ldloc.s  5
0x5a88  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a8d  endfinally
0x5a8e  ret
```
