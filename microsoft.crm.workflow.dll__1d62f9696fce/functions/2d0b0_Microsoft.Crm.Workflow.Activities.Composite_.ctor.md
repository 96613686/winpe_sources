# Microsoft.Crm.Workflow.Activities.Composite::.ctor

- ea: `0x2d0b0`
- end: `0x2d0bc`
- name: `Microsoft.Crm.Workflow.Activities.Composite::.ctor`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x23430`
- `0x23770`
- `0x26320`
- `0x27b90`
- `0x29210`
- `0x2a950`

## callees

- `0x2d0c0`

## pseudocode

```c

```

## disassembly

```asm
0x2d0b0  ldarg.0
0x2d0b1  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::.ctor()
0x2d0b6  call     instance void Microsoft.Crm.Workflow.Activities.Composite::.ctor(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities)
0x2d0bb  ret
```
