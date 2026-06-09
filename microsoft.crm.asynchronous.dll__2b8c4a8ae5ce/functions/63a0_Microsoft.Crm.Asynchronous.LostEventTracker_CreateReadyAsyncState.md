# Microsoft.Crm.Asynchronous.LostEventTracker::CreateReadyAsyncState

- ea: `0x63a0`
- end: `0x63bb`
- name: `Microsoft.Crm.Asynchronous.LostEventTracker::CreateReadyAsyncState`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x62e0`

## callees

- `0x2f20`
- `0x2f40`
- `0x2f60`
- `0x30d0`

## pseudocode

```c

```

## disassembly

```asm
0x63a0  newobj   instance void Microsoft.Crm.Asynchronous.AsyncEventState::.ctor()
0x63a5  dup
0x63a6  ldarg.1
0x63a7  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventState::set_EventId(valuetype [mscorlib]System.Guid value)
0x63ac  dup
0x63ad  ldc.i4.0
0x63ae  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventState::set_NewState(int32 value)
0x63b3  dup
0x63b4  ldc.i4.0
0x63b5  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventState::set_NewStatus(int32 value)
0x63ba  ret
```
