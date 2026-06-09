# Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State

- ea: `0xc70`
- end: `0xc77`
- name: `Microsoft.Crm.Sandbox.OrganizationWorkerBucket::get_State`
- size: `7`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xe70`
- `0xf60`
- `0x1190`
- `0x12b0`
- `0x15b0`
- `0x17b0`
- `0x1870`
- `0x1cb0`
- `0x1f10`
- `0x2040`

## pseudocode

```c

```

## disassembly

```asm
0xc70  ldarg.0
0xc71  ldfld    valuetype Microsoft.Crm.Sandbox.BucketState Microsoft.Crm.Sandbox.OrganizationWorkerBucket::_state
0xc76  ret
```
