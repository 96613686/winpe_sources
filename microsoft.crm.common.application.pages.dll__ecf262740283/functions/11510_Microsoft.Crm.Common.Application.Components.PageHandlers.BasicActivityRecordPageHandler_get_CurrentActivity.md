# Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity

- ea: `0x11510`
- end: `0x1151c`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity`
- size: `12`
- prototype: ``
- caller_count: `13`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10db0`
- `0x110c0`
- `0x11340`
- `0x11550`
- `0x117e0`
- `0x11820`
- `0x11920`
- `0x11b00`
- `0x11b90`
- `0x11c00`
- `0x11c80`
- `0x11cd0`
- `0x11df0`

## pseudocode

```c

```

## disassembly

```asm
0x11510  ldarg.0
0x11511  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x11516  isinst   [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase
0x1151b  ret
```
