# Microsoft.Crm.Common.Application.Platform.Email::Send

- ea: `0x3e30`
- end: `0x3e92`
- name: `Microsoft.Crm.Common.Application.Platform.Email::Send`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x30b0`
- `0x3e30`
- `0x3ea0`

## pseudocode

```c

```

## disassembly

```asm
0x3e30  ldarg.0
0x3e31  call     instance bool Microsoft.Crm.Common.Application.Platform.Email::VerifyPartiesForSend()
0x3e36  brtrue.s loc_3E3A
0x3e38  ldc.i4.0
0x3e39  ret
0x3e3a  ldsfld   string [mscorlib]System.String::Empty
0x3e3f  stloc.0
0x3e40  ldarg.0
0x3e41  ldstr    aSubject// "subject"
0x3e46  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3e4b  isinst   [mscorlib]System.String
0x3e50  stloc.1
0x3e51  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x3e56  brtrue.s loc_3E73
0x3e58  ldloc.1
0x3e59  brtrue.s loc_3E61
0x3e5b  ldsfld   string [mscorlib]System.String::Empty
0x3e60  stloc.1
0x3e61  ldloc.1
0x3e62  ldarg.0
0x3e63  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x3e68  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x3e6d  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::GetTrackingTokenEmail(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3e72  stloc.0
0x3e73  ldarg.0
0x3e74  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x3e79  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3e7e  ldloc.0
0x3e7f  ldarg.0
0x3e80  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x3e85  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x3e8a  call     string Microsoft.Crm.Common.Application.Platform.DataSourceCommon::SendEmail(valuetype [mscorlib]System.Guid emailId, string trackingToken, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3e8f  pop
0x3e90  ldc.i4.1
0x3e91  ret
```
