# Microsoft.Crm.Asynchronous.DuplicateRuleDataAccess::ExecuteCommand

- ea: `0x1f0f0`
- end: `0x1f102`
- name: `Microsoft.Crm.Asynchronous.DuplicateRuleDataAccess::ExecuteCommand`
- size: `18`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1e830`
- `0x1ec50`
- `0x1eed0`
- `0x1ef70`
- `0x1f020`

## pseudocode

```c

```

## disassembly

```asm
0x1f0f0  ldarg.0
0x1f0f1  ldarg.1
0x1f0f2  ldloca.s 0
0x1f0f4  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1f0fa  ldloc.0
0x1f0fb  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Nullable`1<int32>)
0x1f100  pop
0x1f101  ret
```
