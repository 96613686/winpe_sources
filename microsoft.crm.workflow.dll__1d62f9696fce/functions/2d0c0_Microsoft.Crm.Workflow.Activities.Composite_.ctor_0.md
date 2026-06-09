# Microsoft.Crm.Workflow.Activities.Composite::.ctor_0

- ea: `0x2d0c0`
- end: `0x2d0f6`
- name: `Microsoft.Crm.Workflow.Activities.Composite::.ctor_0`
- size: `54`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2cfe0`
- `0x2d0b0`
- `0x2d200`
- `0x2d290`
- `0x2d300`
- `0x2d400`

## pseudocode

```c

```

## disassembly

```asm
0x2d0c0  ldarg.0
0x2d0c1  newobj   instance void class [System.Activities]System.Activities.Variable`1<int32>::.ctor()
0x2d0c6  stfld    class [System.Activities]System.Activities.Variable`1<int32> Microsoft.Crm.Workflow.Activities.Composite::_executionPointer
0x2d0cb  ldarg.0
0x2d0cc  call     instance void [System.Activities]System.Activities.NativeActivity::.ctor()
0x2d0d1  ldarg.0
0x2d0d2  ldarg.0
0x2d0d3  ldftn    instance void Microsoft.Crm.Workflow.Activities.Composite::ChildCompleted(class [System.Activities]System.Activities.NativeActivityContext executionContext, class [System.Activities]System.Activities.ActivityInstance completedInstance)
0x2d0d9  newobj   instance void [System.Activities]System.Activities.CompletionCallback::.ctor(object, native int)
0x2d0de  stfld    class [System.Activities]System.Activities.CompletionCallback Microsoft.Crm.Workflow.Activities.Composite::_onChildComplete
0x2d0e3  ldarg.0
0x2d0e4  ldarg.1
0x2d0e5  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.Composite::_activities
0x2d0ea  ldarg.0
0x2d0eb  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>::.ctor()
0x2d0f0  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.Activities.Composite::_variables
0x2d0f5  ret
```
