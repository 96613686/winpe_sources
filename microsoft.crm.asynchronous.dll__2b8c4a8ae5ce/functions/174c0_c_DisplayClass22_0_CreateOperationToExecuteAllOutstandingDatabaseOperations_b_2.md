# <>c__DisplayClass22_0::<CreateOperationToExecuteAllOutstandingDatabaseOperations>b__2

- ea: `0x174c0`
- end: `0x174d9`
- name: `<>c__DisplayClass22_0::<CreateOperationToExecuteAllOutstandingDatabaseOperations>b__2`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x174ce`: `In shutdown, database operation commands should not attempt retry.`

## pseudocode

```c

```

## disassembly

```asm
0x174c0  ldarg.0
0x174c1  ldfld    class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand> <>c__DisplayClass22_0::retryQueue
0x174c6  callvirt instance int32 class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand>::get_Count()
0x174cb  ldc.i4.0
0x174cc  ceq
0x174ce  ldstr    aInShutdownData// "In shutdown, database operation command"...
0x174d3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x174d8  ret
```
