# Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.MailboxNotificationGenerator::TryAddNotificationForO365AdminApproval

- ea: `0x81260`
- end: `0x813b5`
- name: `Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.MailboxNotificationGenerator::TryAddNotificationForO365AdminApproval`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x81240`

## callees

- `0x11760`
- `0x30260`
- `0x30e70`
- `0x5bab0`
- `0x5be20`
- `0x6a2d0`
- `0x81260`
- `0x81870`

## string_xrefs

- `0x81296`: `incomingemaildeliverymethod`
- `0x812a4`: `incomingemaildeliverymethod`
- `0x812b7`: `incomingemaildeliverymethod`
- `0x81342`: `incomingcredentialretrieval`
- `0x81351`: `incomingcredentialretrieval`

## pseudocode

```c

```

## disassembly

```asm
0x81260  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x81265  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x8126a  ldc.i4.2
0x8126b  bne.un   loc_813B3
0x81270  ldarg.1
0x81271  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x81276  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x8127b  brfalse  loc_813B3
0x81280  ldarg.1
0x81281  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x81286  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x8128b  unbox.any [mscorlib]System.Boolean
0x81290  brtrue   loc_813B3
0x81295  ldarg.1
0x81296  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x8129b  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x812a0  brfalse.s loc_812CD
0x812a2  ldc.i4.2
0x812a3  ldarg.1
0x812a4  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x812a9  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x812ae  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailDeliveryMethod
0x812b3  beq.s    loc_812CA
0x812b5  ldc.i4.3
0x812b6  ldarg.1
0x812b7  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x812bc  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x812c1  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailDeliveryMethod
0x812c6  ceq
0x812c8  br.s     loc_812CE
0x812ca  ldc.i4.1
0x812cb  br.s     loc_812CE
0x812cd  ldc.i4.0
0x812ce  stloc.0
0x812cf  ldarg.1
0x812d0  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x812d5  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x812da  brfalse.s loc_812F1
0x812dc  ldc.i4.2
0x812dd  ldarg.1
0x812de  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x812e3  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x812e8  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailDeliveryMethod
0x812ed  ceq
0x812ef  br.s     loc_812F2
0x812f1  ldc.i4.0
0x812f2  stloc.1
0x812f3  ldloc.0
0x812f4  ldloc.1
0x812f5  or
0x812f6  brfalse  loc_813B3
0x812fb  ldarg.1
0x812fc  ldstr    aEmailserverpro// "emailserverprofile"
0x81301  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x81306  brfalse  loc_813B3
0x8130b  ldarg.3
0x8130c  ldind.ref
0x8130d  brtrue.s loc_8133C
0x8130f  ldarg.3
0x81310  ldarg.0
0x81311  ldarg.1
0x81312  ldstr    aEmailserverpro// "emailserverprofile"
0x81317  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x8131c  castclass Microsoft.Crm.Application.Types.LookupValue
0x81321  callvirt instance string Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x81326  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x8132b  ldarg.1
0x8132c  callvirt instance class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x81331  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x81336  call     instance class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.MailboxNotificationGenerator::RetrieveRefrencedEmailProfile(valuetype [mscorlib]System.Guid emailprofileId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x8133b  stind.ref
0x8133c  ldarg.3
0x8133d  ldind.ref
0x8133e  brfalse.s loc_813B3
0x81340  ldarg.3
0x81341  ldind.ref
0x81342  ldstr    aIncomingcreden// "incomingcredentialretrieval"
0x81347  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x8134c  brfalse.s loc_81364
0x8134e  ldc.i4.2
0x8134f  ldarg.3
0x81350  ldind.ref
0x81351  ldstr    aIncomingcreden// "incomingcredentialretrieval"
0x81356  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x8135b  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CredentialRetrievalMethod
0x81360  ceq
0x81362  br.s     loc_81365
0x81364  ldc.i4.0
0x81365  stloc.2
0x81366  ldarg.3
0x81367  ldind.ref
0x81368  ldstr    aOutgoingcreden// "outgoingcredentialretrieval"
0x8136d  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x81372  brfalse.s loc_8138A
0x81374  ldc.i4.2
0x81375  ldarg.3
0x81376  ldind.ref
0x81377  ldstr    aOutgoingcreden// "outgoingcredentialretrieval"
0x8137c  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x81381  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CredentialRetrievalMethod
0x81386  ceq
0x81388  br.s     loc_8138B
0x8138a  ldc.i4.0
0x8138b  stloc.3
0x8138c  ldloc.0
0x8138d  ldloc.2
0x8138e  and
0x8138f  brtrue.s loc_81396
0x81391  ldloc.1
0x81392  ldloc.3
0x81393  and
0x81394  brfalse.s loc_813B3
0x81396  ldarg.2
0x81397  ldc.i4.2
0x81398  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8139d  ldstr    aWebEmailEmails// "Web.Email.EmailServerProfile.Notificati"...
0x813a2  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x813a7  call     class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::CreateNotification(int32, string)
0x813ac  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x813b1  ldc.i4.1
0x813b2  ret
0x813b3  ldc.i4.0
0x813b4  ret
```
