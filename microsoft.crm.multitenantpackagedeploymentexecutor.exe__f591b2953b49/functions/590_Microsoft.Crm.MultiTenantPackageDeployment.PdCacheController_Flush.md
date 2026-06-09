# Microsoft.Crm.MultiTenantPackageDeployment.PdCacheController::Flush

- ea: `0x590`
- end: `0x5ab`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PdCacheController::Flush`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x590`
- `0x1de0`

## pseudocode

```c

```

## disassembly

```asm
0x590  ldnull
0x591  stloc.0
0x592  ldsfld   class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCacheStorage [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCacheStorage::StaticInstance
0x597  ldarg.1
0x598  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCacheStorage::FlushNoNotification(valuetype [mscorlib]System.Guid)
0x59d  leave.s  loc_5AA
0x59f  stloc.0
0x5a0  leave.s  loc_5AA
0x5a2  ldarg.1
0x5a3  ldloc.0
0x5a4  call     void Microsoft.Crm.MultiTenantPackageDeployment.SetupTelemetry::PDCacheFlush(valuetype [mscorlib]System.Guid orgId, class [mscorlib]System.Exception ex)
0x5a9  endfinally
0x5aa  ret
```
