# UpdateStateAndStatusCommand::.ctor

- ea: `0x16530`
- end: `0x16571`
- name: `UpdateStateAndStatusCommand::.ctor`
- size: `65`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x37e0`
- `0x3810`

## callees

- `0x4580`
- `0x49c0`

## string_xrefs

- `0x16537`: `queueDataAccess`

## pseudocode

```c

```

## disassembly

```asm
0x16530  ldarg.0
0x16531  call     instance void Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::.ctor()
0x16536  ldarg.1
0x16537  ldstr    aQueuedataacces// "queueDataAccess"
0x1653c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x16541  ldarg.2
0x16542  ldstr    aNeweventstate// "newEventState"
0x16547  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1654c  ldarg.0
0x1654d  ldarg.1
0x1654e  stfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess UpdateStateAndStatusCommand::_queueDataAccess
0x16553  ldarg.0
0x16554  ldarg.2
0x16555  stfld    class Microsoft.Crm.Asynchronous.AsyncEventState UpdateStateAndStatusCommand::_newEventState
0x1655a  ldarg.0
0x1655b  ldarg.3
0x1655c  stfld    class Microsoft.Crm.Asynchronous.AsyncEvent UpdateStateAndStatusCommand::_asyncEvent
0x16561  ldarg.0
0x16562  ldarg.s  4
0x16564  stfld    bool UpdateStateAndStatusCommand::_checkForCompletedJobs
0x16569  ldarg.0
0x1656a  ldc.i4.1
0x1656b  call     instance void Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::set_RetryWithBackOff(bool value)
0x16570  ret
```
