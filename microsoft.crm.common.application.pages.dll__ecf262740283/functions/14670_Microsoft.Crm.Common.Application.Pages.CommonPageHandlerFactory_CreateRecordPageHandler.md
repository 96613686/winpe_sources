# Microsoft.Crm.Common.Application.Pages.CommonPageHandlerFactory::CreateRecordPageHandler

- ea: `0x14670`
- end: `0x1473d`
- name: `Microsoft.Crm.Common.Application.Pages.CommonPageHandlerFactory::CreateRecordPageHandler`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x10d30`
- `0x114a0`
- `0x11fb0`
- `0x12290`
- `0x123c0`
- `0x12760`
- `0x127d0`
- `0x12a20`
- `0x12c50`
- `0x131e0`
- `0x13250`
- `0x14670`

## pseudocode

```c

```

## disassembly

```asm
0x14670  ldarg.2
0x14671  ldc.i4   0x420
0x14676  bgt.s    loc_146AF
0x14678  ldarg.2
0x14679  ldc.i4   0x3F5
0x1467e  bgt.s    loc_14695
0x14680  ldarg.2
0x14681  ldc.i4.s 0x5C
0x14683  beq      loc_1471B
0x14688  ldarg.2
0x14689  ldc.i4   0x3F5
0x1468e  beq.s    loc_146F7
0x14690  br       loc_1472D
0x14695  ldarg.2
0x14696  ldc.i4   0x400
0x1469b  beq.s    loc_14709
0x1469d  ldarg.2
0x1469e  ldc.i4   0x41F
0x146a3  beq.s    loc_1470F
0x146a5  ldarg.2
0x146a6  ldc.i4   0x420
0x146ab  beq.s    loc_14715
0x146ad  br.s     loc_1472D
0x146af  ldarg.2
0x146b0  ldc.i4   0x7ED
0x146b5  bgt.s    loc_146D1
0x146b7  ldarg.2
0x146b8  ldc.i4   0x42F
0x146bd  beq.s    loc_146FD
0x146bf  ldarg.2
0x146c0  ldc.i4   0x438
0x146c5  beq.s    loc_146F1
0x146c7  ldarg.2
0x146c8  ldc.i4   0x7ED
0x146cd  beq.s    loc_14703
0x146cf  br.s     loc_1472D
0x146d1  ldarg.2
0x146d2  ldc.i4   0x1069
0x146d7  beq.s    loc_14721
0x146d9  ldarg.2
0x146da  ldc.i4   0x109B
0x146df  beq.s    loc_146EB
0x146e1  ldarg.2
0x146e2  ldc.i4   0x24B9
0x146e7  beq.s    loc_14727
0x146e9  br.s     loc_1472D
0x146eb  newobj   instance void Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::.ctor()
0x146f0  ret
0x146f1  newobj   instance void Microsoft.Crm.Common.Application.Components.PageHandlers.DiscountTypeRecordPageHandler::.ctor()
0x146f6  ret
0x146f7  newobj   instance void Microsoft.Crm.Common.Application.Components.PageHandlers.DiscountTypeItemRecordPageHandler::.ctor()
0x146fc  ret
0x146fd  newobj   instance void Microsoft.Crm.Common.Application.Components.PageHandlers.CustomerAddressRecordPageHandler::.ctor()
0x14702  ret
0x14703  newobj   instance void Microsoft.Crm.Common.Application.Components.PageHandlers.QueueItemRecordPageHandler::.ctor()
0x14708  ret
0x14709  newobj   instance void Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::.ctor()
0x1470e  ret
0x1470f  newobj   instance void Microsoft.Crm.Common.Application.Components.PageHandlers.UoMRecordPageHandler::.ctor()
0x14714  ret
0x14715  newobj   instance void Microsoft.Crm.Common.Application.Components.PageHandlers.UoMScheduleRecordPageHandler::.ctor()
0x1471a  ret
0x1471b  newobj   instance void Microsoft.Crm.Common.Application.Components.PageHandlers.TeamTemplateRecordPageHandler::.ctor()
0x14720  ret
0x14721  newobj   instance void Microsoft.Crm.Common.Application.Components.PageHandlers.AppointmentRecordPageHandler::.ctor()
0x14726  ret
0x14727  newobj   instance void Microsoft.Crm.Common.Application.Components.PageHandlers.ProfileRuleItemRecordPageHandler::.ctor()
0x1472c  ret
0x1472d  ldstr    aUnsupportedEnt_0// "Unsupported Entity code."
0x14732  ldstr    aEntitytypecode_0// "entityTypeCode"
0x14737  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1473c  throw
```
