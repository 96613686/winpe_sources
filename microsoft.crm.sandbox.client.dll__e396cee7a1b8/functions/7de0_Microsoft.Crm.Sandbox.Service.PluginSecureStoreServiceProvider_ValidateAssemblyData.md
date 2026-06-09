# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::ValidateAssemblyData

- ea: `0x7de0`
- end: `0x7e88`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::ValidateAssemblyData`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x7d10`

## callees

- `0x72f0`
- `0x7de0`

## string_xrefs

- `0x7df1`: `assemblyData.PluginAssemblyName`
- `0x7e01`: `assemblyData.PublicKeyToken`
- `0x7e27`: `PluginSecureStoreServiceProvider.ValidateAssemblyData - Assembly is valid. CallInfo {0}`
- `0x7e45`: `PluginSecureStoreServiceProvider.ValidateAssemblyData - Assembly {0} is invalid. CallInfo {1}`

## pseudocode

```c

```

## disassembly

```asm
0x7de0  ldarg.1
0x7de1  ldstr    aAssemblydata// "assemblyData"
0x7de6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7deb  ldarg.1
0x7dec  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData::get_PluginAssemblySimpleName()
0x7df1  ldstr    aAssemblydataPl// "assemblyData.PluginAssemblyName"
0x7df6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7dfb  ldarg.1
0x7dfc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData::get_PublicKeyToken()
0x7e01  ldstr    aAssemblydataPu// "assemblyData.PublicKeyToken"
0x7e06  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7e0b  ldarg.0
0x7e0c  ldfld    class Microsoft.Crm.Sandbox.Service.ITPSService Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::_tpsService
0x7e11  ldarg.1
0x7e12  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData::get_PluginAssemblySimpleName()
0x7e17  ldarg.1
0x7e18  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData::get_PublicKeyToken()
0x7e1d  callvirt instance bool Microsoft.Crm.Sandbox.Service.ITPSService::IsValidAssembly(string shortName, string publicKeyToken)
0x7e22  brfalse.s loc_7E41
0x7e24  ldarg.3
0x7e25  ldc.i4.s 0x1F
0x7e27  ldstr    aPluginsecurest_18// "PluginSecureStoreServiceProvider.Valida"...
0x7e2c  ldc.i4.1
0x7e2d  newarr   [mscorlib]System.Object
0x7e32  dup
0x7e33  ldc.i4.0
0x7e34  ldarg.2
0x7e35  box      [mscorlib]System.Guid
0x7e3a  stelem.ref
0x7e3b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7e40  ret
0x7e41  ldnull
0x7e42  ldarg.3
0x7e43  ldc.i4.s 0x1F
0x7e45  ldstr    aPluginsecurest_19// "PluginSecureStoreServiceProvider.Valida"...
0x7e4a  ldc.i4.2
0x7e4b  newarr   [mscorlib]System.Object
0x7e50  dup
0x7e51  ldc.i4.0
0x7e52  ldarg.1
0x7e53  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData::get_PluginAssemblySimpleName()
0x7e58  stelem.ref
0x7e59  dup
0x7e5a  ldc.i4.1
0x7e5b  ldarg.2
0x7e5c  box      [mscorlib]System.Guid
0x7e61  stelem.ref
0x7e62  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7e67  ldstr    aAssembly0NotFo// "Assembly {0} not found in TPS. CallInfo"...
0x7e6c  ldarg.1
0x7e6d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData::get_PluginAssemblySimpleName()
0x7e72  ldarg.2
0x7e73  box      [mscorlib]System.Guid
0x7e78  call     string [mscorlib]System.String::Format(string, object, object)
0x7e7d  ldc.i4   0x80091007
0x7e82  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.CrmExceptions.CrmTPSException::.ctor(string, int32)
0x7e87  throw
```
