# Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::get_SlaEntity

- ea: `0xc670`
- end: `0xc691`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::get_SlaEntity`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xc610`
- `0xcb80`

## callees

- `0xc670`
- `0xcca0`
- `0xcd70`

## pseudocode

```c

```

## disassembly

```asm
0xc670  ldarg.0
0xc671  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::_slaEntity
0xc676  brtrue.s loc_C68A
0xc678  ldarg.0
0xc679  ldarg.0
0xc67a  ldarg.0
0xc67b  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::get__slaId()
0xc680  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::RetrieveSLAEntity(valuetype [mscorlib]System.Guid _slaId)
0xc685  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::_slaEntity
0xc68a  ldarg.0
0xc68b  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::_slaEntity
0xc690  ret
```
