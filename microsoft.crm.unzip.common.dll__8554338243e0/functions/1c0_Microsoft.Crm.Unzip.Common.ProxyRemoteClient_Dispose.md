# Microsoft.Crm.Unzip.Common.ProxyRemoteClient::Dispose

- ea: `0x1c0`
- end: `0x1eb`
- name: `Microsoft.Crm.Unzip.Common.ProxyRemoteClient::Dispose`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1c0`

## pseudocode

```c

```

## disassembly

```asm
0x1c0  ldarg.0
0x1c1  ldfld    class Microsoft.Crm.Unzip.Common.IUnzipProxy Microsoft.Crm.Unzip.Common.ProxyRemoteClient::_proxy
0x1c6  brfalse.s loc_1E3
0x1c8  ldarg.0
0x1c9  ldfld    class Microsoft.Crm.Unzip.Common.IUnzipProxy Microsoft.Crm.Unzip.Common.ProxyRemoteClient::_proxy
0x1ce  castclass [System.ServiceModel]System.ServiceModel.Channels.IChannel
0x1d3  stloc.0
0x1d4  ldloc.0
0x1d5  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.CommunicationState [System.ServiceModel]System.ServiceModel.ICommunicationObject::get_State()
0x1da  ldc.i4.5
0x1db  beq.s    loc_1E3
0x1dd  ldloc.0
0x1de  callvirt instance void [System.ServiceModel]System.ServiceModel.ICommunicationObject::Close()
0x1e3  ldarg.0
0x1e4  ldnull
0x1e5  stfld    class Microsoft.Crm.Unzip.Common.IUnzipProxy Microsoft.Crm.Unzip.Common.ProxyRemoteClient::_proxy
0x1ea  ret
```
