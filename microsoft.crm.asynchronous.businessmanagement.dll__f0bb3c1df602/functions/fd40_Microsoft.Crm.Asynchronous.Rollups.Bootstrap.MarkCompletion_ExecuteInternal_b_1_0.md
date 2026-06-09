# Microsoft.Crm.Asynchronous.Rollups.Bootstrap.MarkCompletion::<ExecuteInternal>b__1_0

- ea: `0xfd40`
- end: `0xfd70`
- name: `Microsoft.Crm.Asynchronous.Rollups.Bootstrap.MarkCompletion::<ExecuteInternal>b__1_0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xbf70`
- `0xbfa0`
- `0x100e0`

## pseudocode

```c

```

## disassembly

```asm
0xfd40  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RollupPropertiesCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RollupPropertiesCache::Instance()
0xfd45  ldarg.0
0xfd46  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapStep::get_Process()
0xfd4b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_RollupPropertiesId()
0xfd50  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContextFactory::get_Current()
0xfd55  ldarg.0
0xfd56  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapStep::get_Process()
0xfd5b  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_AsyncEvent()
0xfd60  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xfd65  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory::GetOrganizationContext(valuetype [mscorlib]System.Guid)
0xfd6a  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupPropertiesData>::RemoveEntry(var<u1>, !!T0)
0xfd6f  ret
```
