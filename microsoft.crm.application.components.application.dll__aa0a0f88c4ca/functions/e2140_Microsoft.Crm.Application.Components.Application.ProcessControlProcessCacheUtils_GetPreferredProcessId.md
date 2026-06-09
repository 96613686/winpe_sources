# Microsoft.Crm.Application.Components.Application.ProcessControlProcessCacheUtils::GetPreferredProcessId

- ea: `0xe2140`
- end: `0xe22bb`
- name: `Microsoft.Crm.Application.Components.Application.ProcessControlProcessCacheUtils::GetPreferredProcessId`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xe1db0`

## callees

- `0xe2140`

## string_xrefs

- `0xe21de`: `processid`
- `0xe21f1`: `processid`
- `0xe224b`: `processid`
- `0xe2263`: `processid`
- `0xe2283`: `processid`

## pseudocode

```c

```

## disassembly

```asm
0xe2140  ldarg.1
0xe2141  ldstr    aParententityid_0// "parentEntityId"
0xe2146  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xe214b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe2150  stloc.0
0xe2151  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xe2156  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xe215b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ProcessUnification()
0xe2160  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xe2165  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xe216a  brfalse  loc_E221B
0xe216f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xe2174  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xe2179  ldc.i4.0
0xe217a  ldc.i4.0
0xe217b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xe2180  stloc.1
0xe2181  ldloc.1
0xe2182  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xe2187  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0xe218c  ldc.i4.0
0xe218d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0xe2192  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.BusinessProcessFlowAbstractFactory::get_Instance()
0xe2197  castclass [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.BusinessProcessFlowAbstractFactory
0xe219c  dup
0xe219d  ldloc.1
0xe219e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.BusinessProcessFlowAbstractFactory::CreateExecutionContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe21a3  stloc.2
0xe21a4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IProcessSelectionService [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.BusinessProcessFlowAbstractFactory::CreateProcessSelectionService()
0xe21a9  ldloc.2
0xe21aa  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0xe21af  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xe21b4  ldarg.0
0xe21b5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0xe21ba  stloc.3
0xe21bb  ldc.i4.1
0xe21bc  stloc.s  4
0xe21be  ldarg.1
0xe21bf  ldarg.0
0xe21c0  ldloc.3
0xe21c1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xe21c6  ldc.i4.0
0xe21c7  ldloc.2
0xe21c8  ldloc.s  4
0xe21ca  ldc.i4.0
0xe21cb  ldc.i4.0
0xe21cc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IProcessSelectionService::RetrieveDefaultProcessInstance(valuetype [mscorlib]System.Guid, int32, string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IExecutionContext, bool, bool, bool)
0xe21d1  stloc.s  5
0xe21d3  ldloc.s  5
0xe21d5  brfalse.s loc_E2206
0xe21d7  ldloc.s  5
0xe21d9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0xe21de  ldstr    aProcessid_0// "processid"
0xe21e3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0xe21e8  brfalse.s loc_E2206
0xe21ea  ldloc.s  5
0xe21ec  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0xe21f1  ldstr    aProcessid_0// "processid"
0xe21f6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0xe21fb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0xe2200  unbox.any [mscorlib]System.Guid
0xe2205  stloc.0
0xe2206  ldloc.1
0xe2207  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0xe220c  leave    loc_E2293
0xe2211  ldloc.1
0xe2212  brfalse.s loc_E221A
0xe2214  ldloc.1
0xe2215  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe221a  endfinally
0xe221b  ldarg.0
0xe221c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xe2221  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xe2226  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xe222b  stloc.s  6
0xe222d  ldloc.s  6
0xe222f  ldarga.s 1
0xe2231  constrained. [mscorlib]System.Guid
0xe2237  callvirt instance string [mscorlib]System.Object::ToString()
0xe223c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0xe2241  ldloc.s  6
0xe2243  ldc.i4.1
0xe2244  newarr   [mscorlib]System.String
0xe2249  dup
0xe224a  ldc.i4.0
0xe224b  ldstr    aProcessid_0// "processid"
0xe2250  stelem.ref
0xe2251  ldc.i4.1
0xe2252  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string[], bool)
0xe2257  ldloc.s  6
0xe2259  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_InnerEntity()
0xe225e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xe2263  ldstr    aProcessid_0// "processid"
0xe2268  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0xe226d  brtrue.s loc_E2277
0xe226f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe2274  stloc.0
0xe2275  br.s     loc_E2293
0xe2277  ldloc.s  6
0xe2279  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_InnerEntity()
0xe227e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xe2283  ldstr    aProcessid_0// "processid"
0xe2288  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xe228d  unbox.any [mscorlib]System.Guid
0xe2292  stloc.0
0xe2293  leave.s  loc_E22B3
0xe2295  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0xe229a  stloc.s  7
0xe229c  ldloc.s  7
0xe229e  ldc.i4   0x80048306
0xe22a3  bne.un.s loc_E22B1
0xe22a5  ldarg.2
0xe22a6  ldc.i4.1
0xe22a7  stind.i1
0xe22a8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe22ad  stloc.s  8
0xe22af  leave.s  loc_E22B8
0xe22b1  rethrow
0xe22b3  ldarg.2
0xe22b4  ldc.i4.0
0xe22b5  stind.i1
0xe22b6  ldloc.0
0xe22b7  ret
0xe22b8  ldloc.s  8
0xe22ba  ret
```
