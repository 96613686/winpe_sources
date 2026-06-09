# Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::get_ObjectTypeId

- ea: `0xc610`
- end: `0xc656`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::get_ObjectTypeId`
- size: `70`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xc950`
- `0xcb80`
- `0xccf0`

## callees

- `0xc610`
- `0xc660`
- `0xc670`

## pseudocode

```c

```

## disassembly

```asm
0xc610  ldarg.0
0xc611  ldfld    int32 Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::_ObjectTypeId
0xc616  brtrue.s loc_C64F
0xc618  ldarg.0
0xc619  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::get_SlaEntity()
0xc61e  ldstr    aObjecttypecode// "objecttypecode"
0xc623  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xc628  brtrue.s loc_C634
0xc62a  ldarg.0
0xc62b  ldc.i4.s 0x70
0xc62d  call     instance void Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::set_ObjectTypeId(int32 value)
0xc632  br.s     loc_C64F
0xc634  ldarg.0
0xc635  ldarg.0
0xc636  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::get_SlaEntity()
0xc63b  ldstr    aObjecttypecode// "objecttypecode"
0xc640  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xc645  unbox.any [mscorlib]System.Int32
0xc64a  call     instance void Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::set_ObjectTypeId(int32 value)
0xc64f  ldarg.0
0xc650  ldfld    int32 Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::_ObjectTypeId
0xc655  ret
```
