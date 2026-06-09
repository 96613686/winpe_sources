# Microsoft.Crm.Workflow.ObjectModel.BusinessProcessFlowVisitor::VisitControlStep

- ea: `0x3bf50`
- end: `0x3bf9d`
- name: `Microsoft.Crm.Workflow.ObjectModel.BusinessProcessFlowVisitor::VisitControlStep`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x28fa0`
- `0x347e0`
- `0x34840`
- `0x3bd10`
- `0x3bf50`

## string_xrefs

- `0x3bf83`: `_LinkControl`

## pseudocode

```c

```

## disassembly

```asm
0x3bf50  ldarg.0
0x3bf51  ldfld    string Microsoft.Crm.Workflow.ObjectModel.BusinessProcessFlowVisitor::currentVisitingEntityName
0x3bf56  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3bf5b  ldc.i4.0
0x3bf5c  ceq
0x3bf5e  ldstr    aVisitorShouldA// "Visitor should always visit EntityStep "...
0x3bf63  call     void Microsoft.Crm.Workflow.Utils.ExceptionUtility::Assert(bool condition, string message)
0x3bf68  ldarg.1
0x3bf69  callvirt instance string Microsoft.Crm.Workflow.ObjectModel.ControlStep::get_DataFieldName()
0x3bf6e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3bf73  brtrue.s loc_3BF8F
0x3bf75  ldarg.1
0x3bf76  callvirt instance bool Microsoft.Crm.Workflow.ObjectModel.ControlStep::get_IsSystemControl()
0x3bf7b  brfalse.s loc_3BF90
0x3bf7d  ldarg.1
0x3bf7e  callvirt instance string Microsoft.Crm.Workflow.ObjectModel.ControlStep::get_DataFieldName()
0x3bf83  ldstr    aLinkcontrol// "_LinkControl"
0x3bf88  callvirt instance bool [mscorlib]System.String::Contains(string)
0x3bf8d  brfalse.s loc_3BF90
0x3bf8f  ret
0x3bf90  ldarg.0
0x3bf91  ldarg.1
0x3bf92  callvirt instance string Microsoft.Crm.Workflow.ObjectModel.ControlStep::get_DataFieldName()
0x3bf97  call     instance void Microsoft.Crm.Workflow.ObjectModel.BusinessProcessFlowVisitor::AddControlForCurrentEntity(string controlName)
0x3bf9c  ret
```
