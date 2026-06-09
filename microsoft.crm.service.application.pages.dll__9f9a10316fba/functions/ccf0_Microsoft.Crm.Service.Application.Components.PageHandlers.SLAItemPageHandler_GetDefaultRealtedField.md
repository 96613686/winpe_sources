# Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::GetDefaultRealtedField

- ea: `0xccf0`
- end: `0xcd16`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::GetDefaultRealtedField`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xcb80`

## callees

- `0xc610`
- `0xccf0`

## pseudocode

```c

```

## disassembly

```asm
0xccf0  ldarg.0
0xccf1  call     instance int32 Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::get_ObjectTypeId()
0xccf6  stloc.0
0xccf7  ldloc.0
0xccf8  ldc.i4.s 0x70
0xccfa  bne.un.s loc_CD10
0xccfc  ldarg.0
0xccfd  ldfld    bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::useSLAKPI
0xcd02  brfalse.s loc_CD0A
0xcd04  ldstr    aFirstresponseb// "firstresponsebykpiid"
0xcd09  ret
0xcd0a  ldstr    aResponseby// "responseby"
0xcd0f  ret
0xcd10  ldstr    asc_15D82// ""
0xcd15  ret
```
