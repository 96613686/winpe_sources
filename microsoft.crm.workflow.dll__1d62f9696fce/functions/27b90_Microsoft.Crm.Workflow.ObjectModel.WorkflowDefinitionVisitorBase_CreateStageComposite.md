# Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::CreateStageComposite

- ea: `0x27b90`
- end: `0x27bce`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::CreateStageComposite`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x27b70`
- `0x27bd0`

## callees

- `0x27b90`
- `0x2d0b0`
- `0x2d220`
- `0x2d240`
- `0x2d260`

## pseudocode

```c

```

## disassembly

```asm
0x27b90  newobj   instance void Microsoft.Crm.Workflow.Activities.Composite::.ctor()
0x27b95  stloc.0
0x27b96  ldarg.1
0x27b97  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep::get_StageCategory()
0x27b9c  brtrue.s loc_27BA6
0x27b9e  ldarg.1
0x27b9f  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep::get_StageId()
0x27ba4  brfalse.s loc_27BCC
0x27ba6  ldarg.2
0x27ba7  ldarg.1
0x27ba8  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep::get_StageId()
0x27bad  callvirt instance void Microsoft.Crm.Workflow.Activities.StageComposite::set_StageId(string value)
0x27bb2  ldarg.2
0x27bb3  ldarg.1
0x27bb4  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep::get_StageCategory()
0x27bb9  callvirt instance void Microsoft.Crm.Workflow.Activities.StageComposite::set_StageCategory(string value)
0x27bbe  ldarg.2
0x27bbf  ldarg.1
0x27bc0  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep::get_NextStageId()
0x27bc5  callvirt instance void Microsoft.Crm.Workflow.Activities.StageComposite::set_NextStageId(string value)
0x27bca  ldarg.2
0x27bcb  stloc.0
0x27bcc  ldloc.0
0x27bcd  ret
```
