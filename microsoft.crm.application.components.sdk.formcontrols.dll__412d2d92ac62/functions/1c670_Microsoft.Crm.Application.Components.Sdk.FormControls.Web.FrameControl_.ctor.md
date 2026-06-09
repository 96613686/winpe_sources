# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::.ctor

- ea: `0x1c670`
- end: `0x1c685`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::.ctor`
- size: `21`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x153a0`
- `0x19000`
- `0x253d0`
- `0x29200`
- `0x29cb0`
- `0x2b950`
- `0x2cb20`

## callees

- `0x17840`

## pseudocode

```c

```

## disassembly

```asm
0x1c670  ldarg.0
0x1c671  ldc.i4.1
0x1c672  stfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::restricted
0x1c677  ldarg.0
0x1c678  ldc.i4.1
0x1c679  stfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::border
0x1c67e  ldarg.0
0x1c67f  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControl::.ctor()
0x1c684  ret
```
