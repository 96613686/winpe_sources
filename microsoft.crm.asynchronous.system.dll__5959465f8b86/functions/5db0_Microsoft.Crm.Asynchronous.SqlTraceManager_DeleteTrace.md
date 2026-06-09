# Microsoft.Crm.Asynchronous.SqlTraceManager::DeleteTrace

- ea: `0x5db0`
- end: `0x5dd5`
- name: `Microsoft.Crm.Asynchronous.SqlTraceManager::DeleteTrace`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1f60`

## callees

- `0x5db0`
- `0x5de0`

## pseudocode

```c

```

## disassembly

```asm
0x5db0  ldarg.0
0x5db1  ldfld    string Microsoft.Crm.Asynchronous.SqlTraceManager::_fullTracePath
0x5db6  newobj   instance void [System]System.Uri::.ctor(string)
0x5dbb  callvirt instance bool [System]System.Uri::get_IsUnc()
0x5dc0  brfalse.s loc_5DCE
0x5dc2  ldarg.0
0x5dc3  ldfld    string Microsoft.Crm.Asynchronous.SqlTraceManager::_fullTracePath
0x5dc8  call     void [mscorlib]System.IO.File::Delete(string)
0x5dcd  ret
0x5dce  ldarg.0
0x5dcf  call     instance void Microsoft.Crm.Asynchronous.SqlTraceManager::DeleteSqlTrace()
0x5dd4  ret
```
