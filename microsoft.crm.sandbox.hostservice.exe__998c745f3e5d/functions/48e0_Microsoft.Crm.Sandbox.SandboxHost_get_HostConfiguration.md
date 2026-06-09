# Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration

- ea: `0x48e0`
- end: `0x48f5`
- name: `Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration`
- size: `21`
- prototype: ``
- caller_count: `19`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140`
- `0x1060`
- `0x2820`
- `0x3210`
- `0x3880`
- `0x56e0`
- `0x5c60`
- `0x7150`
- `0x74f0`
- `0x8040`
- `0x8230`
- `0x8cc0`
- `0x9640`
- `0xa0f0`
- `0xa350`
- `0xa810`
- `0xc450`
- `0xc8a0`
- `0xc9f0`

## string_xrefs

- `0x48e5`: `_hostConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x48e0  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::_hostConfiguration
0x48e5  ldstr    aHostconfigurat// "_hostConfiguration"
0x48ea  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x48ef  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::_hostConfiguration
0x48f4  ret
```
