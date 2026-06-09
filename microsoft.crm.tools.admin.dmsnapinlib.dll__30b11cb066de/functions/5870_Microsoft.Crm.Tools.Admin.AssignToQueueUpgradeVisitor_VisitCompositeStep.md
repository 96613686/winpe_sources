# Microsoft.Crm.Tools.Admin.AssignToQueueUpgradeVisitor::VisitCompositeStep

- ea: `0x5870`
- end: `0x5899`
- name: `Microsoft.Crm.Tools.Admin.AssignToQueueUpgradeVisitor::VisitCompositeStep`
- size: `41`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5800`
- `0x58a0`
- `0x58b0`
- `0x58c0`
- `0x58d0`
- `0x58e0`
- `0x58f0`
- `0x5900`
- `0x5910`
- `0x5940`

## callees

- `0x5870`

## pseudocode

```c

```

## disassembly

```asm
0x5870  ldc.i4.0
0x5871  stloc.0
0x5872  br.s     loc_588A
0x5874  ldarg.1
0x5875  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x587a  ldloc.0
0x587b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::get_Item(int32)
0x5880  ldarg.0
0x5881  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::Apply(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepVisitorBase)
0x5886  ldloc.0
0x5887  ldc.i4.1
0x5888  add
0x5889  stloc.0
0x588a  ldloc.0
0x588b  ldarg.1
0x588c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x5891  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::get_Count()
0x5896  blt.s    loc_5874
0x5898  ret
```
