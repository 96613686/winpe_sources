# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetAssemblyMetadataAndValidateIsFullySigned

- ea: `0x80e0`
- end: `0x814b`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetAssemblyMetadataAndValidateIsFullySigned`
- size: `107`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x7d10`
- `0x7ed0`
- `0x9510`
- `0x9570`

## callees

- `0xc0`
- `0x2f0`
- `0x80e0`

## string_xrefs

- `0x80ed`: `pluginAssemblyData`
- `0x813b`: `pluginAssemblyData`
- `0x80ff`: `PluginSecureStoreServiceProvider.GetAssemblyMetadataAndValidateIsFullySigned - PluginAssemblySimpleName: {0} PublicKeyToken: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x80e0  call     class Microsoft.Crm.Sandbox.SandboxCallManager Microsoft.Crm.Sandbox.SandboxCallManager::get_Instance()
0x80e5  ldarg.1
0x80e6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData Microsoft.Crm.Sandbox.SandboxCallManager::GetCallbackAssemblyData(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo sandboxCallInfo)
0x80eb  stloc.0
0x80ec  ldloc.0
0x80ed  ldstr    aPluginassembly_1// "pluginAssemblyData"
0x80f2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x80f7  ldarg.2
0x80f8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x80fd  ldc.i4.s 0x1F
0x80ff  ldstr    aPluginsecurest_25// "PluginSecureStoreServiceProvider.GetAss"...
0x8104  ldc.i4.2
0x8105  newarr   [mscorlib]System.Object
0x810a  dup
0x810b  ldc.i4.0
0x810c  ldloc.0
0x810d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData::get_PluginAssemblySimpleName()
0x8112  stelem.ref
0x8113  dup
0x8114  ldc.i4.1
0x8115  ldloc.0
0x8116  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData::get_PublicKeyToken()
0x811b  stelem.ref
0x811c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8121  ldloc.0
0x8122  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData::get_IsFullySigned()
0x8127  brfalse.s loc_812B
0x8129  ldloc.0
0x812a  ret
0x812b  ldstr    aAssembly0NotFu// "Assembly {0} not fully signed"
0x8130  ldloc.0
0x8131  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData::get_PluginAssemblyName()
0x8136  call     string [mscorlib]System.String::Format(string, object)
0x813b  ldstr    aPluginassembly_1// "pluginAssemblyData"
0x8140  ldc.i4   0x8009100F
0x8145  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string, int32)
0x814a  throw
```
