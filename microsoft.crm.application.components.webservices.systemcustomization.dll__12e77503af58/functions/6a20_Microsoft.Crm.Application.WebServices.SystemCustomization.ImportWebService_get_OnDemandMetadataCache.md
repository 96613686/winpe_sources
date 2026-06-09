# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::get_OnDemandMetadataCache

- ea: `0x6a20`
- end: `0x6a7d`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::get_OnDemandMetadataCache`
- size: `93`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5e50`
- `0x5ed0`
- `0x6240`
- `0x6380`
- `0x6430`
- `0x6480`

## callees

- `0x6a20`

## pseudocode

```c

```

## disassembly

```asm
0x6a20  ldarg.0
0x6a21  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::onDemandCache
0x6a26  brtrue.s loc_6A76
0x6a28  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x6a2d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x6a32  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x6a37  pop
0x6a38  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.MetadataCacheUtil::IsCacheForCustomizationUIEnabled()
0x6a3d  brfalse.s loc_6A5B
0x6a3f  ldarg.0
0x6a40  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x6a45  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x6a4a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x6a4f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6a54  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::onDemandCache
0x6a59  br.s     loc_6A76
0x6a5b  ldarg.0
0x6a5c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x6a61  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x6a66  ldc.i4.1
0x6a67  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Metadata.OnDemandMetadataCacheDataProvider::.ctor(valuetype [mscorlib]System.Guid, bool)
0x6a6c  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ServerDynamicMetadataCache::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataCacheDataProvider)
0x6a71  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::onDemandCache
0x6a76  ldarg.0
0x6a77  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::onDemandCache
0x6a7c  ret
```
