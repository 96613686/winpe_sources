# Microsoft.Crm.Sandbox.SandboxHost::get_HostWorkerConfiguration

- ea: `0x4900`
- end: `0x4915`
- name: `Microsoft.Crm.Sandbox.SandboxHost::get_HostWorkerConfiguration`
- size: `21`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa350`
- `0xa810`
- `0xb250`

## string_xrefs

- `0x4905`: `_workerConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x4900  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration Microsoft.Crm.Sandbox.SandboxHost::_workerConfiguration
0x4905  ldstr    aWorkerconfigur// "_workerConfiguration"
0x490a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x490f  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration Microsoft.Crm.Sandbox.SandboxHost::_workerConfiguration
0x4914  ret
```
