# Microsoft.Crm.Common.Application.Platform.Email::CreateReplyAll

- ea: `0x3810`
- end: `0x3887`
- name: `Microsoft.Crm.Common.Application.Platform.Email::CreateReplyAll`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x31a0`
- `0x3320`
- `0x34b0`
- `0x35f0`
- `0x3ad0`

## string_xrefs

- `0x3865`: `<columnset><column>subject</column><column>description</column><column>compressed</column><column>actualend</column><column>from</column><column>to</column><column>cc</column></columnset>`

## pseudocode

```c

```

## disassembly

```asm
0x3810  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3815  ldstr    aEmailPrefixRep// "Email_Prefix_Reply"
0x381a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x381f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3824  stloc.0
0x3825  ldloca.s 1
0x3827  ldarg.1
0x3828  call     instance void [mscorlib]System.Guid::.ctor(string)
0x382d  ldarg.0
0x382e  ldloc.1
0x382f  ldloc.0
0x3830  call     instance void Microsoft.Crm.Common.Application.Platform.Email::CreateEmailResponseFromExistingEmail(valuetype [mscorlib]System.Guid existingEmailId, string subjectPrefix)
0x3835  ldarg.0
0x3836  ldloc.1
0x3837  call     instance void Microsoft.Crm.Common.Application.Platform.Email::SetParentActivityIdAndClearCorrelationFields(valuetype [mscorlib]System.Guid parentId)
0x383c  ldarg.0
0x383d  call     instance void Microsoft.Crm.Common.Application.Platform.Email::CreateReplyAllRecipients()
0x3842  ldstr    aEmail// "email"
0x3847  ldarg.0
0x3848  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x384d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x3852  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3857  newobj   instance void Microsoft.Crm.Common.Application.Platform.Email::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType type)
0x385c  stloc.2
0x385d  ldloc.2
0x385e  ldarg.1
0x385f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x3864  ldloc.2
0x3865  ldstr    aColumnsetColum// "<columnset><column>subject</column><col"...
0x386a  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x386f  ldarg.0
0x3870  ldstr    aDescription// "description"
0x3875  ldloc.2
0x3876  callvirt instance string Microsoft.Crm.Common.Application.Platform.Email::BuildEmailFollowUpBody()
0x387b  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3880  ldarg.0
0x3881  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::CreateAndRetrieve()
0x3886  ret
```
