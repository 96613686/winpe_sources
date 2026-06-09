# Microsoft.Crm.Common.Application.Platform.Template::Send

- ea: `0x5070`
- end: `0x5103`
- name: `Microsoft.Crm.Common.Application.Platform.Template::Send`
- size: `147`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x30d0`
- `0x5070`

## pseudocode

```c

```

## disassembly

```asm
0x5070  ldarg.s  5
0x5072  ldlen
0x5073  conv.i4
0x5074  newarr   [mscorlib]System.Guid
0x5079  stloc.0
0x507a  ldc.i4.0
0x507b  stloc.1
0x507c  br.s     loc_5092
0x507e  ldloc.0
0x507f  ldloc.1
0x5080  ldarg.s  5
0x5082  ldloc.1
0x5083  ldelem.ref
0x5084  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5089  stelem   [mscorlib]System.Guid
0x508e  ldloc.1
0x508f  ldc.i4.1
0x5090  add
0x5091  stloc.1
0x5092  ldloc.1
0x5093  ldarg.s  5
0x5095  ldlen
0x5096  conv.i4
0x5097  blt.s    loc_507E
0x5099  ldarg.1
0x509a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x509f  ldloc.0
0x50a0  ldarg.s  4
0x50a2  ldarg.0
0x50a3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x50a8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x50ad  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x50b2  ldarg.s  7
0x50b4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x50b9  brtrue.s loc_50C4
0x50bb  ldarg.s  7
0x50bd  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x50c2  br.s     loc_50C9
0x50c4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x50c9  ldarg.s  6
0x50cb  ldarg.0
0x50cc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x50d1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x50d6  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x50db  ldarg.2
0x50dc  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x50e1  ldarg.3
0x50e2  ldarg.0
0x50e3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x50e8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x50ed  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x50f2  ldarg.0
0x50f3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x50f8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x50fd  call     void Microsoft.Crm.Common.Application.Platform.DataSourceCommon::SendTemplate(valuetype [mscorlib]System.Guid templateId, valuetype [mscorlib]System.Guid[] recipients, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType recipientType, valuetype [mscorlib]System.Guid regardingId, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType regardingType, valuetype [mscorlib]System.Guid senderId, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType senderType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x5102  ret
```
