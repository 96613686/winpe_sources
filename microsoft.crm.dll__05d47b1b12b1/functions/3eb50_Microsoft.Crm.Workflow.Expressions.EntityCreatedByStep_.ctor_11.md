# Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor_11

- ea: `0x3eb50`
- end: `0x3eb83`
- name: `Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor_11`
- size: `51`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2cb30`
- `0x3e9b0`
- `0x3eb00`
- `0x3eb40`

## callees

- `0x3e740`
- `0x3e790`

## string_xrefs

- `0x3eb78`: `EntityCreatedByStep:#Microsoft.Crm.Workflow.Expressions`

## pseudocode

```c

```

## disassembly

```asm
0x3eb50  ldarg.0
0x3eb51  ldarg.1
0x3eb52  ldarg.s  5
0x3eb54  call     instance void Microsoft.Crm.Workflow.Expressions.EntityBase::.ctor(class Microsoft.Crm.Workflow.ObjectModel.WorkflowStep sourceWorkflow, string sourceParameterName)
0x3eb59  ldarg.0
0x3eb5a  ldarg.2
0x3eb5b  stfld    class Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::step
0x3eb60  ldarg.0
0x3eb61  ldarg.3
0x3eb62  call     instance void Microsoft.Crm.Workflow.Expressions.EntityBase::set_EntityName(string value)
0x3eb67  ldarg.0
0x3eb68  ldarg.s  4
0x3eb6a  stfld    string Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::entityIdentifier
0x3eb6f  ldarg.0
0x3eb70  ldarg.s  6
0x3eb72  stfld    bool Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::isCustomOperationArgument
0x3eb77  ldarg.0
0x3eb78  ldstr    aEntitycreatedb// "EntityCreatedByStep:#Microsoft.Crm.Work"...
0x3eb7d  stfld    string Microsoft.Crm.Workflow.Expressions.EntityBase::__class
0x3eb82  ret
```
