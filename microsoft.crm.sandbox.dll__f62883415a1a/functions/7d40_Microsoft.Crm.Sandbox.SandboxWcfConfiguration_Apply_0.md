# Microsoft.Crm.Sandbox.SandboxWcfConfiguration::Apply_0

- ea: `0x7d40`
- end: `0x8045`
- name: `Microsoft.Crm.Sandbox.SandboxWcfConfiguration::Apply_0`
- size: `773`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2800`
- `0x5680`

## callees

- `0x1420`
- `0x14d0`
- `0x7aa0`
- `0x7b50`
- `0x7d40`

## string_xrefs

- `0x7eac`: `SandboxWcfConfiguration.Aplly: Override from registry: TransferMode: {0}`
- `0x7ed5`: `SandboxWcfConfiguration.Aplly: {0} Override from registry failed: TransferMode: {1}`
- `0x7f4e`: `SandboxWcfConfiguration.Aplly: Override from registry: HostNameComparisonMode: {0}`
- `0x7f77`: `SandboxWcfConfiguration.Aplly: {0}Override from registry failed: HostNameComparisonMode: {1}`
- `0x7fcf`: `SandboxWcfConfiguration.Aplly: Override from registry: PortSharingEnabled: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7d40  ldarg.0
0x7d41  ldarg.1
0x7d42  call     instance void Microsoft.Crm.Sandbox.SandboxWcfConfiguration::ApplyBase(class [System.ServiceModel]System.ServiceModel.Channels.Binding binding)
0x7d47  ldarg.0
0x7d48  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7d4d  ldc.i4.s 0x14
0x7d4f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7d54  brfalse.s loc_7D71
0x7d56  ldarg.1
0x7d57  callvirt instance class [System.ServiceModel]System.ServiceModel.OptionalReliableSession [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_ReliableSession()
0x7d5c  ldarg.0
0x7d5d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7d62  ldc.i4.s 0x14
0x7d64  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7d69  ldc.i4.0
0x7d6a  cgt
0x7d6c  callvirt instance void [System.ServiceModel]System.ServiceModel.OptionalReliableSession::set_Enabled(bool)
0x7d71  ldarg.0
0x7d72  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7d77  ldc.i4.s 0x15
0x7d79  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7d7e  brfalse.s loc_7D9E
0x7d80  ldarg.1
0x7d81  callvirt instance class [System.ServiceModel]System.ServiceModel.OptionalReliableSession [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_ReliableSession()
0x7d86  ldarg.0
0x7d87  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7d8c  ldc.i4.s 0x15
0x7d8e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7d93  conv.r8
0x7d94  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x7d99  callvirt instance void [System.ServiceModel]System.ServiceModel.ReliableSession::set_InactivityTimeout(valuetype [mscorlib]System.TimeSpan)
0x7d9e  ldarg.0
0x7d9f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7da4  ldc.i4.s 0x16
0x7da6  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7dab  brfalse.s loc_7DC8
0x7dad  ldarg.1
0x7dae  callvirt instance class [System.ServiceModel]System.ServiceModel.OptionalReliableSession [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_ReliableSession()
0x7db3  ldarg.0
0x7db4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7db9  ldc.i4.s 0x16
0x7dbb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7dc0  ldc.i4.0
0x7dc1  cgt
0x7dc3  callvirt instance void [System.ServiceModel]System.ServiceModel.ReliableSession::set_Ordered(bool)
0x7dc8  ldarg.0
0x7dc9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7dce  ldc.i4.s 9
0x7dd0  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7dd5  brfalse.s loc_7DEB
0x7dd7  ldarg.1
0x7dd8  ldarg.0
0x7dd9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7dde  ldc.i4.s 9
0x7de0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7de5  conv.i8
0x7de6  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_MaxBufferPoolSize(int64)
0x7deb  ldarg.0
0x7dec  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7df1  ldc.i4.s 0xA
0x7df3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7df8  brfalse.s loc_7E0D
0x7dfa  ldarg.1
0x7dfb  ldarg.0
0x7dfc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7e01  ldc.i4.s 0xA
0x7e03  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7e08  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_MaxBufferSize(int32)
0x7e0d  ldarg.0
0x7e0e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7e13  ldc.i4.s 0xB
0x7e15  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7e1a  brfalse.s loc_7E2F
0x7e1c  ldarg.1
0x7e1d  ldarg.0
0x7e1e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7e23  ldc.i4.s 0xB
0x7e25  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7e2a  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_MaxConnections(int32)
0x7e2f  ldarg.0
0x7e30  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7e35  ldc.i4.s 0xC
0x7e37  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7e3c  brfalse.s loc_7E52
0x7e3e  ldarg.1
0x7e3f  ldarg.0
0x7e40  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7e45  ldc.i4.s 0xC
0x7e47  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7e4c  conv.i8
0x7e4d  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_MaxReceivedMessageSize(int64)
0x7e52  ldarg.0
0x7e53  ldfld    string Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_propertyPrefix
0x7e58  ldc.i4.s 0xD
0x7e5a  box      Microsoft.Crm.Sandbox.SandboxWcfProperty
0x7e5f  call     string [mscorlib]System.String::Concat(object, object)
0x7e64  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x7e69  stloc.0
0x7e6a  ldloc.0
0x7e6b  brfalse  loc_7EF4
0x7e70  ldloc.0
0x7e71  isinst   [mscorlib]System.String
0x7e76  brfalse.s loc_7EF4
0x7e78  ldloc.0
0x7e79  castclass [mscorlib]System.String
0x7e7e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7e83  brtrue.s loc_7EF4
0x7e85  ldarg.1
0x7e86  ldtoken  [System.ServiceModel]System.ServiceModel.TransferMode
0x7e8b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e90  ldloc.0
0x7e91  castclass [mscorlib]System.String
0x7e96  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x7e9b  unbox.any [System.ServiceModel]System.ServiceModel.TransferMode
0x7ea0  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_TransferMode(valuetype [System.ServiceModel]System.ServiceModel.TransferMode)
0x7ea5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7eaa  ldc.i4.s 0x26
0x7eac  ldstr    aSandboxwcfconf_0// "SandboxWcfConfiguration.Aplly: Override"...
0x7eb1  ldc.i4.1
0x7eb2  newarr   [mscorlib]System.Object
0x7eb7  dup
0x7eb8  ldc.i4.0
0x7eb9  ldarg.1
0x7eba  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.TransferMode [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_TransferMode()
0x7ebf  box      [System.ServiceModel]System.ServiceModel.TransferMode
0x7ec4  stelem.ref
0x7ec5  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x7eca  leave.s  loc_7EF4
0x7ecc  stloc.2
0x7ecd  ldloc.2
0x7ece  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7ed3  ldc.i4.s 0x21
0x7ed5  ldstr    aSandboxwcfconf_2// "SandboxWcfConfiguration.Aplly: {0} Over"...
0x7eda  ldc.i4.2
0x7edb  newarr   [mscorlib]System.Object
0x7ee0  dup
0x7ee1  ldc.i4.0
0x7ee2  ldarg.0
0x7ee3  ldfld    string Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_propertyPrefix
0x7ee8  stelem.ref
0x7ee9  dup
0x7eea  ldc.i4.1
0x7eeb  ldloc.2
0x7eec  stelem.ref
0x7eed  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x7ef2  leave.s  loc_7EF4
0x7ef4  ldarg.0
0x7ef5  ldfld    string Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_propertyPrefix
0x7efa  ldc.i4.s 0xE
0x7efc  box      Microsoft.Crm.Sandbox.SandboxWcfProperty
0x7f01  call     string [mscorlib]System.String::Concat(object, object)
0x7f06  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x7f0b  stloc.0
0x7f0c  ldloc.0
0x7f0d  brfalse  loc_7F96
0x7f12  ldloc.0
0x7f13  isinst   [mscorlib]System.String
0x7f18  brfalse.s loc_7F96
0x7f1a  ldloc.0
0x7f1b  castclass [mscorlib]System.String
0x7f20  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7f25  brtrue.s loc_7F96
0x7f27  ldarg.1
0x7f28  ldtoken  [System.ServiceModel]System.ServiceModel.HostNameComparisonMode
0x7f2d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7f32  ldloc.0
0x7f33  castclass [mscorlib]System.String
0x7f38  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x7f3d  unbox.any [System.ServiceModel]System.ServiceModel.HostNameComparisonMode
0x7f42  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_HostNameComparisonMode(valuetype [System.ServiceModel]System.ServiceModel.HostNameComparisonMode)
0x7f47  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7f4c  ldc.i4.s 0x26
0x7f4e  ldstr    aSandboxwcfconf_3// "SandboxWcfConfiguration.Aplly: Override"...
0x7f53  ldc.i4.1
0x7f54  newarr   [mscorlib]System.Object
0x7f59  dup
0x7f5a  ldc.i4.0
0x7f5b  ldarg.1
0x7f5c  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.HostNameComparisonMode [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_HostNameComparisonMode()
0x7f61  box      [System.ServiceModel]System.ServiceModel.HostNameComparisonMode
0x7f66  stelem.ref
0x7f67  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x7f6c  leave.s  loc_7F96
0x7f6e  stloc.3
0x7f6f  ldloc.3
0x7f70  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7f75  ldc.i4.s 0x21
0x7f77  ldstr    aSandboxwcfconf_4// "SandboxWcfConfiguration.Aplly: {0}Overr"...
0x7f7c  ldc.i4.2
0x7f7d  newarr   [mscorlib]System.Object
0x7f82  dup
0x7f83  ldc.i4.0
0x7f84  ldarg.0
0x7f85  ldfld    string Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_propertyPrefix
0x7f8a  stelem.ref
0x7f8b  dup
0x7f8c  ldc.i4.1
0x7f8d  ldloc.3
0x7f8e  stelem.ref
0x7f8f  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x7f94  leave.s  loc_7F96
0x7f96  ldarg.0
0x7f97  ldfld    string Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_propertyPrefix
0x7f9c  ldc.i4.s 0xF
0x7f9e  box      Microsoft.Crm.Sandbox.SandboxWcfProperty
0x7fa3  call     string [mscorlib]System.String::Concat(object, object)
0x7fa8  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x7fad  stloc.0
0x7fae  ldloc.0
0x7faf  brfalse.s loc_7FEF
0x7fb1  ldloc.0
0x7fb2  isinst   [mscorlib]System.Int32
0x7fb7  brfalse.s loc_7FEF
0x7fb9  ldarg.1
0x7fba  ldloc.0
0x7fbb  unbox.any [mscorlib]System.Int32
0x7fc0  ldc.i4.0
0x7fc1  cgt
0x7fc3  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_PortSharingEnabled(bool)
0x7fc8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7fcd  ldc.i4.s 0x26
0x7fcf  ldstr    aSandboxwcfconf_5// "SandboxWcfConfiguration.Aplly: Override"...
0x7fd4  ldc.i4.1
0x7fd5  newarr   [mscorlib]System.Object
0x7fda  dup
0x7fdb  ldc.i4.0
0x7fdc  ldarg.1
0x7fdd  callvirt instance bool [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_PortSharingEnabled()
0x7fe2  box      [mscorlib]System.Boolean
0x7fe7  stelem.ref
0x7fe8  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x7fed  br.s     loc_8006
0x7fef  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInSandboxWorkerContext()
0x7ff4  brfalse.s loc_7FFF
0x7ff6  ldarg.1
0x7ff7  ldc.i4.0
0x7ff8  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_PortSharingEnabled(bool)
0x7ffd  br.s     loc_8006
0x7fff  ldarg.1
0x8000  ldc.i4.1
0x8001  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_PortSharingEnabled(bool)
0x8006  ldarg.0
0x8007  call     instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas Microsoft.Crm.Sandbox.SandboxWcfConfiguration::GetQuotas()
0x800c  stloc.1
0x800d  ldloc.1
0x800e  ldnull
0x800f  cgt.un
0x8011  ldstr    aQuotasIsNull// "quotas is null"
0x8016  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x801b  ldarg.1
0x801c  ldloc.1
0x801d  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_ReaderQuotas(class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas)
0x8022  ldarg.0
0x8023  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x8028  ldc.i4.s 0x10
0x802a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x802f  brfalse.s loc_8044
0x8031  ldarg.1
0x8032  ldarg.0
0x8033  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x8038  ldc.i4.s 0x10
0x803a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x803f  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_ListenBacklog(int32)
0x8044  ret
```
