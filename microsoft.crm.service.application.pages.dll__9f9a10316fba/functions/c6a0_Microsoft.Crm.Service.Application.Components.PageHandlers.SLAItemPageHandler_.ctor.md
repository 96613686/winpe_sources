# Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::.ctor

- ea: `0xc6a0`
- end: `0xc6eb`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::.ctor`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1040`

## string_xrefs

- `0xc6a9`: `UpdateStep27`
- `0xc6bd`: `UpdateStep18`
- `0xc6d1`: `UpdateStep14`

## pseudocode

```c

```

## disassembly

```asm
0xc6a0  ldarg.0
0xc6a1  ldc.i4.1
0xc6a2  newarr   [mscorlib]System.String
0xc6a7  dup
0xc6a8  ldc.i4.0
0xc6a9  ldstr    aUpdatestep27// "UpdateStep27"
0xc6ae  stelem.ref
0xc6af  stfld    string[] Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::HideKPIFailSteps
0xc6b4  ldarg.0
0xc6b5  ldc.i4.1
0xc6b6  newarr   [mscorlib]System.String
0xc6bb  dup
0xc6bc  ldc.i4.0
0xc6bd  ldstr    aUpdatestep18// "UpdateStep18"
0xc6c2  stelem.ref
0xc6c3  stfld    string[] Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::HideKPIWarnSteps
0xc6c8  ldarg.0
0xc6c9  ldc.i4.2
0xc6ca  newarr   [mscorlib]System.String
0xc6cf  dup
0xc6d0  ldc.i4.0
0xc6d1  ldstr    aUpdatestep14// "UpdateStep14"
0xc6d6  stelem.ref
0xc6d7  dup
0xc6d8  ldc.i4.1
0xc6d9  ldstr    aStopworkflowst// "StopWorkflowStep8"
0xc6de  stelem.ref
0xc6df  stfld    string[] Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::HideKPISuccessSteps
0xc6e4  ldarg.0
0xc6e5  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::.ctor()
0xc6ea  ret
```
