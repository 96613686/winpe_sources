# Microsoft.Crm.Metadata.AttributeService::CreateMultiple_0

- ea: `0x1a900`
- end: `0x1a9f9`
- name: `Microsoft.Crm.Metadata.AttributeService::CreateMultiple_0`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a8b0`

## callees

- `0x184e0`
- `0x1a900`
- `0x1c120`
- `0x21220`
- `0x5a810`

## string_xrefs

- `0x1a924`: `prvReadAttribute`
- `0x1a90d`: `prvCreateAttribute`
- `0x1a9d8`: `AttributeService.CreateMultiple caught exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1a900  ldarg.3
0x1a901  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a906  pop
0x1a907  ldarg.3
0x1a908  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x1a90d  ldstr    aPrvcreateattri// "prvCreateAttribute"
0x1a912  ldarg.3
0x1a913  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1a918  ldarg.3
0x1a919  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1a91e  ldarg.3
0x1a91f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x1a924  ldstr    aPrvreadattribu// "prvReadAttribute"
0x1a929  ldarg.3
0x1a92a  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1a92f  ldarg.3
0x1a930  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1a935  ldarg.3
0x1a936  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x1a93b  stloc.0
0x1a93c  ldarg.3
0x1a93d  ldc.i4.1
0x1a93e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoAddRootsContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AddRootsOption)
0x1a943  stloc.1
0x1a944  ldarg.3
0x1a945  ldarg.3
0x1a946  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1a94b  ldc.i4.1
0x1a94c  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::.ctor()
0x1a951  newobj   instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Guid, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject)
0x1a956  stloc.2
0x1a957  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a95c  stloc.3
0x1a95d  ldc.i4.0
0x1a95e  stloc.s  4
0x1a960  br.s     loc_1A992
0x1a962  ldarg.2
0x1a963  ldloc.s  4
0x1a965  ldelem.ref
0x1a966  ldarg.1
0x1a967  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::set_EntityId(valuetype [mscorlib]System.Guid value)
0x1a96c  ldarg.2
0x1a96d  ldloc.s  4
0x1a96f  ldelem.ref
0x1a970  ldloc.2
0x1a971  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x1a976  ldc.i4.0
0x1a977  ceq
0x1a979  ldarg.3
0x1a97a  ldloc.2
0x1a97b  call     void Microsoft.Crm.Metadata.AttributeService::ValidateForCreate(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, bool validateSchemaName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x1a980  ldarg.2
0x1a981  ldloc.s  4
0x1a983  ldelem.ref
0x1a984  ldloc.2
0x1a985  ldarg.3
0x1a986  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::CreateInternal(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1a98b  stloc.3
0x1a98c  ldloc.s  4
0x1a98e  ldc.i4.1
0x1a98f  add
0x1a990  stloc.s  4
0x1a992  ldloc.s  4
0x1a994  ldarg.2
0x1a995  ldlen
0x1a996  conv.i4
0x1a997  blt.s    loc_1A962
0x1a999  ldloc.2
0x1a99a  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x1a99f  ldloc.3
0x1a9a0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a9a5  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a9aa  brfalse.s loc_1A9B5
0x1a9ac  ldarg.3
0x1a9ad  ldc.i4.4
0x1a9ae  ldloc.3
0x1a9af  ldc.i4.2
0x1a9b0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::AddDependencyOperation(valuetype [Microsoft.Crm.Core]Microsoft.Crm.DependencyOperationType, valuetype [mscorlib]System.Guid, int32)
0x1a9b5  ldloc.0
0x1a9b6  brfalse.s loc_1A9BE
0x1a9b8  ldarg.3
0x1a9b9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x1a9be  leave.s  loc_1A9CA
0x1a9c0  ldloc.1
0x1a9c1  brfalse.s loc_1A9C9
0x1a9c3  ldloc.1
0x1a9c4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a9c9  endfinally
0x1a9ca  leave.s  loc_1A9F8
0x1a9cc  stloc.s  5
0x1a9ce  ldloc.s  5
0x1a9d0  ldarg.3
0x1a9d1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1a9d6  ldc.i4.s 0x19
0x1a9d8  ldstr    aAttributeservi_0// "AttributeService.CreateMultiple caught "...
0x1a9dd  ldc.i4.1
0x1a9de  newarr   [mscorlib]System.Object
0x1a9e3  dup
0x1a9e4  ldc.i4.0
0x1a9e5  ldloc.s  5
0x1a9e7  stelem.ref
0x1a9e8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a9ed  ldloc.0
0x1a9ee  brfalse.s loc_1A9F6
0x1a9f0  ldarg.3
0x1a9f1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0x1a9f6  rethrow
0x1a9f8  ret
```
