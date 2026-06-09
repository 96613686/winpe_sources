# Microsoft.Crm.Common.Application.Platform.Email::SetCurrentUserAsSender

- ea: `0x36f0`
- end: `0x3781`
- name: `Microsoft.Crm.Common.Application.Platform.Email::SetCurrentUserAsSender`
- size: `145`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3530`
- `0x35f0`
- `0x39f0`

## pseudocode

```c

```

## disassembly

```asm
0x36f0  ldarg.0
0x36f1  ldstr    aFrom// "from"
0x36f6  ldnull
0x36f7  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x36fc  ldstr    aActivityparty// "activityparty"
0x3701  ldarg.0
0x3702  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x3707  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x370c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3711  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x3716  stloc.0
0x3717  ldloc.0
0x3718  ldstr    aPartyid// "partyid"
0x371d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x3722  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x3727  box      [mscorlib]System.Guid
0x372c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3731  ldloc.0
0x3732  ldstr    aPartyidname// "partyidname"
0x3737  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x373c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UserName()
0x3741  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3746  ldloc.0
0x3747  ldstr    aPartyobjecttyp// "partyobjecttypecode"
0x374c  ldstr    aSystemuser// "systemuser"
0x3751  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3756  ldloc.0
0x3757  ldstr    aAddressused// "addressused"
0x375c  ldstr    aEmailAddress// "EMAIL_ADDRESS"
0x3761  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3766  ldarg.0
0x3767  ldstr    aFrom// "from"
0x376c  ldc.i4.1
0x376d  newarr   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity
0x3772  dup
0x3773  ldc.i4.0
0x3774  ldloc.0
0x3775  stelem.ref
0x3776  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>)
0x377b  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3780  ret
```
