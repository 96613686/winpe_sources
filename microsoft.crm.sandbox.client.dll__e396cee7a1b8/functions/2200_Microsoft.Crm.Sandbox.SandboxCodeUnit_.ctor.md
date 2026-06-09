# Microsoft.Crm.Sandbox.SandboxCodeUnit::.ctor

- ea: `0x2200`
- end: `0x22a2`
- name: `Microsoft.Crm.Sandbox.SandboxCodeUnit::.ctor`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1fd0`
- `0x3410`

## string_xrefs

- `0x2207`: `pluginTypeName`

## pseudocode

```c

```

## disassembly

```asm
0x2200  ldarg.0
0x2201  call     instance void [mscorlib]System.Object::.ctor()
0x2206  ldarg.2
0x2207  ldstr    aPlugintypename// "pluginTypeName"
0x220c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x2211  ldarg.s  6
0x2213  ldstr    aAssemblydata// "assemblyData"
0x2218  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x221d  ldarg.2
0x221e  ldc.i4.1
0x221f  newarr   [mscorlib]System.Char
0x2224  dup
0x2225  ldc.i4.0
0x2226  ldc.i4.s 0x2C
0x2228  stelem.i2
0x2229  ldc.i4.2
0x222a  callvirt instance string[] [mscorlib]System.String::Split(char[], int32)
0x222f  stloc.0
0x2230  ldloc.0
0x2231  ldlen
0x2232  conv.i4
0x2233  ldc.i4.2
0x2234  ceq
0x2236  ldstr    aAssemblyQualif// "Assembly qualified type name should be "...
0x223b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2240  ldarg.0
0x2241  ldloc.0
0x2242  ldc.i4.0
0x2243  ldelem.ref
0x2244  stfld    string Microsoft.Crm.Sandbox.SandboxCodeUnit::_typeName
0x2249  ldarg.0
0x224a  ldarg.s  6
0x224c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData::get_PluginAssemblyName()
0x2251  stfld    string Microsoft.Crm.Sandbox.SandboxCodeUnit::_assemblyName
0x2256  ldarg.0
0x2257  ldarg.3
0x2258  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxCodeUnit::_pluginAssemblyId
0x225d  ldarg.0
0x225e  ldarg.1
0x225f  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxCodeUnit::_pluginTypeId
0x2264  ldarg.0
0x2265  ldarg.s  6
0x2267  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData::get_PluginAssemblyHashCode()
0x226c  stfld    int32 Microsoft.Crm.Sandbox.SandboxCodeUnit::_pluginAssemblyHashCode
0x2271  ldarg.0
0x2272  ldarg.s  4
0x2274  stfld    string Microsoft.Crm.Sandbox.SandboxCodeUnit::_pluginConfiguration
0x2279  ldarg.0
0x227a  ldarg.s  5
0x227c  stfld    string Microsoft.Crm.Sandbox.SandboxCodeUnit::_pluginSecureConfig
0x2281  ldarg.0
0x2282  ldarg.s  6
0x2284  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData Microsoft.Crm.Sandbox.SandboxCodeUnit::_assemblyData
0x2289  ldarg.0
0x228a  ldarg.s  8
0x228c  stfld    int32 Microsoft.Crm.Sandbox.SandboxCodeUnit::_attemptNumber
0x2291  ldarg.0
0x2292  ldarg.s  9
0x2294  stfld    int32 Microsoft.Crm.Sandbox.SandboxCodeUnit::_maxAttempts
0x2299  ldarg.0
0x229a  ldarg.s  7
0x229c  stfld    class Microsoft.Crm.Sandbox.SandboxClient Microsoft.Crm.Sandbox.SandboxCodeUnit::_sandboxClient
0x22a1  ret
```
