# Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer

- ea: `0x30980`
- end: `0x309ca`
- name: `Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer`
- size: `74`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x32d50`
- `0x32e20`
- `0x354d0`
- `0x384a0`

## callees

- `0x28f20`
- `0x28fa0`
- `0x2dd00`
- `0x308c0`

## string_xrefs

- `0x309ac`: `Parent step is not a Composite Step`

## pseudocode

```c

```

## disassembly

```asm
0x30980  ldarg.2
0x30981  ldstr    aNewstep// "newStep"
0x30986  call     void Microsoft.Crm.Workflow.Utils.ExceptionUtility::ThrowIfNull(object expression, string message)
0x3098b  ldarg.0
0x3098c  callvirt instance class Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x30991  ldnull
0x30992  cgt.un
0x30994  ldstr    aParentStepIsNu// "Parent step is null"
0x30999  call     void Microsoft.Crm.Workflow.Utils.ExceptionUtility::Assert(bool condition, string message)
0x3099e  ldarg.0
0x3099f  callvirt instance class Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x309a4  isinst   Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x309a9  ldnull
0x309aa  cgt.un
0x309ac  ldstr    aParentStepIsNo// "Parent step is not a Composite Step"
0x309b1  call     void Microsoft.Crm.Workflow.Utils.ExceptionUtility::Assert(bool condition, string message)
0x309b6  ldarg.0
0x309b7  callvirt instance class Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x309bc  castclass Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x309c1  ldarg.0
0x309c2  ldarg.1
0x309c3  ldarg.2
0x309c4  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::Insert(class Microsoft.Crm.Workflow.ObjectModel.StepBase peer, valuetype Microsoft.Crm.Workflow.ObjectModel.InsertDirection direction, class Microsoft.Crm.Workflow.ObjectModel.StepBase newStep)
0x309c9  ret
```
