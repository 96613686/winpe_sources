# Microsoft.Crm.Common.Application.Platform.Email::CreateReply

- ea: `0x3790`
- end: `0x3807`
- name: `Microsoft.Crm.Common.Application.Platform.Email::CreateReply`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x31a0`
- `0x3320`
- `0x34b0`
- `0x3530`
- `0x3ad0`

## string_xrefs

- `0x37e5`: `<columnset><column>subject</column><column>description</column><column>compressed</column><column>actualend</column><column>from</column><column>to</column><column>cc</column></columnset>`

## pseudocode

```c

```

## disassembly

```asm
0x3790  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3795  ldstr    aEmailPrefixRep// "Email_Prefix_Reply"
0x379a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x379f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x37a4  stloc.0
0x37a5  ldloca.s 1
0x37a7  ldarg.1
0x37a8  call     instance void [mscorlib]System.Guid::.ctor(string)
0x37ad  ldarg.0
0x37ae  ldloc.1
0x37af  ldloc.0
0x37b0  call     instance void Microsoft.Crm.Common.Application.Platform.Email::CreateEmailResponseFromExistingEmail(valuetype [mscorlib]System.Guid existingEmailId, string subjectPrefix)
0x37b5  ldarg.0
0x37b6  ldloc.1
0x37b7  call     instance void Microsoft.Crm.Common.Application.Platform.Email::SetParentActivityIdAndClearCorrelationFields(valuetype [mscorlib]System.Guid parentId)
0x37bc  ldarg.0
0x37bd  call     instance void Microsoft.Crm.Common.Application.Platform.Email::CreateReplyRecipients()
0x37c2  ldstr    aEmail// "email"
0x37c7  ldarg.0
0x37c8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x37cd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x37d2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x37d7  newobj   instance void Microsoft.Crm.Common.Application.Platform.Email::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType type)
0x37dc  stloc.2
0x37dd  ldloc.2
0x37de  ldarg.1
0x37df  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x37e4  ldloc.2
0x37e5  ldstr    aColumnsetColum// "<columnset><column>subject</column><col"...
0x37ea  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x37ef  ldarg.0
0x37f0  ldstr    aDescription// "description"
0x37f5  ldloc.2
0x37f6  callvirt instance string Microsoft.Crm.Common.Application.Platform.Email::BuildEmailFollowUpBody()
0x37fb  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3800  ldarg.0
0x3801  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::CreateAndRetrieve()
0x3806  ret
```
