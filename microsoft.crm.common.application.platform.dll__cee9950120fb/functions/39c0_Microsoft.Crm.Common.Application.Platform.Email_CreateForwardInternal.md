# Microsoft.Crm.Common.Application.Platform.Email::CreateForwardInternal

- ea: `0x39c0`
- end: `0x39e9`
- name: `Microsoft.Crm.Common.Application.Platform.Email::CreateForwardInternal`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3890`

## callees

- `0x3320`
- `0x39f0`

## pseudocode

```c

```

## disassembly

```asm
0x39c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x39c5  ldstr    aEmailPrefixFor// "Email_Prefix_Forward"
0x39ca  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x39cf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x39d4  stloc.0
0x39d5  ldarg.0
0x39d6  ldarg.1
0x39d7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x39dc  ldloc.0
0x39dd  call     instance void Microsoft.Crm.Common.Application.Platform.Email::CreateEmailResponseFromExistingEmail(valuetype [mscorlib]System.Guid existingEmailId, string subjectPrefix)
0x39e2  ldarg.0
0x39e3  call     instance void Microsoft.Crm.Common.Application.Platform.Email::CreateForwardRecipients()
0x39e8  ret
```
