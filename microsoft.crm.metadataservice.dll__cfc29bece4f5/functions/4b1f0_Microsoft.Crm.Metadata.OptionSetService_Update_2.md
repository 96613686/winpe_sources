# Microsoft.Crm.Metadata.OptionSetService::Update_2

- ea: `0x4b1f0`
- end: `0x4b2c1`
- name: `Microsoft.Crm.Metadata.OptionSetService::Update_2`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x4b1c0`

## callees

- `0x4b1f0`
- `0x4b2d0`
- `0x4bc00`
- `0x5a810`

## string_xrefs

- `0x4b22d`: `prvWriteOptionSet`
- `0x4b2a0`: `OptionSetService.Update caught exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4b1f0  ldarg.1
0x4b1f1  ldstr    aOptionsetid_0// "optionSetId"
0x4b1f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x4b1fb  ldarg.2
0x4b1fc  ldstr    aOptionsetinfo// "optionSetInfo"
0x4b201  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4b206  ldarg.s  4
0x4b208  ldstr    aMetadatahelper// "metadataHelper"
0x4b20d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4b212  ldarg.s  5
0x4b214  ldstr    aContext// "context"
0x4b219  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4b21e  ldarg.s  5
0x4b220  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4b225  pop
0x4b226  ldarg.s  5
0x4b228  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x4b22d  ldstr    aPrvwriteoption// "prvWriteOptionSet"
0x4b232  ldarg.s  5
0x4b234  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4b239  ldarg.s  5
0x4b23b  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4b240  ldarg.s  5
0x4b242  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x4b247  stloc.0
0x4b248  ldc.i4.1
0x4b249  ldarg.1
0x4b24a  ldarg.s  5
0x4b24c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4b251  call     void Microsoft.Crm.Metadata.OptionSetService::ValidateIsGlobalAgainstExistingOptionSet(bool expectedIsGlobal, valuetype [mscorlib]System.Guid existingOptionSetId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4b256  ldarg.s  5
0x4b258  ldc.i4.1
0x4b259  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoAddRootsContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AddRootsOption)
0x4b25e  stloc.1
0x4b25f  ldarg.1
0x4b260  ldarg.2
0x4b261  ldarg.3
0x4b262  ldarg.s  4
0x4b264  ldarg.s  5
0x4b266  call     void Microsoft.Crm.Metadata.OptionSetService::UpdateInternal(valuetype [mscorlib]System.Guid optionSetId, class Microsoft.Crm.Metadata.OptionSetUpdateInfo optionSetInfo, bool mergeLabels, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4b26b  ldarg.s  4
0x4b26d  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x4b272  ldarg.s  5
0x4b274  ldc.i4.4
0x4b275  ldarg.1
0x4b276  ldc.i4.s 9
0x4b278  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::AddDependencyOperation(valuetype [Microsoft.Crm.Core]Microsoft.Crm.DependencyOperationType, valuetype [mscorlib]System.Guid, int32)
0x4b27d  ldloc.0
0x4b27e  brfalse.s loc_4B287
0x4b280  ldarg.s  5
0x4b282  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x4b287  leave.s  loc_4B293
0x4b289  ldloc.1
0x4b28a  brfalse.s loc_4B292
0x4b28c  ldloc.1
0x4b28d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4b292  endfinally
0x4b293  leave.s  loc_4B2C0
0x4b295  stloc.2
0x4b296  ldloc.2
0x4b297  ldarg.s  5
0x4b299  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x4b29e  ldc.i4.s 0x19
0x4b2a0  ldstr    aOptionsetservi_0// "OptionSetService.Update caught exceptio"...
0x4b2a5  ldc.i4.1
0x4b2a6  newarr   [mscorlib]System.Object
0x4b2ab  dup
0x4b2ac  ldc.i4.0
0x4b2ad  ldloc.2
0x4b2ae  stelem.ref
0x4b2af  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4b2b4  ldloc.0
0x4b2b5  brfalse.s loc_4B2BE
0x4b2b7  ldarg.s  5
0x4b2b9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0x4b2be  rethrow
0x4b2c0  ret
```
