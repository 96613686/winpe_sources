# Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::.ctor

- ea: `0xe660`
- end: `0xe6d7`
- name: `Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::.ctor`
- size: `119`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xe970`
- `0xecc0`
- `0xf040`

## callees

- `0xe800`

## pseudocode

```c

```

## disassembly

```asm
0xe660  ldarg.0
0xe661  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::.ctor()
0xe666  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::_organizations
0xe66b  ldarg.0
0xe66c  call     instance void [mscorlib]System.Object::.ctor()
0xe671  ldarg.0
0xe672  ldarg.1
0xe673  stfld    class Microsoft.Crm.Asynchronous.ISharedQueueConfiguration Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::_sharedConfiguration
0xe678  ldarg.0
0xe679  ldarg.2
0xe67a  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::_locatorService
0xe67f  ldc.i4.s 0x16
0xe681  ldarg.0
0xe682  ldftn    instance void Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xe688  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xe68d  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xe692  ldc.i4.s 0x17
0xe694  ldarg.0
0xe695  ldftn    instance void Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xe69b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xe6a0  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xe6a5  ldc.i4.s 0x18
0xe6a7  ldarg.0
0xe6a8  ldftn    instance void Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xe6ae  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xe6b3  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xe6b8  ldarg.0
0xe6b9  ldfld    class Microsoft.Crm.Asynchronous.ISharedQueueConfiguration Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::_sharedConfiguration
0xe6be  ldarg.0
0xe6bf  ldftn    instance void Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::OnOrganizationsChanged(object sender, class [mscorlib]System.EventArgs args)
0xe6c5  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xe6ca  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationList::add_OrganizationsChanged(class [mscorlib]System.EventHandler)
0xe6cf  ldarg.0
0xe6d0  ldnull
0xe6d1  call     instance void Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::InitializeOrganizationList(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> inactiveOrganizations)
0xe6d6  ret
```
