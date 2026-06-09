# Microsoft.Crm.Sandbox.SandboxCallManager::NewCallTracker

- ea: `0xd0`
- end: `0xf5`
- name: `Microsoft.Crm.Sandbox.SandboxCallManager::NewCallTracker`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x8dc0`

## callees

- `0x110`

## string_xrefs

- `0xe1`: `pluginAssemblyId`

## pseudocode

```c

```

## disassembly

```asm
0xd0  ldarg.1
0xd1  ldstr    aContext// "context"
0xd6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xdb  ldarg.3
0xdc  box      [mscorlib]System.Guid
0xe1  ldstr    aPluginassembly// "pluginAssemblyId"
0xe6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xeb  ldarg.0
0xec  ldarg.1
0xed  ldarg.2
0xee  ldarg.3
0xef  call     instance class Microsoft.Crm.Sandbox.SandboxCallTracker Microsoft.Crm.Sandbox.SandboxCallManager::NewCallTrackerInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData assemblyData, valuetype [mscorlib]System.Guid pluginAssemblyId)
0xf4  ret
```
