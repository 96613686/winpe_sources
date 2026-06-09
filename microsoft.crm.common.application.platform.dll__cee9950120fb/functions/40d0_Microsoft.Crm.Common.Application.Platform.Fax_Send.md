# Microsoft.Crm.Common.Application.Platform.Fax::Send

- ea: `0x40d0`
- end: `0x4110`
- name: `Microsoft.Crm.Common.Application.Platform.Fax::Send`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x3170`

## callees

- `0x30c0`
- `0x40d0`
- `0x4110`

## pseudocode

```c

```

## disassembly

```asm
0x40d0  ldarg.0
0x40d1  call     instance bool Microsoft.Crm.Common.Application.Platform.Fax::VerifyPartiesForSend()
0x40d6  brtrue.s loc_40DA
0x40d8  ldc.i4.0
0x40d9  ret
0x40da  ldarg.0
0x40db  ldstr    aFaxnumber// "faxnumber"
0x40e0  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x40e5  isinst   [mscorlib]System.String
0x40ea  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x40ef  brfalse.s loc_40F3
0x40f1  ldc.i4.0
0x40f2  ret
0x40f3  ldarg.0
0x40f4  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x40f9  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x40fe  ldarg.0
0x40ff  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x4104  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x4109  call     void Microsoft.Crm.Common.Application.Platform.DataSourceCommon::SendFax(valuetype [mscorlib]System.Guid faxId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x410e  ldc.i4.1
0x410f  ret
```
