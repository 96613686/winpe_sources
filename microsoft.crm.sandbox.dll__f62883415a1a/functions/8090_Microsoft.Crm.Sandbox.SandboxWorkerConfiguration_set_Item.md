# Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::set_Item

- ea: `0x8090`
- end: `0x8099`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::set_Item`
- size: `9`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x80d0`

## callees

- `0x3a50`

## pseudocode

```c

```

## disassembly

```asm
0x8090  ldarg.0
0x8091  ldarg.1
0x8092  ldarg.2
0x8093  call     instance void Microsoft.Crm.Sandbox.SandboxConfiguration::set_Item(int32 key, int32 value)
0x8098  ret
```
