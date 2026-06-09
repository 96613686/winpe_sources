# Microsoft.Crm.Sandbox.SandboxHostManager::get_ClientConfiguration

- ea: `0x1a80`
- end: `0x1a95`
- name: `Microsoft.Crm.Sandbox.SandboxHostManager::get_ClientConfiguration`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x22b0`
- `0x5be0`

## string_xrefs

- `0x1a85`: `_clientConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x1a80  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientConfiguration Microsoft.Crm.Sandbox.SandboxHostManager::_clientConfiguration
0x1a85  ldstr    aClientconfigur// "_clientConfiguration"
0x1a8a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1a8f  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientConfiguration Microsoft.Crm.Sandbox.SandboxHostManager::_clientConfiguration
0x1a94  ret
```
