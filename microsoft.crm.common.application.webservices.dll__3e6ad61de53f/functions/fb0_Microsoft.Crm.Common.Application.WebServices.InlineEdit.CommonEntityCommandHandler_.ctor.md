# Microsoft.Crm.Common.Application.WebServices.InlineEdit.CommonEntityCommandHandler::.ctor

- ea: `0xfb0`
- end: `0x1081`
- name: `Microsoft.Crm.Common.Application.WebServices.InlineEdit.CommonEntityCommandHandler::.ctor`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x10a0`

## callees

- `0x8b0`
- `0xa70`
- `0xb40`
- `0xc30`
- `0xdd0`
- `0xeb0`
- `0xf90`
- `0xfb0`

## pseudocode

```c

```

## disassembly

```asm
0xfb0  ldarg.0
0xfb1  ldarg.1
0xfb2  call     instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.EntityCommandHandler::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xfb7  ldarg.1
0xfb8  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0xfbd  stloc.0
0xfbe  ldloc.0
0xfbf  ldc.i4   0x400
0xfc4  bgt.s    loc_FD6
0xfc6  ldloc.0
0xfc7  ldc.i4.4
0xfc8  beq.s    loc_100D
0xfca  ldloc.0
0xfcb  ldc.i4   0x400
0xfd0  beq      loc_105C
0xfd5  ret
0xfd6  ldloc.0
0xfd7  ldc.i4   0x106A
0xfdc  beq.s    loc_FE7
0xfde  ldloc.0
0xfdf  ldc.i4   0x106C
0xfe4  beq.s    loc_FFA
0xfe6  ret
0xfe7  ldarg.0
0xfe8  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.ICommand> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.IEntityCommandHandler::get_SupportedCommands()
0xfed  ldc.i4.s 0x43
0xfef  newobj   instance void Microsoft.Crm.Common.Application.WebServices.InlineEdit.EmailSendCommand::.ctor()
0xff4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.ICommand>::Add(var<u1>, !!T0)
0xff9  ret
0xffa  ldarg.0
0xffb  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.ICommand> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.IEntityCommandHandler::get_SupportedCommands()
0x1000  ldc.i4.s 0x37
0x1002  newobj   instance void Microsoft.Crm.Common.Application.WebServices.InlineEdit.FaxSendCommand::.ctor()
0x1007  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.ICommand>::Add(var<u1>, !!T0)
0x100c  ret
0x100d  ldarg.0
0x100e  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.ICommand> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.IEntityCommandHandler::get_SupportedCommands()
0x1013  ldc.i4.s 0x10
0x1015  newobj   instance void Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadDisqualifyCommand::.ctor()
0x101a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.ICommand>::Add(var<u1>, !!T0)
0x101f  ldarg.0
0x1020  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.ICommand> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.IEntityCommandHandler::get_SupportedCommands()
0x1025  ldc.i4.s 0xF
0x1027  newobj   instance void Microsoft.Crm.Common.Application.WebServices.InlineEdit.LeadQualifyCommand::.ctor()
0x102c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.ICommand>::Add(var<u1>, !!T0)
0x1031  ldarg.0
0x1032  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.ICommand> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.IEntityCommandHandler::get_SupportedCommands()
0x1037  ldc.i4   0xCF
0x103c  newobj   instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.InlineEdit.CreateConnectionCommand::.ctor()
0x1041  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.ICommand>::Add(var<u1>, !!T0)
0x1046  ldarg.0
0x1047  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.ICommand> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.IEntityCommandHandler::get_SupportedCommands()
0x104c  ldc.i4   0xD2
0x1051  newobj   instance void Microsoft.Crm.Common.Application.WebServices.InlineEdit.AssociateToCompetitorCommand::.ctor()
0x1056  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.ICommand>::Add(var<u1>, !!T0)
0x105b  ret
0x105c  ldarg.0
0x105d  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.ICommand> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.IEntityCommandHandler::get_SupportedCommands()
0x1062  ldc.i4.s 0x23
0x1064  newobj   instance void Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertToKitCommand::.ctor()
0x1069  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.ICommand>::Add(var<u1>, !!T0)
0x106e  ldarg.0
0x106f  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.ICommand> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.IEntityCommandHandler::get_SupportedCommands()
0x1074  ldc.i4.s 0x24
0x1076  newobj   instance void Microsoft.Crm.Common.Application.WebServices.InlineEdit.ProductConvertFromKitCommand::.ctor()
0x107b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.ICommand>::Add(var<u1>, !!T0)
0x1080  ret
```
