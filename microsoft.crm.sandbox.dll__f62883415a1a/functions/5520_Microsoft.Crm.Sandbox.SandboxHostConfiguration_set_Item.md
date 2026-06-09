# Microsoft.Crm.Sandbox.SandboxHostConfiguration::set_Item

- ea: `0x5520`
- end: `0x5529`
- name: `Microsoft.Crm.Sandbox.SandboxHostConfiguration::set_Item`
- size: `9`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5580`

## callees

- `0x3a50`

## pseudocode

```c

```

## disassembly

```asm
0x5520  ldarg.0
0x5521  ldarg.1
0x5522  ldarg.2
0x5523  call     instance void Microsoft.Crm.Sandbox.SandboxConfiguration::set_Item(int32 key, int32 value)
0x5528  ret
```
