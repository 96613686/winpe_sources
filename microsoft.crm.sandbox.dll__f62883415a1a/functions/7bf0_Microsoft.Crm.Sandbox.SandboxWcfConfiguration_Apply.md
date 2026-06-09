# Microsoft.Crm.Sandbox.SandboxWcfConfiguration::Apply

- ea: `0x7bf0`
- end: `0x7d34`
- name: `Microsoft.Crm.Sandbox.SandboxWcfConfiguration::Apply`
- size: `324`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1420`
- `0x14d0`
- `0x7aa0`
- `0x7b50`
- `0x7bf0`

## string_xrefs

- `0x7cd8`: `SandboxWcfConfiguration.Aplly: Override from registry: TransferMode: {0}`
- `0x7d01`: `SandboxWcfConfiguration.Aplly: Override from registry failed: TransferMode: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7bf0  ldarg.0
0x7bf1  ldarg.1
0x7bf2  call     instance void Microsoft.Crm.Sandbox.SandboxWcfConfiguration::ApplyBase(class [System.ServiceModel]System.ServiceModel.Channels.Binding binding)
0x7bf7  ldarg.0
0x7bf8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7bfd  ldc.i4.s 9
0x7bff  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7c04  brfalse.s loc_7C1A
0x7c06  ldarg.1
0x7c07  ldarg.0
0x7c08  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7c0d  ldc.i4.s 9
0x7c0f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7c14  conv.i8
0x7c15  callvirt instance void [System.ServiceModel]System.ServiceModel.NetNamedPipeBinding::set_MaxBufferPoolSize(int64)
0x7c1a  ldarg.0
0x7c1b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7c20  ldc.i4.s 0xA
0x7c22  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7c27  brfalse.s loc_7C3C
0x7c29  ldarg.1
0x7c2a  ldarg.0
0x7c2b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7c30  ldc.i4.s 0xA
0x7c32  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7c37  callvirt instance void [System.ServiceModel]System.ServiceModel.NetNamedPipeBinding::set_MaxBufferSize(int32)
0x7c3c  ldarg.0
0x7c3d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7c42  ldc.i4.s 0xB
0x7c44  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7c49  brfalse.s loc_7C5E
0x7c4b  ldarg.1
0x7c4c  ldarg.0
0x7c4d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7c52  ldc.i4.s 0xB
0x7c54  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7c59  callvirt instance void [System.ServiceModel]System.ServiceModel.NetNamedPipeBinding::set_MaxConnections(int32)
0x7c5e  ldarg.0
0x7c5f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7c64  ldc.i4.s 0xC
0x7c66  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7c6b  brfalse.s loc_7C81
0x7c6d  ldarg.1
0x7c6e  ldarg.0
0x7c6f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7c74  ldc.i4.s 0xC
0x7c76  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7c7b  conv.i8
0x7c7c  callvirt instance void [System.ServiceModel]System.ServiceModel.NetNamedPipeBinding::set_MaxReceivedMessageSize(int64)
0x7c81  ldarg.0
0x7c82  ldfld    string Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_propertyPrefix
0x7c87  ldc.i4.s 0xD
0x7c89  box      Microsoft.Crm.Sandbox.SandboxWcfProperty
0x7c8e  call     string [mscorlib]System.String::Concat(object, object)
0x7c93  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x7c98  stloc.0
0x7c99  ldloc.0
0x7c9a  brfalse.s loc_7D17
0x7c9c  ldloc.0
0x7c9d  isinst   [mscorlib]System.String
0x7ca2  brfalse.s loc_7D17
0x7ca4  ldloc.0
0x7ca5  castclass [mscorlib]System.String
0x7caa  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7caf  brtrue.s loc_7D17
0x7cb1  ldarg.1
0x7cb2  ldtoken  [System.ServiceModel]System.ServiceModel.TransferMode
0x7cb7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7cbc  ldloc.0
0x7cbd  castclass [mscorlib]System.String
0x7cc2  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x7cc7  unbox.any [System.ServiceModel]System.ServiceModel.TransferMode
0x7ccc  callvirt instance void [System.ServiceModel]System.ServiceModel.NetNamedPipeBinding::set_TransferMode(valuetype [System.ServiceModel]System.ServiceModel.TransferMode)
0x7cd1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7cd6  ldc.i4.s 0x26
0x7cd8  ldstr    aSandboxwcfconf_0// "SandboxWcfConfiguration.Aplly: Override"...
0x7cdd  ldc.i4.1
0x7cde  newarr   [mscorlib]System.Object
0x7ce3  dup
0x7ce4  ldc.i4.0
0x7ce5  ldarg.1
0x7ce6  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.TransferMode [System.ServiceModel]System.ServiceModel.NetNamedPipeBinding::get_TransferMode()
0x7ceb  box      [System.ServiceModel]System.ServiceModel.TransferMode
0x7cf0  stelem.ref
0x7cf1  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x7cf6  leave.s  loc_7D17
0x7cf8  stloc.2
0x7cf9  ldloc.2
0x7cfa  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7cff  ldc.i4.s 0x21
0x7d01  ldstr    aSandboxwcfconf_1// "SandboxWcfConfiguration.Aplly: Override"...
0x7d06  ldc.i4.1
0x7d07  newarr   [mscorlib]System.Object
0x7d0c  dup
0x7d0d  ldc.i4.0
0x7d0e  ldloc.2
0x7d0f  stelem.ref
0x7d10  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x7d15  leave.s  loc_7D17
0x7d17  ldarg.0
0x7d18  call     instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas Microsoft.Crm.Sandbox.SandboxWcfConfiguration::GetQuotas()
0x7d1d  stloc.1
0x7d1e  ldloc.1
0x7d1f  ldnull
0x7d20  cgt.un
0x7d22  ldstr    aQuotasIsNull// "quotas is null"
0x7d27  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x7d2c  ldarg.1
0x7d2d  ldloc.1
0x7d2e  callvirt instance void [System.ServiceModel]System.ServiceModel.NetNamedPipeBinding::set_ReaderQuotas(class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas)
0x7d33  ret
```
