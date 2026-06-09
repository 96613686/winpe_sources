# Microsoft.Crm.Asynchronous.EventOperation::GetPluginAssembly

- ea: `0x2d80`
- end: `0x2dad`
- name: `Microsoft.Crm.Asynchronous.EventOperation::GetPluginAssembly`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x2db0`
- `0x2fc0`

## callees

- `0x2c60`
- `0x2d80`

## pseudocode

```c

```

## disassembly

```asm
0x2d80  ldarg.1
0x2d81  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_OwningExtension()
0x2d86  brtrue.s loc_2D8A
0x2d88  ldnull
0x2d89  ret
0x2d8a  ldarg.0
0x2d8b  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_AsyncService()
0x2d90  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeCache [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService::get_PluginTypeCache()
0x2d95  ldarg.0
0x2d96  ldarg.1
0x2d97  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EventOperation::GetPluginTypeId(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context)
0x2d9c  ldarg.1
0x2d9d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_OrganizationId()
0x2da2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x2da7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeCache::LookupAssemblyEntry(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2dac  ret
```
