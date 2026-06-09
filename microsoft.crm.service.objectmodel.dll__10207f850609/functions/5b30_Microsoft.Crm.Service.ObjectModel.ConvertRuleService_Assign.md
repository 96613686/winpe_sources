# Microsoft.Crm.Service.ObjectModel.ConvertRuleService::Assign

- ea: `0x5b30`
- end: `0x5cc4`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleService::Assign`
- size: `404`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x5b30`
- `0x5dc0`
- `0x5e20`

## pseudocode

```c

```

## disassembly

```asm
0x5b30  ldc.i4.0
0x5b31  stloc.0
0x5b32  ldarg.0
0x5b33  ldarg.1
0x5b34  ldarg.3
0x5b35  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.ConvertRuleService::RetrieveConvertRuleRecord(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5b3a  stloc.1
0x5b3b  ldarg.3
0x5b3c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x5b41  box      [mscorlib]System.Guid
0x5b46  ldarg.2
0x5b47  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x5b4c  box      [mscorlib]System.Guid
0x5b51  call     bool [mscorlib]System.Object::Equals(object, object)
0x5b56  brtrue.s loc_5B77
0x5b58  ldloc.1
0x5b59  ldstr    aStatecode// "statecode"
0x5b5e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5b63  unbox.any [mscorlib]System.Int32
0x5b68  brfalse.s loc_5B77
0x5b6a  ldarg.0
0x5b6b  ldarg.1
0x5b6c  ldc.i4.0
0x5b6d  ldc.i4.1
0x5b6e  ldarg.3
0x5b6f  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5b74  pop
0x5b75  ldc.i4.1
0x5b76  stloc.0
0x5b77  ldarg.0
0x5b78  ldarg.1
0x5b79  ldarg.2
0x5b7a  ldarg.3
0x5b7b  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Assign(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5b80  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService::.ctor()
0x5b85  stloc.2
0x5b86  ldarg.3
0x5b87  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5b8c  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity::.ctor(valuetype [mscorlib]System.Guid)
0x5b91  stloc.3
0x5b92  ldloc.1
0x5b93  ldstr    aWorkflowid// "workflowid"
0x5b98  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5b9d  brfalse.s loc_5BE6
0x5b9f  ldloc.1
0x5ba0  ldstr    aWorkflowid// "workflowid"
0x5ba5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5baa  unbox.any [mscorlib]System.Guid
0x5baf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5bb4  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5bb9  brfalse.s loc_5BE6
0x5bbb  ldloc.0
0x5bbc  brtrue.s loc_5BE6
0x5bbe  ldloc.1
0x5bbf  ldstr    aWorkflowid// "workflowid"
0x5bc4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5bc9  unbox.any [mscorlib]System.Guid
0x5bce  ldloc.3
0x5bcf  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x5bd4  ldarg.3
0x5bd5  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5bda  stloc.s  4
0x5bdc  ldloc.2
0x5bdd  ldloc.s  4
0x5bdf  ldarg.2
0x5be0  ldarg.3
0x5be1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Assign(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5be6  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x5beb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x5bf0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AnyChanelToAnyEntityRecordCreation()
0x5bf5  ldarg.3
0x5bf6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5bfb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x5c00  ldarg.3
0x5c01  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5c06  ldarg.3
0x5c07  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x5c0c  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x5c11  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x5c16  brfalse  loc_5CC3
0x5c1b  ldarg.0
0x5c1c  ldloc.1
0x5c1d  ldstr    aConvertruleid_0// "convertruleid"
0x5c22  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5c27  unbox.any [mscorlib]System.Guid
0x5c2c  ldarg.3
0x5c2d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.ConvertRuleService::RetrieveConvertRuleItemWorkflows(valuetype [mscorlib]System.Guid convertRuleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5c32  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5c37  stloc.s  5
0x5c39  br.s     loc_5CA3
0x5c3b  ldloc.s  5
0x5c3d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5c42  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x5c47  stloc.s  6
0x5c49  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService::.ctor()
0x5c4e  stloc.2
0x5c4f  ldloc.s  6
0x5c51  ldstr    aWorkflowid// "workflowid"
0x5c56  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5c5b  brfalse.s loc_5CA3
0x5c5d  ldloc.s  6
0x5c5f  ldstr    aWorkflowid// "workflowid"
0x5c64  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5c69  unbox.any [mscorlib]System.Guid
0x5c6e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5c73  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5c78  brfalse.s loc_5CA3
0x5c7a  ldloc.s  6
0x5c7c  ldstr    aWorkflowid// "workflowid"
0x5c81  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5c86  unbox.any [mscorlib]System.Guid
0x5c8b  ldloc.3
0x5c8c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x5c91  ldarg.3
0x5c92  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5c97  stloc.s  7
0x5c99  ldloc.2
0x5c9a  ldloc.s  7
0x5c9c  ldarg.2
0x5c9d  ldarg.3
0x5c9e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Assign(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5ca3  ldloc.s  5
0x5ca5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5caa  brtrue.s loc_5C3B
0x5cac  leave.s  loc_5CC3
0x5cae  ldloc.s  5
0x5cb0  isinst   [mscorlib]System.IDisposable
0x5cb5  stloc.s  8
0x5cb7  ldloc.s  8
0x5cb9  brfalse.s loc_5CC2
0x5cbb  ldloc.s  8
0x5cbd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5cc2  endfinally
0x5cc3  ret
```
