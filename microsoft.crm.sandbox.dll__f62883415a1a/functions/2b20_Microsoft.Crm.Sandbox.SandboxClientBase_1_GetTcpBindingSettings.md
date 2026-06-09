# Microsoft.Crm.Sandbox.SandboxClientBase`1::GetTcpBindingSettings

- ea: `0x2b20`
- end: `0x2bfa`
- name: `Microsoft.Crm.Sandbox.SandboxClientBase`1::GetTcpBindingSettings`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x2b9a`: `HostNameComparisonMode`
- `0x2bca`: `ReaderQuotas`

## pseudocode

```c

```

## disassembly

```asm
0x2b20  ldarg.2
0x2b21  ldarg.3
0x2b22  ldstr    aMaxbufferpools// "MaxBufferPoolSize"
0x2b27  ldarg.1
0x2b28  callvirt instance int64 [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_MaxBufferPoolSize()
0x2b2d  box      [mscorlib]System.Int64
0x2b32  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x2b37  pop
0x2b38  ldarg.2
0x2b39  ldarg.3
0x2b3a  ldstr    aMaxbuffersize// "MaxBufferSize"
0x2b3f  ldarg.1
0x2b40  callvirt instance int32 [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_MaxBufferSize()
0x2b45  box      [mscorlib]System.Int32
0x2b4a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x2b4f  pop
0x2b50  ldarg.2
0x2b51  ldarg.3
0x2b52  ldstr    aMaxconnections// "MaxConnections"
0x2b57  ldarg.1
0x2b58  callvirt instance int32 [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_MaxConnections()
0x2b5d  box      [mscorlib]System.Int32
0x2b62  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x2b67  pop
0x2b68  ldarg.2
0x2b69  ldarg.3
0x2b6a  ldstr    aMaxreceivedmes// "MaxReceivedMessageSize"
0x2b6f  ldarg.1
0x2b70  callvirt instance int64 [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_MaxReceivedMessageSize()
0x2b75  box      [mscorlib]System.Int64
0x2b7a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x2b7f  pop
0x2b80  ldarg.2
0x2b81  ldarg.3
0x2b82  ldstr    aTransfermode// "TransferMode"
0x2b87  ldarg.1
0x2b88  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.TransferMode [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_TransferMode()
0x2b8d  box      [System.ServiceModel]System.ServiceModel.TransferMode
0x2b92  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x2b97  pop
0x2b98  ldarg.2
0x2b99  ldarg.3
0x2b9a  ldstr    aHostnamecompar// "HostNameComparisonMode"
0x2b9f  ldarg.1
0x2ba0  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.HostNameComparisonMode [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_HostNameComparisonMode()
0x2ba5  box      [System.ServiceModel]System.ServiceModel.HostNameComparisonMode
0x2baa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x2baf  pop
0x2bb0  ldarg.2
0x2bb1  ldarg.3
0x2bb2  ldstr    aPortsharingena// "PortSharingEnabled"
0x2bb7  ldarg.1
0x2bb8  callvirt instance bool [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_PortSharingEnabled()
0x2bbd  box      [mscorlib]System.Boolean
0x2bc2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x2bc7  pop
0x2bc8  ldarg.2
0x2bc9  ldarg.3
0x2bca  ldstr    aReaderquotas// "ReaderQuotas"
0x2bcf  ldarg.1
0x2bd0  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_ReaderQuotas()
0x2bd5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x2bda  pop
0x2bdb  ldarg.2
0x2bdc  ldarg.3
0x2bdd  ldstr    aListenbacklog// "ListenBacklog"
0x2be2  ldarg.1
0x2be3  callvirt instance int32 [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_ListenBacklog()
0x2be8  box      [mscorlib]System.Int32
0x2bed  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x2bf2  pop
0x2bf3  ldarg.2
0x2bf4  callvirt instance string [mscorlib]System.Object::ToString()
0x2bf9  ret
```
