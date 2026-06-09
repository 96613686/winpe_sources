# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::IsVisibleInCurrentView

- ea: `0x8460`
- end: `0x8499`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::IsVisibleInCurrentView`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x84a0`

## callees

- `0x8460`

## pseudocode

```c

```

## disassembly

```asm
0x8460  ldarg.0
0x8461  ldfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.AttributeMapView Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_view
0x8466  ldc.i4.2
0x8467  bne.un.s loc_846B
0x8469  ldc.i4.1
0x846a  ret
0x846b  ldarg.1
0x846c  ldc.i4.1
0x846d  bne.un.s loc_8479
0x846f  ldarg.0
0x8470  ldfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.AttributeMapView Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_view
0x8475  brtrue.s loc_8479
0x8477  ldc.i4.1
0x8478  ret
0x8479  ldarg.1
0x847a  ldc.i4.1
0x847b  beq.s    loc_8488
0x847d  ldarg.0
0x847e  ldfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.AttributeMapView Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_view
0x8483  ldc.i4.1
0x8484  bne.un.s loc_8488
0x8486  ldc.i4.1
0x8487  ret
0x8488  ldarg.1
0x8489  ldc.i4.4
0x848a  bne.un.s loc_8497
0x848c  ldarg.0
0x848d  ldfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.AttributeMapView Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_view
0x8492  ldc.i4.1
0x8493  bne.un.s loc_8497
0x8495  ldc.i4.1
0x8496  ret
0x8497  ldc.i4.0
0x8498  ret
```
