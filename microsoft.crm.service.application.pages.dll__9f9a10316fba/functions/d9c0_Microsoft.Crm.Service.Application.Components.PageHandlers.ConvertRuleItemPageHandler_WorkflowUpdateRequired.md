# Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::WorkflowUpdateRequired

- ea: `0xd9c0`
- end: `0xd9d6`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::WorkflowUpdateRequired`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0xd880`

## callees

- `0xd9c0`

## string_xrefs

- `0xd9c6`: `conditionxml`

## pseudocode

```c

```

## disassembly

```asm
0xd9c0  ldarg.1
0xd9c1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0xd9c6  ldstr    aConditionxml// "conditionxml"
0xd9cb  callvirt instance bool [mscorlib]System.String::Contains(string)
0xd9d0  brfalse.s loc_D9D4
0xd9d2  ldc.i4.1
0xd9d3  ret
0xd9d4  ldc.i4.0
0xd9d5  ret
```
