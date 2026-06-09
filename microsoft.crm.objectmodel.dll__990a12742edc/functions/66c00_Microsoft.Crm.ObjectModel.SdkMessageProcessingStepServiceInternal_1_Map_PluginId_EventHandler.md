# Microsoft.Crm.ObjectModel.SdkMessageProcessingStepServiceInternal`1::Map_PluginId_EventHandler

- ea: `0x66c00`
- end: `0x66dd7`
- name: `Microsoft.Crm.ObjectModel.SdkMessageProcessingStepServiceInternal`1::Map_PluginId_EventHandler`
- size: `471`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x66c00`

## string_xrefs

- `0x66c1c`: `serviceendpoint`
- `0x66c29`: `plugintypeid`
- `0x66c4c`: `plugintypeid`
- `0x66c7d`: `plugintypeid`
- `0x66ca7`: `plugintypeid`
- `0x66cc6`: `plugintypeid`
- `0x66d1a`: `plugintypeid`
- `0x66d27`: `plugintypeid`
- `0x66d48`: `plugintypeid`
- `0x66dac`: `plugintypeid`
- `0x66dc2`: `plugintypeid`
- `0x66c0a`: `plugintype`
- `0x66ce4`: `PluginTypeId and EventHandler should be the same or only one should be provided.`
- `0x66d6e`: `PluginTypeId and EventHandler should be the same or only one should be provided.`

## pseudocode

```c

```

## disassembly

```asm
0x66c00  ldarg.1
0x66c01  brtrue.s loc_66C04
0x66c03  ret
0x66c04  ldarg.2
0x66c05  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x66c0a  ldstr    aPlugintype_0// "plugintype"
0x66c0f  ldc.i4.1
0x66c10  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x66c15  stloc.0
0x66c16  ldarg.2
0x66c17  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x66c1c  ldstr    aServiceendpoin_0// "serviceendpoint"
0x66c21  ldc.i4.1
0x66c22  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x66c27  stloc.1
0x66c28  ldarg.1
0x66c29  ldstr    aPlugintypeid// "plugintypeid"
0x66c2e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x66c33  brtrue   loc_66CEF
0x66c38  ldarg.1
0x66c39  ldstr    aEventhandler// "eventhandler"
0x66c3e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x66c43  brfalse.s loc_66C7C
0x66c45  ldarg.1
0x66c46  ldstr    aEventhandler// "eventhandler"
0x66c4b  ldarg.1
0x66c4c  ldstr    aPlugintypeid// "plugintypeid"
0x66c51  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66c56  unbox.any [mscorlib]System.Guid
0x66c5b  box      [mscorlib]System.Guid
0x66c60  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x66c65  ldarg.1
0x66c66  ldstr    aEventhandlerty// "eventhandlertypecode"
0x66c6b  ldloc.0
0x66c6c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x66c71  box      [mscorlib]System.Int32
0x66c76  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x66c7b  ret
0x66c7c  ldarg.1
0x66c7d  ldstr    aPlugintypeid// "plugintypeid"
0x66c82  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66c87  unbox.any [mscorlib]System.Guid
0x66c8c  ldarg.1
0x66c8d  ldstr    aEventhandler// "eventhandler"
0x66c92  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66c97  unbox.any [mscorlib]System.Guid
0x66c9c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x66ca1  brfalse  loc_66DD6
0x66ca6  ldarg.1
0x66ca7  ldstr    aPlugintypeid// "plugintypeid"
0x66cac  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66cb1  unbox.any [mscorlib]System.Guid
0x66cb6  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.ServiceEndpointService::ServiceEndpointPluginId
0x66cbb  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x66cc0  brfalse  loc_66DD6
0x66cc5  ldarg.1
0x66cc6  ldstr    aPlugintypeid// "plugintypeid"
0x66ccb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66cd0  unbox.any [mscorlib]System.Guid
0x66cd5  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.ServiceEndpointService::WebhookPluginId
0x66cda  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x66cdf  brfalse  loc_66DD6
0x66ce4  ldstr    aPlugintypeidAn// "PluginTypeId and EventHandler should be"...
0x66ce9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x66cee  throw
0x66cef  ldarg.1
0x66cf0  ldstr    aEventhandler// "eventhandler"
0x66cf5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x66cfa  brtrue   loc_66DD6
0x66cff  ldarg.1
0x66d00  ldstr    aEventhandlerty// "eventhandlertypecode"
0x66d05  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66d0a  unbox.any [mscorlib]System.Int32
0x66d0f  stloc.2
0x66d10  ldloc.2
0x66d11  ldloc.0
0x66d12  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x66d17  bne.un.s loc_66D79
0x66d19  ldarg.1
0x66d1a  ldstr    aPlugintypeid// "plugintypeid"
0x66d1f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x66d24  brfalse.s loc_66D47
0x66d26  ldarg.1
0x66d27  ldstr    aPlugintypeid// "plugintypeid"
0x66d2c  ldarg.1
0x66d2d  ldstr    aEventhandler// "eventhandler"
0x66d32  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66d37  unbox.any [mscorlib]System.Guid
0x66d3c  box      [mscorlib]System.Guid
0x66d41  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x66d46  ret
0x66d47  ldarg.1
0x66d48  ldstr    aPlugintypeid// "plugintypeid"
0x66d4d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66d52  unbox.any [mscorlib]System.Guid
0x66d57  ldarg.1
0x66d58  ldstr    aEventhandler// "eventhandler"
0x66d5d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66d62  unbox.any [mscorlib]System.Guid
0x66d67  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x66d6c  brfalse.s loc_66DD6
0x66d6e  ldstr    aPlugintypeidAn// "PluginTypeId and EventHandler should be"...
0x66d73  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x66d78  throw
0x66d79  ldloc.2
0x66d7a  ldloc.1
0x66d7b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x66d80  bne.un.s loc_66DD6
0x66d82  ldarg.0
0x66d83  ldarg.2
0x66d84  ldarg.1
0x66d85  ldstr    aEventhandler// "eventhandler"
0x66d8a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66d8f  unbox.any [mscorlib]System.Guid
0x66d94  call     instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ServiceEndpoint class Microsoft.Crm.ObjectModel.SdkMessageProcessingStepServiceInternal`1<var<u1>>::GetServiceEndpointEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Guid)
0x66d99  ldstr    aContract// "contract"
0x66d9e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x66da3  unbox.any [mscorlib]System.Int32
0x66da8  ldc.i4.8
0x66da9  beq.s    loc_66DC1
0x66dab  ldarg.1
0x66dac  ldstr    aPlugintypeid// "plugintypeid"
0x66db1  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.ServiceEndpointService::ServiceEndpointPluginId
0x66db6  box      [mscorlib]System.Guid
0x66dbb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x66dc0  ret
0x66dc1  ldarg.1
0x66dc2  ldstr    aPlugintypeid// "plugintypeid"
0x66dc7  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.ServiceEndpointService::WebhookPluginId
0x66dcc  box      [mscorlib]System.Guid
0x66dd1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x66dd6  ret
```
