# Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::GetWizardFormId

- ea: `0x3d40`
- end: `0x3d68`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::GetWizardFormId`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3920`

## callees

- `0x3d40`

## pseudocode

```c

```

## disassembly

```asm
0x3d40  ldc.i4   0x106A
0x3d45  ldarg.0
0x3d46  ldfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::objectTypeCode
0x3d4b  bne.un.s loc_3D53
0x3d4d  ldstr    a9360ee64523843// "9360EE64-5238-4334-A1DE-C155D20FE63D"
0x3d52  ret
0x3d53  ldc.i4   0x1069
0x3d58  ldarg.0
0x3d59  ldfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::objectTypeCode
0x3d5e  bne.un.s loc_3D66
0x3d60  ldstr    a3a7d8836E2d74b// "3A7D8836-E2D7-4BC3-919B-CC86A8D9688A"
0x3d65  ret
0x3d66  ldnull
0x3d67  ret
```
