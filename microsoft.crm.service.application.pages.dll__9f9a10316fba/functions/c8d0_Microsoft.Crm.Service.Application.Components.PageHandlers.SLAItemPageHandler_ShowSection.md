# Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::ShowSection

- ea: `0xc8d0`
- end: `0xc8f9`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::ShowSection`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xc720`

## callees

- `0xc8d0`

## pseudocode

```c

```

## disassembly

```asm
0xc8d0  ldarg.1
0xc8d1  ldarg.2
0xc8d2  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0xc8d7  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormSection
0xc8dc  stloc.0
0xc8dd  ldloc.0
0xc8de  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormSection::get_RenderAsVisible()
0xc8e3  brtrue.s loc_C8EC
0xc8e5  ldloc.0
0xc8e6  ldc.i4.1
0xc8e7  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormSection::set_RenderAsVisible(bool)
0xc8ec  leave.s  loc_C8F8
0xc8ee  ldloc.0
0xc8ef  brfalse.s loc_C8F7
0xc8f1  ldloc.0
0xc8f2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc8f7  endfinally
0xc8f8  ret
```
