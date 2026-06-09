# Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::GetNewActivityCommand

- ea: `0x1990`
- end: `0x19a4`
- name: `Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::GetNewActivityCommand`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x17c0`

## callees

- `0x19b0`

## pseudocode

```c

```

## disassembly

```asm
0x1990  ldarg.0
0x1991  ldarg.1
0x1992  ldarg.2
0x1993  ldarg.3
0x1994  call     instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::GetNewRecordCommand(int32, string, string)
0x1999  stloc.0
0x199a  ldarg.0
0x199b  ldarg.1
0x199c  ldloc.0
0x199d  call     instance void Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::SetOutlookCommandActionType(int32 activityTypeCode, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition definition)
0x19a2  ldloc.0
0x19a3  ret
```
