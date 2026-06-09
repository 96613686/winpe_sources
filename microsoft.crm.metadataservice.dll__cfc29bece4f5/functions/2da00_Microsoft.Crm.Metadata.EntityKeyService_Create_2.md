# Microsoft.Crm.Metadata.EntityKeyService::Create_2

- ea: `0x2da00`
- end: `0x2db04`
- name: `Microsoft.Crm.Metadata.EntityKeyService::Create_2`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x2d9e0`

## callees

- `0x2d860`
- `0x2da00`
- `0x2dbc0`
- `0x2ddd0`
- `0x5a810`

## string_xrefs

- `0x2da4b`: `prvReadEntityKey`
- `0x2da31`: `prvCreateEntityKey`
- `0x2dae1`: `EntityKeyService.Create caught exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2da00  ldarg.2
0x2da01  ldstr    aEntitykeyinfo// "entityKeyInfo"
0x2da06  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2da0b  ldarg.3
0x2da0c  ldstr    aMetadatahelper// "metadataHelper"
0x2da11  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2da16  ldarg.s  4
0x2da18  ldstr    aContext// "context"
0x2da1d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2da22  ldarg.s  4
0x2da24  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2da29  pop
0x2da2a  ldarg.s  4
0x2da2c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x2da31  ldstr    aPrvcreateentit// "prvCreateEntityKey"
0x2da36  ldarg.s  4
0x2da38  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2da3d  ldarg.s  4
0x2da3f  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2da44  ldarg.s  4
0x2da46  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x2da4b  ldstr    aPrvreadentityk// "prvReadEntityKey"
0x2da50  ldarg.s  4
0x2da52  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2da57  ldarg.s  4
0x2da59  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2da5e  ldarg.s  4
0x2da60  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x2da65  stloc.0
0x2da66  ldarg.s  4
0x2da68  ldc.i4.1
0x2da69  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoAddRootsContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AddRootsOption)
0x2da6e  stloc.1
0x2da6f  ldarg.2
0x2da70  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyDescriptionPropertyBag Microsoft.Crm.Metadata.EntityKeyCreateInfo::get_EntityKeyDescription()
0x2da75  ldarg.1
0x2da76  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyDescription::set_EntityId(valuetype [mscorlib]System.Guid)
0x2da7b  ldarg.2
0x2da7c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyDescriptionPropertyBag Microsoft.Crm.Metadata.EntityKeyCreateInfo::get_EntityKeyDescription()
0x2da81  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x2da86  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyDescription::set_AsyncJobId(valuetype [mscorlib]System.Guid)
0x2da8b  ldarg.0
0x2da8c  ldarg.2
0x2da8d  ldarg.3
0x2da8e  ldarg.s  4
0x2da90  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityKeyService::CreateInternal(class Microsoft.Crm.Metadata.EntityKeyCreateInfo entityKeyInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2da95  stloc.2
0x2da96  ldarg.3
0x2da97  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x2da9c  ldarg.s  4
0x2da9e  ldc.i4.4
0x2da9f  ldloc.2
0x2daa0  ldc.i4.s 0xE
0x2daa2  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::AddDependencyOperation(valuetype [Microsoft.Crm.Core]Microsoft.Crm.DependencyOperationType, valuetype [mscorlib]System.Guid, int32)
0x2daa7  ldloc.0
0x2daa8  brfalse.s loc_2DAB1
0x2daaa  ldarg.s  4
0x2daac  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x2dab1  ldarg.0
0x2dab2  ldarg.1
0x2dab3  ldloc.2
0x2dab4  ldarg.2
0x2dab5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyDescriptionPropertyBag Microsoft.Crm.Metadata.EntityKeyCreateInfo::get_EntityKeyDescription()
0x2daba  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyDescription::get_AsyncJobId()
0x2dabf  ldarg.s  4
0x2dac1  call     instance void Microsoft.Crm.Metadata.EntityKeyService::ExecuteAsyncJobForIndexCreation(valuetype [mscorlib]System.Guid entityId, valuetype [mscorlib]System.Guid entityKeyId, valuetype [mscorlib]System.Guid asyncJobId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2dac6  ldloc.2
0x2dac7  stloc.3
0x2dac8  leave.s  loc_2DB02
0x2daca  ldloc.1
0x2dacb  brfalse.s loc_2DAD3
0x2dacd  ldloc.1
0x2dace  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2dad3  endfinally
0x2dad4  stloc.s  4
0x2dad6  ldloc.s  4
0x2dad8  ldarg.s  4
0x2dada  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2dadf  ldc.i4.s 0x19
0x2dae1  ldstr    aEntitykeyservi// "EntityKeyService.Create caught exceptio"...
0x2dae6  ldc.i4.1
0x2dae7  newarr   [mscorlib]System.Object
0x2daec  dup
0x2daed  ldc.i4.0
0x2daee  ldloc.s  4
0x2daf0  stelem.ref
0x2daf1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2daf6  ldloc.0
0x2daf7  brfalse.s loc_2DB00
0x2daf9  ldarg.s  4
0x2dafb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0x2db00  rethrow
0x2db02  ldloc.3
0x2db03  ret
```
