# Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.EmailApprovalNotificationGenerator::AddNotificationIfNecessary

- ea: `0x82160`
- end: `0x82230`
- name: `Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.EmailApprovalNotificationGenerator::AddNotificationIfNecessary`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x11760`
- `0x30260`
- `0x5be20`
- `0x82120`
- `0x82160`

## string_xrefs

- `0x821ce`: `emailrouteraccessapproval`
- `0x821db`: `emailrouteraccessapproval`
- `0x8216d`: `incomingemaildeliverymethod`
- `0x8217a`: `incomingemaildeliverymethod`
- `0x8218d`: `incomingemaildeliverymethod`

## pseudocode

```c

```

## disassembly

```asm
0x82160  ldarg.0
0x82161  ldarg.1
0x82162  callvirt instance bool Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.EmailApprovalNotificationGenerator::CanAddNotification(class Microsoft.Crm.Application.Platform.Entity entity)
0x82167  brfalse  loc_8222F
0x8216c  ldarg.1
0x8216d  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x82172  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x82177  brfalse.s loc_821A4
0x82179  ldarg.1
0x8217a  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x8217f  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x82184  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailDeliveryMethod
0x82189  ldc.i4.2
0x8218a  beq.s    loc_821A1
0x8218c  ldarg.1
0x8218d  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x82192  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x82197  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailDeliveryMethod
0x8219c  ldc.i4.3
0x8219d  ceq
0x8219f  br.s     loc_821A5
0x821a1  ldc.i4.1
0x821a2  br.s     loc_821A5
0x821a4  ldc.i4.0
0x821a5  ldarg.1
0x821a6  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x821ab  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x821b0  brfalse.s loc_821C7
0x821b2  ldarg.1
0x821b3  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x821b8  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x821bd  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailDeliveryMethod
0x821c2  ldc.i4.2
0x821c3  ceq
0x821c5  br.s     loc_821C8
0x821c7  ldc.i4.0
0x821c8  stloc.0
0x821c9  ldloc.0
0x821ca  or
0x821cb  brfalse.s loc_8222F
0x821cd  ldarg.1
0x821ce  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x821d3  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x821d8  brfalse.s loc_8222F
0x821da  ldarg.1
0x821db  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x821e0  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x821e5  unbox.any [mscorlib]System.Int32
0x821ea  stloc.1
0x821eb  ldloc.1
0x821ec  ldc.i4.2
0x821ed  beq.s    loc_821F4
0x821ef  ldloc.1
0x821f0  ldc.i4.3
0x821f1  beq.s    loc_82212
0x821f3  ret
0x821f4  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x821f9  ldstr    aWebFormNotific// "Web.Form.Notification.PendingApproval"
0x821fe  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x82203  stloc.2
0x82204  ldarg.2
0x82205  ldc.i4.2
0x82206  ldloc.2
0x82207  call     class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::CreateNotification(int32, string)
0x8220c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x82211  ret
0x82212  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x82217  ldstr    aWebFormNotific_0// "Web.Form.Notification.Rejected"
0x8221c  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x82221  stloc.2
0x82222  ldarg.2
0x82223  ldc.i4.2
0x82224  ldloc.2
0x82225  call     class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::CreateNotification(int32, string)
0x8222a  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x8222f  ret
```
