# Microsoft.Crm.Common.Application.Platform.Template::Send_0

- ea: `0x5110`
- end: `0x517b`
- name: `Microsoft.Crm.Common.Application.Platform.Template::Send_0`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x30d0`
- `0x5110`

## pseudocode

```c

```

## disassembly

```asm
0x5110  ldarg.1
0x5111  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5116  ldarg.s  5
0x5118  ldarg.s  4
0x511a  ldarg.0
0x511b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x5120  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x5125  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x512a  ldarg.s  7
0x512c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5131  brtrue.s loc_513C
0x5133  ldarg.s  7
0x5135  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x513a  br.s     loc_5141
0x513c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5141  ldarg.s  6
0x5143  ldarg.0
0x5144  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x5149  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x514e  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5153  ldarg.2
0x5154  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5159  ldarg.3
0x515a  ldarg.0
0x515b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x5160  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x5165  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x516a  ldarg.0
0x516b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x5170  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x5175  call     void Microsoft.Crm.Common.Application.Platform.DataSourceCommon::SendTemplate(valuetype [mscorlib]System.Guid templateId, valuetype [mscorlib]System.Guid[] recipients, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType recipientType, valuetype [mscorlib]System.Guid regardingId, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType regardingType, valuetype [mscorlib]System.Guid senderId, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType senderType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x517a  ret
```
