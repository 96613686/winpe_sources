# Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::HasJobBeenAbortedOrPaused

- ea: `0xaea0`
- end: `0xaeba`
- name: `Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::HasJobBeenAbortedOrPaused`
- size: `26`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xa990`
- `0xac60`
- `0xaec0`

## callees

- `0xaea0`

## pseudocode

```c

```

## disassembly

```asm
0xaea0  ldc.i4.0
0xaea1  stloc.0
0xaea2  ldarg.0
0xaea3  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_asyncEvent
0xaea8  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::QueryForEarlyExitRequest()
0xaead  stloc.1
0xaeae  ldloc.1
0xaeaf  ldc.i4.1
0xaeb0  beq.s    loc_AEB6
0xaeb2  ldloc.1
0xaeb3  ldc.i4.2
0xaeb4  bne.un.s loc_AEB8
0xaeb6  ldc.i4.1
0xaeb7  stloc.0
0xaeb8  ldloc.0
0xaeb9  ret
```
