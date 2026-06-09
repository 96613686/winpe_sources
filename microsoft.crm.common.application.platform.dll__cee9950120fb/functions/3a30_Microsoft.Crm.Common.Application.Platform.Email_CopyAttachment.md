# Microsoft.Crm.Common.Application.Platform.Email::CopyAttachment

- ea: `0x3a30`
- end: `0x3ace`
- name: `Microsoft.Crm.Common.Application.Platform.Email::CopyAttachment`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3890`

## callees

- `0x3a30`

## string_xrefs

- `0x3aaf`: `Attachment was created with ID: {0}, but should have been created with ID: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x3a30  ldstr    aActivitymimeat_0// "activitymimeattachment"
0x3a35  ldarg.2
0x3a36  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3a3b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x3a40  ldarg.0
0x3a41  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3a46  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.AllColumns::.ctor()
0x3a4b  ldarg.2
0x3a4c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3a51  dup
0x3a52  ldstr    aActivityid// "activityid"
0x3a57  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::ClearAttribute(string)
0x3a5c  ldsfld   string [mscorlib]System.String::Empty
0x3a61  stloc.0
0x3a62  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x3a67  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x3a6c  stloc.0
0x3a6d  dup
0x3a6e  ldstr    aActivitymimeat// "activitymimeattachmentid"
0x3a73  ldloc.0
0x3a74  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3a79  dup
0x3a7a  ldstr    aObjectid// "objectid"
0x3a7f  ldarg.1
0x3a80  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3a85  dup
0x3a86  ldstr    aAttachmentid// "attachmentid"
0x3a8b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::ClearAttribute(string)
0x3a90  ldarg.2
0x3a91  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Create(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3a96  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x3a9b  stloc.1
0x3a9c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x3aa1  brtrue.s loc_3ACC
0x3aa3  ldloc.1
0x3aa4  ldloc.0
0x3aa5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3aaa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3aaf  ldstr    aAttachmentWasC// "Attachment was created with ID: {0}, bu"...
0x3ab4  ldc.i4.2
0x3ab5  newarr   [mscorlib]System.Object
0x3aba  dup
0x3abb  ldc.i4.0
0x3abc  ldloc.1
0x3abd  stelem.ref
0x3abe  dup
0x3abf  ldc.i4.1
0x3ac0  ldloc.0
0x3ac1  stelem.ref
0x3ac2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3ac7  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x3acc  ldloc.1
0x3acd  ret
```
