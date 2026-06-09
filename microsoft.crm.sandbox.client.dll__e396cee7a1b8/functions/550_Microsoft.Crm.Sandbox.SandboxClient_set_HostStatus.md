# Microsoft.Crm.Sandbox.SandboxClient::set_HostStatus

- ea: `0x550`
- end: `0x558`
- name: `Microsoft.Crm.Sandbox.SandboxClient::set_HostStatus`
- size: `8`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1470`
- `0x23d0`
- `0x83d0`

## pseudocode

```c

```

## disassembly

```asm
0x550  ldarg.0
0x551  ldarg.1
0x552  stfld    valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxClient::<HostStatus>k__BackingField
0x557  ret
```
