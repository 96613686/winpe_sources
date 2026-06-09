# Microsoft.Crm.Metadata.OptionSetService::Create_2

- ea: `0x4afb0`
- end: `0x4b07f`
- name: `Microsoft.Crm.Metadata.OptionSetService::Create_2`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x4af90`

## callees

- `0x4ab20`
- `0x4afb0`
- `0x4b080`
- `0x4bc30`
- `0x5a810`

## string_xrefs

- `0x4aff5`: `prvReadOptionSet`
- `0x4afde`: `prvCreateOptionSet`
- `0x4b05d`: `OptionSetService.Create caught exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4afb0  ldarg.1
0x4afb1  ldstr    aOptionsetinfo// "optionSetInfo"
0x4afb6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4afbb  ldarg.2
0x4afbc  ldstr    aMetadatahelper// "metadataHelper"
0x4afc1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4afc6  ldarg.3
0x4afc7  ldstr    aContext// "context"
0x4afcc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4afd1  ldarg.3
0x4afd2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4afd7  pop
0x4afd8  ldarg.3
0x4afd9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x4afde  ldstr    aPrvcreateoptio// "prvCreateOptionSet"
0x4afe3  ldarg.3
0x4afe4  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4afe9  ldarg.3
0x4afea  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4afef  ldarg.3
0x4aff0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x4aff5  ldstr    aPrvreadoptions// "prvReadOptionSet"
0x4affa  ldarg.3
0x4affb  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4b000  ldarg.3
0x4b001  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4b006  ldarg.3
0x4b007  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x4b00c  stloc.0
0x4b00d  ldc.i4.1
0x4b00e  ldarg.1
0x4b00f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x4b014  call     void Microsoft.Crm.Metadata.OptionSetService::ValidateIsGlobalAgainstExistingOptionSet(bool expectedIsGlobal, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag existingOptionSetDescription)
0x4b019  ldarg.3
0x4b01a  ldc.i4.1
0x4b01b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoAddRootsContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AddRootsOption)
0x4b020  stloc.1
0x4b021  ldarg.1
0x4b022  ldarg.2
0x4b023  ldarg.3
0x4b024  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.OptionSetService::CreateInternal(class Microsoft.Crm.Metadata.OptionSetCreateInfo optionSetInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4b029  stloc.2
0x4b02a  ldarg.2
0x4b02b  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x4b030  ldarg.3
0x4b031  ldc.i4.4
0x4b032  ldloc.2
0x4b033  ldc.i4.s 9
0x4b035  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::AddDependencyOperation(valuetype [Microsoft.Crm.Core]Microsoft.Crm.DependencyOperationType, valuetype [mscorlib]System.Guid, int32)
0x4b03a  ldloc.0
0x4b03b  brfalse.s loc_4B043
0x4b03d  ldarg.3
0x4b03e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x4b043  ldloc.2
0x4b044  stloc.3
0x4b045  leave.s  loc_4B07D
0x4b047  ldloc.1
0x4b048  brfalse.s loc_4B050
0x4b04a  ldloc.1
0x4b04b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4b050  endfinally
0x4b051  stloc.s  4
0x4b053  ldloc.s  4
0x4b055  ldarg.3
0x4b056  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x4b05b  ldc.i4.s 0x19
0x4b05d  ldstr    aOptionsetservi// "OptionSetService.Create caught exceptio"...
0x4b062  ldc.i4.1
0x4b063  newarr   [mscorlib]System.Object
0x4b068  dup
0x4b069  ldc.i4.0
0x4b06a  ldloc.s  4
0x4b06c  stelem.ref
0x4b06d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4b072  ldloc.0
0x4b073  brfalse.s loc_4B07B
0x4b075  ldarg.3
0x4b076  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0x4b07b  rethrow
0x4b07d  ldloc.3
0x4b07e  ret
```
