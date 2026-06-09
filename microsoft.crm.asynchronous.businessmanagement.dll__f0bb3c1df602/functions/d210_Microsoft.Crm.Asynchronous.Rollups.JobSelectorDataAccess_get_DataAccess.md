# Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::get_DataAccess

- ea: `0xd210`
- end: `0xd21c`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::get_DataAccess`
- size: `12`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xd280`
- `0xd2e0`
- `0xd320`
- `0xd3b0`
- `0xd410`
- `0xd490`
- `0xd510`
- `0xd6b0`

## callees

- `0xc4c0`

## pseudocode

```c

```

## disassembly

```asm
0xd210  ldarg.0
0xd211  ldfld    class Microsoft.Crm.Asynchronous.RollupsAsyncContext Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::_rollupsAsyncContext
0xd216  callvirt instance class Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess Microsoft.Crm.Asynchronous.RollupsAsyncContext::get_RollupsDataAccess()
0xd21b  ret
```
