# Microsoft.Crm.Asynchronous.OptInFcbUpdate::InternalExecute

- ea: `0xd560`
- end: `0xd57b`
- name: `Microsoft.Crm.Asynchronous.OptInFcbUpdate::InternalExecute`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0xd560`
- `0xd580`

## pseudocode

```c

```

## disassembly

```asm
0xd560  ldarg.0
0xd561  ldarg.1
0xd562  call     instance void Microsoft.Crm.Asynchronous.OptInFcbUpdate::DoPatchImport(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent)
0xd567  ldc.i4.s 0x1E
0xd569  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRemoveEventResult::.ctor(int32)
0xd56e  stloc.0
0xd56f  leave.s  loc_D579
0xd571  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0xd576  stloc.0
0xd577  leave.s  loc_D579
0xd579  ldloc.0
0xd57a  ret
```
