# Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::CreateWithInvocationSource

- ea: `0x56f0`
- end: `0x5861`
- name: `Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::CreateWithInvocationSource`
- size: `369`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x56e0`
- `0x5c40`

## callees

- `0x56f0`
- `0x5b70`
- `0x6120`
- `0x6140`
- `0x6160`

## string_xrefs

- `0x5707`: `Create`
- `0x5779`: `Create`
- `0x577e`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0x56f0  ldarg.1
0x56f1  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_RelatedEntities()
0x56f6  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection>>::get_Count()
0x56fb  ldc.i4.0
0x56fc  ble.s    loc_5707
0x56fe  ldarg.0
0x56ff  ldarg.1
0x5700  ldarg.3
0x5701  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::CreateWithRelatedEntities(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5706  ret
0x5707  ldstr    aCreate// "Create"
0x570c  ldarg.1
0x570d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x5712  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x5717  ldc.i4.0
0x5718  stloc.s  4
0x571a  ldloca.s 4
0x571c  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Extensibility.EntityName
0x5722  callvirt instance string [mscorlib]System.Object::ToString()
0x5727  ldarg.2
0x5728  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MessageProcessorKey::.ctor(string, string, string, int32)
0x572d  stloc.0
0x572e  ldarg.0
0x572f  ldloc.0
0x5730  ldarg.3
0x5731  call     instance bool Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::IsPipelineDefined(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MessageProcessorKey key, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5736  brtrue.s loc_5746
0x5738  ldarg.0
0x5739  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IPlatformMessageDispatcher Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::_backupDispatcher
0x573e  ldarg.1
0x573f  ldarg.3
0x5740  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IPlatformMessageDispatcher::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5745  ret
0x5746  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection::.ctor()
0x574b  stloc.1
0x574c  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityToEntityConverter::.ctor()
0x5751  stloc.2
0x5752  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionContextFactory [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionContextFactory::get_Instance()
0x5757  ldarg.3
0x5758  ldarg.2
0x5759  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionContextFactory::CreateInstance(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, int32)
0x575e  stloc.3
0x575f  ldloc.1
0x5760  ldstr    aTarget// "Target"
0x5765  ldloc.2
0x5766  ldloc.3
0x5767  ldarg.1
0x5768  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityToEntityConverter::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity)
0x576d  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x5772  ldarg.0
0x5773  ldarg.3
0x5774  call     instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::GetInternalServiceFactoryFromContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5779  ldstr    aCreate// "Create"
0x577e  ldstr    aCreate// "Create"
0x5783  ldc.i4.0
0x5784  ldarg.1
0x5785  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x578a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x578f  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_ObjectTypeCode()
0x5794  ldc.i4.0
0x5795  ldloc.1
0x5796  ldarg.2
0x5797  ldarg.3
0x5798  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::.ctor(class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory, string, string, int32, int32, int32, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x579d  stloc.s  5
0x579f  ldarg.0
0x57a0  ldloc.s  5
0x57a2  call     instance void Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::Execute(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pluginContext)
0x57a7  ldloc.s  5
0x57a9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_OutputParameters()
0x57ae  ldstr    aId// "id"
0x57b3  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x57b8  unbox.any [mscorlib]System.Guid
0x57bd  stloc.s  6
0x57bf  ldloc.s  5
0x57c1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_InputParameters()
0x57c6  ldstr    aTarget// "Target"
0x57cb  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x57d0  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x57d5  stloc.s  7
0x57d7  ldloc.3
0x57d8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext::get_OrganizationId()
0x57dd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x57e2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x57e7  ldloc.s  7
0x57e9  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x57ee  ldc.i4.1
0x57ef  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x57f4  stloc.s  8
0x57f6  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityToBusinessEntityConverter::.ctor()
0x57fb  ldloc.s  8
0x57fd  ldloc.3
0x57fe  ldloc.s  7
0x5800  ldarg.1
0x5801  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityToBusinessEntityConverter::ConvertUsingExistingBusinessEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity)
0x5806  ldarg.1
0x5807  ldarg.1
0x5808  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x580d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x5812  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x5817  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x581c  brfalse.s loc_583B
0x581e  ldarg.1
0x581f  ldarg.1
0x5820  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x5825  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x582a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x582f  ldloc.s  6
0x5831  box      [mscorlib]System.Guid
0x5836  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x583b  ldloc.s  6
0x583d  ldarg.1
0x583e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x5843  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5848  ldarg.3
0x5849  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x584e  stloc.s  9
0x5850  leave.s  loc_585E
0x5852  ldloc.s  5
0x5854  brfalse.s loc_585D
0x5856  ldloc.s  5
0x5858  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x585d  endfinally
0x585e  ldloc.s  9
0x5860  ret
```
