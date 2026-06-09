# Microsoft.Crm.Sandbox.SandboxHostManager::RetrieveReadyPlugin

- ea: `0x1220`
- end: `0x122f`
- name: `Microsoft.Crm.Sandbox.SandboxHostManager::RetrieveReadyPlugin`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1230`
- `0x17f0`

## pseudocode

```c

```

## disassembly

```asm
0x1220  ldarg.0
0x1221  call     class Microsoft.Crm.Sandbox.SandboxClient Microsoft.Crm.Sandbox.SandboxHostManager::RetrieveReadyClient(bool useDrawBridgeIsolation)
0x1226  stloc.0
0x1227  ldarg.1
0x1228  ldloc.0
0x1229  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin Microsoft.Crm.Sandbox.SandboxHostManager::CreatePluginFromRequestAndClient(class [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest request, class Microsoft.Crm.Sandbox.SandboxClient pingClient)
0x122e  ret
```
