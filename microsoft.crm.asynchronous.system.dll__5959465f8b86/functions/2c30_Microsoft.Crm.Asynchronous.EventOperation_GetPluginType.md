# Microsoft.Crm.Asynchronous.EventOperation::GetPluginType

- ea: `0x2c30`
- end: `0x2c5d`
- name: `Microsoft.Crm.Asynchronous.EventOperation::GetPluginType`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x2db0`
- `0x2fc0`

## callees

- `0x2c30`
- `0x2c60`

## pseudocode

```c

```

## disassembly

```asm
0x2c30  ldarg.1
0x2c31  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_OwningExtension()
0x2c36  brtrue.s loc_2C3A
0x2c38  ldnull
0x2c39  ret
0x2c3a  ldarg.0
0x2c3b  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_AsyncService()
0x2c40  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeCache [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService::get_PluginTypeCache()
0x2c45  ldarg.0
0x2c46  ldarg.1
0x2c47  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EventOperation::GetPluginTypeId(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context)
0x2c4c  ldarg.1
0x2c4d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_OrganizationId()
0x2c52  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x2c57  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData>::LookupEntry(void, var<u1>)
0x2c5c  ret
```
