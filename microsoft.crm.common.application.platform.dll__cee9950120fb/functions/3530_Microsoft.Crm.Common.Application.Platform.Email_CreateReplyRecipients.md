# Microsoft.Crm.Common.Application.Platform.Email::CreateReplyRecipients

- ea: `0x3530`
- end: `0x35a0`
- name: `Microsoft.Crm.Common.Application.Platform.Email::CreateReplyRecipients`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x3790`

## callees

- `0x3530`
- `0x35a0`
- `0x36f0`

## pseudocode

```c

```

## disassembly

```asm
0x3530  ldarg.0
0x3531  ldstr    aTo// "to"
0x3536  ldnull
0x3537  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x353c  ldarg.0
0x353d  ldstr    aCc// "cc"
0x3542  ldnull
0x3543  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3548  ldarg.0
0x3549  ldstr    aBcc// "bcc"
0x354e  ldnull
0x354f  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3554  ldarg.0
0x3555  ldstr    aFrom// "from"
0x355a  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x355f  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0x3564  stloc.0
0x3565  ldloc.0
0x3566  brfalse.s loc_3599
0x3568  ldloc.0
0x3569  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x356e  ldc.i4.0
0x356f  ble.s    loc_3599
0x3571  ldloc.0
0x3572  ldc.i4.0
0x3573  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x3578  stloc.1
0x3579  ldloc.1
0x357a  call     void Microsoft.Crm.Common.Application.Platform.Email::ClearAttributesForNewEmail(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity currentSender)
0x357f  ldarg.0
0x3580  ldstr    aTo// "to"
0x3585  ldc.i4.1
0x3586  newarr   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity
0x358b  dup
0x358c  ldc.i4.0
0x358d  ldloc.1
0x358e  stelem.ref
0x358f  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>)
0x3594  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3599  ldarg.0
0x359a  call     instance void Microsoft.Crm.Common.Application.Platform.Email::SetCurrentUserAsSender()
0x359f  ret
```
