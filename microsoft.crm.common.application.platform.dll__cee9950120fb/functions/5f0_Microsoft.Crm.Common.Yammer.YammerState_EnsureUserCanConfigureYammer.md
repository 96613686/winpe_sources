# Microsoft.Crm.Common.Yammer.YammerState::EnsureUserCanConfigureYammer

- ea: `0x5f0`
- end: `0x62b`
- name: `Microsoft.Crm.Common.Yammer.YammerState::EnsureUserCanConfigureYammer`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2a0`
- `0x480`
- `0x5f0`

## pseudocode

```c

```

## disassembly

```asm
0x5f0  ldarg.0
0x5f1  call     class Microsoft.Crm.Common.Yammer.IYammerState Microsoft.Crm.Common.Yammer.YammerState::Read(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation currentUser)
0x5f6  callvirt instance bool Microsoft.Crm.Common.Yammer.IYammerState::get_CanConfigureYammer()
0x5fb  brtrue.s loc_62A
0x5fd  ldc.i4.8
0x5fe  ldarg.0
0x5ff  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x604  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal::.ctor(int32, valuetype [mscorlib]System.Guid)
0x609  ldstr    a79c8bb808c984b// "{79C8BB80-8C98-4B4B-907E-B82CC1F1EE6E}"
0x60e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x613  ldc.i4   0x80040220
0x618  ldarg.0
0x619  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x61e  ldc.i4.0
0x61f  ldc.i4.0
0x620  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x625  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::ThrowCrmSecurityException(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal, valuetype [mscorlib]System.Guid, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x62a  ret
```
