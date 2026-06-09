# Microsoft.Crm.Sandbox.SandboxClientConfiguration::set_Item

- ea: `0xd70`
- end: `0xd79`
- name: `Microsoft.Crm.Sandbox.SandboxClientConfiguration::set_Item`
- size: `9`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xdb0`

## callees

- `0x3a50`

## pseudocode

```c

```

## disassembly

```asm
0xd70  ldarg.0
0xd71  ldarg.1
0xd72  ldarg.2
0xd73  call     instance void Microsoft.Crm.Sandbox.SandboxConfiguration::set_Item(int32 key, int32 value)
0xd78  ret
```
