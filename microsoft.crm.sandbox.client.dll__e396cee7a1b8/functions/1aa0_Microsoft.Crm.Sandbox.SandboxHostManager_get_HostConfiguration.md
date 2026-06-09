# Microsoft.Crm.Sandbox.SandboxHostManager::get_HostConfiguration

- ea: `0x1aa0`
- end: `0x1ab5`
- name: `Microsoft.Crm.Sandbox.SandboxHostManager::get_HostConfiguration`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5fb0`

## string_xrefs

- `0x1aa5`: `_hostConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x1aa0  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHostManager::_hostConfiguration
0x1aa5  ldstr    aHostconfigurat// "_hostConfiguration"
0x1aaa  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1aaf  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHostManager::_hostConfiguration
0x1ab4  ret
```
