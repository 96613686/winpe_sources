# Microsoft.Crm.Sdk.RequestBuilderProxyCacheLoader::LoadCacheData

- ea: `0x5ca0`
- end: `0x5cd0`
- name: `Microsoft.Crm.Sdk.RequestBuilderProxyCacheLoader::LoadCacheData`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x56f0`
- `0x5ca0`

## pseudocode

```c

```

## disassembly

```asm
0x5ca0  ldarg.2
0x5ca1  ldc.i4.0
0x5ca2  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x5ca7  stloc.0
0x5ca8  ldarg.0
0x5ca9  ldfld    class Microsoft.Crm.Sdk.RequestBuilderCache Microsoft.Crm.Sdk.RequestBuilderProxyCacheLoader::_builderCache
0x5cae  ldarg.0
0x5caf  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SdkMessageFilterCache Microsoft.Crm.Sdk.RequestBuilderProxyCacheLoader::_filterCache
0x5cb4  ldarg.2
0x5cb5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5cba  ldarg.1
0x5cbb  ldarg.2
0x5cbc  newobj   instance void Microsoft.Crm.Sdk.RequestBuilderProxy::.ctor(class Microsoft.Crm.Sdk.RequestBuilderCache builderCache, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SdkMessageFilterCache filterCache, valuetype [mscorlib]System.Guid organizationId, class Microsoft.Crm.Sdk.RequestBuilderKey key, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5cc1  stloc.1
0x5cc2  leave.s  loc_5CCE
0x5cc4  ldloc.0
0x5cc5  brfalse.s loc_5CCD
0x5cc7  ldloc.0
0x5cc8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ccd  endfinally
0x5cce  ldloc.1
0x5ccf  ret
```
