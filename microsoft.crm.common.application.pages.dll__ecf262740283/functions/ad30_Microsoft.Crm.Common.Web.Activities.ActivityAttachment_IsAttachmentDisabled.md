# Microsoft.Crm.Common.Web.Activities.ActivityAttachment::IsAttachmentDisabled

- ea: `0xad30`
- end: `0xadf7`
- name: `Microsoft.Crm.Common.Web.Activities.ActivityAttachment::IsAttachmentDisabled`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xabb0`

## callees

- `0xad30`

## string_xrefs

- `0xad4f`: `template`
- `0xade7`: `Scheduled`

## pseudocode

```c

```

## disassembly

```asm
0xad30  ldarg.2
0xad31  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xad36  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xad3b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xad40  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xad45  stloc.0
0xad46  ldloca.s 1
0xad48  ldarg.1
0xad49  call     instance void [mscorlib]System.Guid::.ctor(string)
0xad4e  ldloc.0
0xad4f  ldstr    aTemplate// "template"
0xad54  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xad59  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xad5e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::op_Equality(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xad63  brfalse.s loc_ADAA
0xad65  ldloc.0
0xad66  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xad6b  ldloc.1
0xad6c  ldc.i4.1
0xad6d  newarr   [mscorlib]System.String
0xad72  dup
0xad73  ldc.i4.0
0xad74  ldstr    aIscustomizable// "iscustomizable"
0xad79  stelem.ref
0xad7a  ldc.i4.0
0xad7b  ldc.i4.1
0xad7c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xad81  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], bool, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xad86  stloc.3
0xad87  ldloc.3
0xad88  ldstr    aIscustomizable// "iscustomizable"
0xad8d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xad92  brfalse.s loc_ADA8
0xad94  ldloc.3
0xad95  ldstr    aIscustomizable// "iscustomizable"
0xad9a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xad9f  unbox.any [mscorlib]System.Boolean
0xada4  brtrue.s loc_ADA8
0xada6  ldc.i4.1
0xada7  ret
0xada8  ldc.i4.0
0xada9  ret
0xadaa  ldloc.0
0xadab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xadb0  ldloc.1
0xadb1  ldc.i4.1
0xadb2  newarr   [mscorlib]System.String
0xadb7  dup
0xadb8  ldc.i4.0
0xadb9  ldstr    aStatecode// "statecode"
0xadbe  stelem.ref
0xadbf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xadc4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xadc9  ldstr    aStatecode// "statecode"
0xadce  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xadd3  isinst   [mscorlib]System.String
0xadd8  stloc.2
0xadd9  ldloc.2
0xadda  ldstr    aOpen// "Open"
0xaddf  call     bool [mscorlib]System.String::op_Equality(string, string)
0xade4  brtrue.s loc_ADF3
0xade6  ldloc.2
0xade7  ldstr    aScheduled// "Scheduled"
0xadec  call     bool [mscorlib]System.String::op_Equality(string, string)
0xadf1  brfalse.s loc_ADF5
0xadf3  ldc.i4.0
0xadf4  ret
0xadf5  ldc.i4.1
0xadf6  ret
```
