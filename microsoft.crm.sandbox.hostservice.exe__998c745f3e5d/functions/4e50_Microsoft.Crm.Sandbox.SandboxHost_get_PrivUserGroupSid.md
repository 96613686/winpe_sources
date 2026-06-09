# Microsoft.Crm.Sandbox.SandboxHost::get_PrivUserGroupSid

- ea: `0x4e50`
- end: `0x4e56`
- name: `Microsoft.Crm.Sandbox.SandboxHost::get_PrivUserGroupSid`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x48a0`
- `0x49d0`
- `0x88d0`

## pseudocode

```c

```

## disassembly

```asm
0x4e50  ldsfld   unsigned int8[] Microsoft.Crm.Sandbox.SandboxHost::<PrivUserGroupSid>k__BackingField
0x4e55  ret
```
