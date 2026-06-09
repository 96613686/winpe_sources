# Microsoft.Crm.Asynchronous.EventOperation::CreateAsyncSucceededResult

- ea: `0x3150`
- end: `0x3170`
- name: `Microsoft.Crm.Asynchronous.EventOperation::CreateAsyncSucceededResult`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2f90`

## callees

- `0x2d20`
- `0x3150`

## pseudocode

```c

```

## disassembly

```asm
0x3150  ldc.i4.0
0x3151  stloc.0
0x3152  ldarg.0
0x3153  ldarg.1
0x3154  call     instance bool Microsoft.Crm.Asynchronous.EventOperation::GetAsyncAutoDeleteSetting(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context)
0x3159  stloc.0
0x315a  leave.s  loc_315F
0x315c  pop
0x315d  leave.s  loc_315F
0x315f  ldloc.0
0x3160  brtrue.s loc_3168
0x3162  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0x3167  ret
0x3168  ldc.i4.s 0x1E
0x316a  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRemoveEventResult::.ctor(int32)
0x316f  ret
```
