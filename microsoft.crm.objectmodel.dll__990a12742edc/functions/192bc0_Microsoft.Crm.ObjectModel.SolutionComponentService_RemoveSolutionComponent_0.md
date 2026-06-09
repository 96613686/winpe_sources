# Microsoft.Crm.ObjectModel.SolutionComponentService::RemoveSolutionComponent_0

- ea: `0x192bc0`
- end: `0x192ec5`
- name: `Microsoft.Crm.ObjectModel.SolutionComponentService::RemoveSolutionComponent_0`
- size: `773`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x192bb0`
- `0x193010`
- `0x193110`

## callees

- `0x1913c0`
- `0x191880`
- `0x192930`
- `0x192a30`
- `0x192bc0`
- `0x192ed0`
- `0x193010`
- `0x193220`
- `0x1959f0`
- `0x1b2450`
- `0x1b2790`

## string_xrefs

- `0x192ccc`: `componenttype`
- `0x192ddd`: `configurationpageid`
- `0x192e0b`: `configurationpageid`
- `0x192e1a`: `configurationpageid`
- `0x192e53`: `configurationpageid`
- `0x192bc1`: `componentId`
- `0x192cb1`: `solutioncomponentid`
- `0x192cc4`: `solutioncomponentid`
- `0x192d61`: `solutioncomponentid`
- `0x192d7d`: `solutioncomponentid`
- `0x192ce4`: `rootsolutioncomponentid`
- `0x192c39`: `SolutionComponent_BEGIN_{0}.RemoveSolutionComponent`
- `0x192c65`: `Can only remove root components.  Component type {0} is not supported`
- `0x192e86`: `SolutionComponent_END_{0}.RemoveSolutionComponent`

## pseudocode

```c

```

## disassembly

```asm
0x192bc0  ldarg.1
0x192bc1  ldstr    aComponentid_0// "componentId"
0x192bc6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x192bcb  ldarg.3
0x192bcc  ldstr    aSolutionunique_0// "solutionUniqueName"
0x192bd1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x192bd6  ldarg.s  4
0x192bd8  ldstr    aContext// "context"
0x192bdd  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x192be2  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x192be7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x192bec  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_SolutionSegmentation()
0x192bf1  ldarg.s  4
0x192bf3  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x192bf8  stloc.0
0x192bf9  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x192bfe  stloc.1
0x192bff  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x192c04  ldarg.s  4
0x192c06  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x192c0b  ldarg.s  4
0x192c0d  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x192c12  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x192c17  callvirt instance string [mscorlib]System.Object::ToString()
0x192c1c  stloc.2
0x192c1d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x192c22  stloc.3
0x192c23  ldc.i4.0
0x192c24  stloc.s  4
0x192c26  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x192c2b  stloc.s  5
0x192c2d  ldsfld   string [mscorlib]System.String::Empty
0x192c32  stloc.s  6
0x192c34  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x192c39  ldstr    aSolutioncompon_5// "SolutionComponent_BEGIN_{0}.RemoveSolut"...
0x192c3e  ldc.i4.1
0x192c3f  newarr   [mscorlib]System.Object
0x192c44  dup
0x192c45  ldc.i4.0
0x192c46  ldarg.0
0x192c47  stelem.ref
0x192c48  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x192c4d  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x192c52  ldloc.0
0x192c53  brtrue.s loc_192C89
0x192c55  ldarg.2
0x192c56  ldarg.1
0x192c57  ldarg.s  4
0x192c59  call     bool Microsoft.Crm.ObjectModel.SolutionComponentHelper::IsComponentRoot(int32 componentType, valuetype [mscorlib]System.Guid componentId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x192c5e  brtrue.s loc_192C89
0x192c60  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x192c65  ldstr    aCanOnlyRemoveR_0// "Can only remove root components.  Compo"...
0x192c6a  ldc.i4.1
0x192c6b  newarr   [mscorlib]System.Object
0x192c70  dup
0x192c71  ldc.i4.0
0x192c72  ldarg.2
0x192c73  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrievePlatformName(int32)
0x192c78  stelem.ref
0x192c79  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x192c7e  ldc.i4   0x80040203
0x192c83  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x192c88  throw
0x192c89  ldarg.s  5
0x192c8b  brfalse.s loc_192C9A
0x192c8d  ldarg.0
0x192c8e  ldarg.3
0x192c8f  ldarg.s  4
0x192c91  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.SolutionComponentService::ValidateRestrictedSolutions(string solutionUniqueName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x192c96  stloc.s  5
0x192c98  br.s     loc_192CA9
0x192c9a  newobj   instance void Microsoft.Crm.ObjectModel.SolutionService::.ctor()
0x192c9f  ldarg.3
0x192ca0  ldarg.s  4
0x192ca2  call     instance valuetype [mscorlib]System.Guid class Microsoft.Crm.ObjectModel.SolutionServiceInternal`1<class Microsoft.Crm.ObjectModel.ProvisioningOff>::RetrieveSolutionId(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x192ca7  stloc.s  5
0x192ca9  ldc.i4.1
0x192caa  newarr   [mscorlib]System.String
0x192caf  dup
0x192cb0  ldc.i4.0
0x192cb1  ldstr    aSolutioncompon_2// "solutioncomponentid"
0x192cb6  stelem.ref
0x192cb7  stloc.s  7
0x192cb9  ldloc.0
0x192cba  brfalse.s loc_192CEC
0x192cbc  ldc.i4.5
0x192cbd  newarr   [mscorlib]System.String
0x192cc2  dup
0x192cc3  ldc.i4.0
0x192cc4  ldstr    aSolutioncompon_2// "solutioncomponentid"
0x192cc9  stelem.ref
0x192cca  dup
0x192ccb  ldc.i4.1
0x192ccc  ldstr    aComponenttype// "componenttype"
0x192cd1  stelem.ref
0x192cd2  dup
0x192cd3  ldc.i4.2
0x192cd4  ldstr    aSolutionid// "solutionid"
0x192cd9  stelem.ref
0x192cda  dup
0x192cdb  ldc.i4.3
0x192cdc  ldsfld   string Microsoft.Crm.ObjectModel.SolutionComponentService::rootComponentBehavior
0x192ce1  stelem.ref
0x192ce2  dup
0x192ce3  ldc.i4.4
0x192ce4  ldstr    aRootsolutionco// "rootsolutioncomponentid"
0x192ce9  stelem.ref
0x192cea  stloc.s  7
0x192cec  ldarg.s  5
0x192cee  brfalse.s loc_192CFB
0x192cf0  ldarg.0
0x192cf1  ldloc.s  5
0x192cf3  ldarg.3
0x192cf4  ldarg.s  4
0x192cf6  call     instance void Microsoft.Crm.ObjectModel.SolutionComponentService::ValidateSolutionIsEditable(valuetype [mscorlib]System.Guid solutionId, string solutionUniqueName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x192cfb  ldnull
0x192cfc  stloc.s  8
0x192cfe  ldarg.0
0x192cff  ldarg.1
0x192d00  ldarg.2
0x192d01  ldloc.s  5
0x192d03  ldloc.s  7
0x192d05  ldloca.s 8
0x192d07  ldarg.s  4
0x192d09  call     instance bool Microsoft.Crm.ObjectModel.SolutionComponentService::TryRetrieveSolutionComponent(valuetype [mscorlib]System.Guid objectId, int32 componentType, valuetype [mscorlib]System.Guid solutionId, string[] columnSet, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity& foundEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x192d0e  brtrue.s loc_192D3D
0x192d10  ldc.i4   0x8004F021
0x192d15  ldc.i4.3
0x192d16  newarr   [mscorlib]System.Object
0x192d1b  dup
0x192d1c  ldc.i4.0
0x192d1d  ldarg.2
0x192d1e  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrievePlatformName(int32)
0x192d23  stelem.ref
0x192d24  dup
0x192d25  ldc.i4.1
0x192d26  ldarg.1
0x192d27  box      [mscorlib]System.Guid
0x192d2c  stelem.ref
0x192d2d  dup
0x192d2e  ldc.i4.2
0x192d2f  ldloc.s  5
0x192d31  box      [mscorlib]System.Guid
0x192d36  stelem.ref
0x192d37  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x192d3c  throw
0x192d3d  ldloc.0
0x192d3e  brfalse.s loc_192D7B
0x192d40  ldarg.2
0x192d41  ldarg.1
0x192d42  ldarg.s  4
0x192d44  call     bool Microsoft.Crm.ObjectModel.SolutionComponentHelper::IsComponentRoot(int32 componentType, valuetype [mscorlib]System.Guid componentId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x192d49  brfalse.s loc_192D7B
0x192d4b  ldloc.s  8
0x192d4d  ldsfld   string Microsoft.Crm.ObjectModel.SolutionComponentService::rootComponentBehavior
0x192d52  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x192d57  unbox.any [mscorlib]System.Int32
0x192d5c  brfalse.s loc_192D7B
0x192d5e  ldarg.0
0x192d5f  ldloc.s  8
0x192d61  ldstr    aSolutioncompon_2// "solutioncomponentid"
0x192d66  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x192d6b  unbox.any [mscorlib]System.Guid
0x192d70  ldloc.s  5
0x192d72  ldarg.s  4
0x192d74  call     instance int32 Microsoft.Crm.ObjectModel.SolutionComponentService::RemoveAllSubcomponentsOfRoot(valuetype [mscorlib]System.Guid rootSolutionComponentId, valuetype [mscorlib]System.Guid solutionId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x192d79  stloc.s  4
0x192d7b  ldloc.s  8
0x192d7d  ldstr    aSolutioncompon_2// "solutioncomponentid"
0x192d82  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x192d87  unbox.any [mscorlib]System.Guid
0x192d8c  ldloc.s  8
0x192d8e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x192d93  ldarg.s  4
0x192d95  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x192d9a  stloc.s  9
0x192d9c  ldarg.0
0x192d9d  ldarg.2
0x192d9e  ldarg.1
0x192d9f  ldloc.s  5
0x192da1  call     instance void Microsoft.Crm.ObjectModel.SolutionComponentService::SetAdditionalDetailsForTelemetry(int32 componentType, valuetype [mscorlib]System.Guid objectId, valuetype [mscorlib]System.Guid solutionId)
0x192da6  ldarg.0
0x192da7  ldloc.s  9
0x192da9  ldarg.s  4
0x192dab  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x192db0  ldarg.2
0x192db1  ldc.i4.s 0x1D
0x192db3  bne.un.s loc_192DC0
0x192db5  ldarg.0
0x192db6  ldarg.1
0x192db7  ldarg.s  4
0x192db9  ldloc.s  5
0x192dbb  call     instance void Microsoft.Crm.ObjectModel.SolutionComponentService::RemoveTaskBasedFormIfNeeded(valuetype [mscorlib]System.Guid componentId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid solutionId)
0x192dc0  ldarg.2
0x192dc1  ldc.i4.s 0x3D
0x192dc3  bne.un   loc_192E6D
0x192dc8  ldstr    aSolution// "Solution"
0x192dcd  ldarg.s  4
0x192dcf  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x192dd4  stloc.s  0xA
0x192dd6  ldloc.s  0xA
0x192dd8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x192ddd  ldstr    aConfigurationp// "configurationpageid"
0x192de2  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x192de7  newobj   instance void Microsoft.Crm.ObjectModel.SolutionService::.ctor()
0x192dec  stloc.s  0xB
0x192dee  ldloc.s  0xB
0x192df0  ldloc.s  5
0x192df2  ldstr    aSolution// "Solution"
0x192df7  ldarg.s  4
0x192df9  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x192dfe  ldloc.s  0xA
0x192e00  ldarg.s  4
0x192e02  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x192e07  stloc.s  0xC
0x192e09  ldloc.s  0xC
0x192e0b  ldstr    aConfigurationp// "configurationpageid"
0x192e10  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x192e15  brtrue.s loc_192E6D
0x192e17  ldarg.1
0x192e18  ldloc.s  0xC
0x192e1a  ldstr    aConfigurationp// "configurationpageid"
0x192e1f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x192e24  unbox.any [mscorlib]System.Guid
0x192e29  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x192e2e  brfalse.s loc_192E6D
0x192e30  ldarg.s  4
0x192e32  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x192e37  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Solution::.ctor(valuetype [mscorlib]System.Guid)
0x192e3c  stloc.s  0xD
0x192e3e  ldloc.s  0xD
0x192e40  ldstr    aSolutionid// "solutionid"
0x192e45  ldloc.s  5
0x192e47  box      [mscorlib]System.Guid
0x192e4c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x192e51  ldloc.s  0xD
0x192e53  ldstr    aConfigurationp// "configurationpageid"
0x192e58  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x192e5d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x192e62  ldloc.s  0xB
0x192e64  ldloc.s  0xD
0x192e66  ldarg.s  4
0x192e68  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x192e6d  ldloc.s  9
0x192e6f  stloc.s  0xE
0x192e71  leave.s  loc_192EC2
0x192e73  callvirt instance string [mscorlib]System.Exception::get_Message()
0x192e78  callvirt instance string [mscorlib]System.Object::ToString()
0x192e7d  stloc.s  6
0x192e7f  rethrow
0x192e81  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x192e86  ldstr    aSolutioncompon_6// "SolutionComponent_END_{0}.RemoveSolutio"...
0x192e8b  ldc.i4.1
0x192e8c  newarr   [mscorlib]System.Object
0x192e91  dup
0x192e92  ldc.i4.0
0x192e93  ldarg.0
0x192e94  stelem.ref
0x192e95  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x192e9a  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x192e9f  call     class Microsoft.Crm.ObjectModel.SolutionTelemetryEvents Microsoft.Crm.ObjectModel.SolutionTelemetryEvents::get_Instance()
0x192ea4  ldarg.s  4
0x192ea6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x192eab  ldloc.1
0x192eac  ldloc.2
0x192ead  ldarg.1
0x192eae  ldarg.2
0x192eaf  ldloc.s  5
0x192eb1  ldarg.3
0x192eb2  ldloc.3
0x192eb3  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x192eb8  ldloc.s  4
0x192eba  ldloc.s  6
0x192ebc  callvirt instance void Microsoft.Crm.ObjectModel.SolutionTelemetryEvents::RemoveSolutionComponentCompleted(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string databaseVersion, valuetype [mscorlib]System.Guid rootComponentId, int32 componentType, valuetype [mscorlib]System.Guid solutionId, string solutionUniqueName, int64 executionTime, int32 subcomponentsSelectedToRemove, string removeSolutionComponentException)
0x192ec1  endfinally
0x192ec2  ldloc.s  0xE
0x192ec4  ret
```
