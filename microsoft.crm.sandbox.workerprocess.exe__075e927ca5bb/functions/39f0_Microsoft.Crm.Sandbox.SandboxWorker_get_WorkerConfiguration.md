# Microsoft.Crm.Sandbox.SandboxWorker::get_WorkerConfiguration

- ea: `0x39f0`
- end: `0x3a05`
- name: `Microsoft.Crm.Sandbox.SandboxWorker::get_WorkerConfiguration`
- size: `21`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1a30`
- `0x2340`
- `0x28b0`
- `0x3ea0`
- `0x4720`

## string_xrefs

- `0x39f5`: `_workerConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x39f0  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration Microsoft.Crm.Sandbox.SandboxWorker::_workerConfiguration
0x39f5  ldstr    aWorkerconfigur// "_workerConfiguration"
0x39fa  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x39ff  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration Microsoft.Crm.Sandbox.SandboxWorker::_workerConfiguration
0x3a04  ret
```
