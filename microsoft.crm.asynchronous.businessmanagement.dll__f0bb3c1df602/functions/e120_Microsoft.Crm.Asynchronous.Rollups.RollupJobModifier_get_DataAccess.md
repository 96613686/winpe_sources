# Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier::get_DataAccess

- ea: `0xe120`
- end: `0xe12c`
- name: `Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier::get_DataAccess`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xe130`
- `0x17000`
- `0x17040`
- `0x17080`
- `0x170c0`
- `0x17100`

## callees

- `0xc4c0`

## pseudocode

```c

```

## disassembly

```asm
0xe120  ldarg.0
0xe121  ldfld    class Microsoft.Crm.Asynchronous.RollupsAsyncContext Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier::_rollupsAsyncContext
0xe126  callvirt instance class Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess Microsoft.Crm.Asynchronous.RollupsAsyncContext::get_RollupsDataAccess()
0xe12b  ret
```
