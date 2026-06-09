# Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::IsConvertRuleStateCodeActive

- ea: `0xd740`
- end: `0xd770`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::IsConvertRuleStateCodeActive`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xd240`
- `0xd770`

## callees

- `0xd740`

## pseudocode

```c

```

## disassembly

```asm
0xd740  ldarg.1
0xd741  brfalse.s loc_D76E
0xd743  ldarg.1
0xd744  ldstr    aStatecode// "statecode"
0xd749  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd74e  brfalse.s loc_D76E
0xd750  ldarg.1
0xd751  ldstr    aStatecode// "statecode"
0xd756  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd75b  callvirt instance string [mscorlib]System.Object::ToString()
0xd760  ldstr    aActive// "Active"
0xd765  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd76a  brfalse.s loc_D76E
0xd76c  ldc.i4.1
0xd76d  ret
0xd76e  ldc.i4.0
0xd76f  ret
```
