# Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::get_EntityTypeCode

- ea: `0xd200`
- end: `0xd20c`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::get_EntityTypeCode`
- size: `12`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xd320`
- `0xd6b0`

## callees

- `0xc460`

## pseudocode

```c

```

## disassembly

```asm
0xd200  ldarg.0
0xd201  ldfld    class Microsoft.Crm.Asynchronous.RollupsAsyncContext Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::_rollupsAsyncContext
0xd206  callvirt instance int32 Microsoft.Crm.Asynchronous.RollupsAsyncContext::get_EntityTypeCode()
0xd20b  ret
```
