# Microsoft.Crm.Sandbox.SandboxHostManager::CreatePluginFromRequestAndClient

- ea: `0x17f0`
- end: `0x1900`
- name: `Microsoft.Crm.Sandbox.SandboxHostManager::CreatePluginFromRequestAndClient`
- size: `272`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1220`
- `0x8980`

## callees

- `0x17f0`
- `0x1fd0`
- `0x22b0`
- `0x3410`
- `0x3510`
- `0x3530`
- `0x3550`
- `0x3570`
- `0x3590`
- `0x35a0`

## pseudocode

```c

```

## disassembly

```asm
0x17f0  ldarg.1
0x17f1  ldc.i4.0
0x17f2  ldc.i4.0
0x17f3  call     int32 Microsoft.Crm.Sandbox.SandboxCodeUnit::get_OperationTimeoutInSeconds()
0x17f8  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x17fd  callvirt instance void class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxHost>::SetOperationTimeout(valuetype [mscorlib]System.TimeSpan)
0x1802  ldarg.0
0x1803  callvirt instance valuetype [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.CodeUnitType [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_CodeUnit()
0x1808  brtrue.s loc_1881
0x180a  ldarg.0
0x180b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_PluginTypeId()
0x1810  ldarg.0
0x1811  callvirt instance string [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_TypeName()
0x1816  ldarg.0
0x1817  callvirt instance string [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_Configuration()
0x181c  ldarg.0
0x181d  callvirt instance string [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_SecureConfiguration()
0x1822  ldarg.0
0x1823  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_PluginAssemblyId()
0x1828  newobj   instance void Microsoft.Crm.Sandbox.SandboxPluginAssemblyData::.ctor()
0x182d  dup
0x182e  ldarg.0
0x182f  callvirt instance bool [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_IsFullySigned()
0x1834  callvirt instance void Microsoft.Crm.Sandbox.SandboxPluginAssemblyData::set_IsFullySigned(bool value)
0x1839  dup
0x183a  ldarg.0
0x183b  callvirt instance string [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_AssemblyName()
0x1840  callvirt instance void Microsoft.Crm.Sandbox.SandboxPluginAssemblyData::set_PluginAssemblyName(string value)
0x1845  dup
0x1846  ldarg.0
0x1847  callvirt instance string [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_AssemblyShortName()
0x184c  callvirt instance void Microsoft.Crm.Sandbox.SandboxPluginAssemblyData::set_PluginAssemblySimpleName(string value)
0x1851  dup
0x1852  ldarg.0
0x1853  callvirt instance unsigned int8[] [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_PublicToken()
0x1858  call     string [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.ByteEncoder::Decode(unsigned int8[])
0x185d  callvirt instance void Microsoft.Crm.Sandbox.SandboxPluginAssemblyData::set_PublicKeyToken(string value)
0x1862  dup
0x1863  ldarg.0
0x1864  callvirt instance int32 [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_AssemblyHashCode()
0x1869  callvirt instance void Microsoft.Crm.Sandbox.SandboxPluginAssemblyData::set_PluginAssemblyHashCode(int32 value)
0x186e  ldarg.1
0x186f  ldarg.0
0x1870  callvirt instance int32 [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_AttemptNumber()
0x1875  ldarg.0
0x1876  callvirt instance int32 [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_MaxAttempts()
0x187b  newobj   instance void Microsoft.Crm.Sandbox.SandboxPlugin::.ctor(valuetype [mscorlib]System.Guid pluginTypeId, string pluginTypeName, string pluginConfiguration, string pluginSecureConfig, valuetype [mscorlib]System.Guid pluginAssemblyId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData assemblyData, class Microsoft.Crm.Sandbox.SandboxClient sandboxClient, [opt] int32 attemptNumber, [opt] int32 maxAttempts)
0x1880  ret
0x1881  ldarg.0
0x1882  callvirt instance valuetype [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.CodeUnitType [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_CodeUnit()
0x1887  ldc.i4.1
0x1888  bne.un.s loc_18F5
0x188a  ldarg.0
0x188b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_PluginTypeId()
0x1890  ldarg.0
0x1891  callvirt instance string [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_TypeName()
0x1896  ldarg.0
0x1897  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_PluginAssemblyId()
0x189c  newobj   instance void Microsoft.Crm.Sandbox.SandboxPluginAssemblyData::.ctor()
0x18a1  dup
0x18a2  ldarg.0
0x18a3  callvirt instance bool [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_IsFullySigned()
0x18a8  callvirt instance void Microsoft.Crm.Sandbox.SandboxPluginAssemblyData::set_IsFullySigned(bool value)
0x18ad  dup
0x18ae  ldarg.0
0x18af  callvirt instance string [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_AssemblyName()
0x18b4  callvirt instance void Microsoft.Crm.Sandbox.SandboxPluginAssemblyData::set_PluginAssemblyName(string value)
0x18b9  dup
0x18ba  ldarg.0
0x18bb  callvirt instance string [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_AssemblyShortName()
0x18c0  callvirt instance void Microsoft.Crm.Sandbox.SandboxPluginAssemblyData::set_PluginAssemblySimpleName(string value)
0x18c5  dup
0x18c6  ldarg.0
0x18c7  callvirt instance unsigned int8[] [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_PublicToken()
0x18cc  call     string [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.ByteEncoder::Decode(unsigned int8[])
0x18d1  callvirt instance void Microsoft.Crm.Sandbox.SandboxPluginAssemblyData::set_PublicKeyToken(string value)
0x18d6  dup
0x18d7  ldarg.0
0x18d8  callvirt instance int32 [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_AssemblyHashCode()
0x18dd  callvirt instance void Microsoft.Crm.Sandbox.SandboxPluginAssemblyData::set_PluginAssemblyHashCode(int32 value)
0x18e2  ldarg.1
0x18e3  ldarg.0
0x18e4  callvirt instance int32 [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_AttemptNumber()
0x18e9  ldarg.0
0x18ea  callvirt instance int32 [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest::get_MaxAttempts()
0x18ef  newobj   instance void Microsoft.Crm.Sandbox.SandboxCustomActivity::.ctor(valuetype [mscorlib]System.Guid pluginTypeId, string pluginTypeName, valuetype [mscorlib]System.Guid pluginAssemblyId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData assemblyData, class Microsoft.Crm.Sandbox.SandboxClient sandboxClient, [opt] int32 attemptNumber, [opt] int32 maxAttempts)
0x18f4  ret
0x18f5  ldstr    aUnexpectedCode// "Unexpected CodeUnit type"
0x18fa  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x18ff  throw
```
