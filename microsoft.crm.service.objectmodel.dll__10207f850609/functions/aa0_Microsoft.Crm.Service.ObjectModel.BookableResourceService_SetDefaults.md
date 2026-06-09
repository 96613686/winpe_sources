# Microsoft.Crm.Service.ObjectModel.BookableResourceService::SetDefaults

- ea: `0xaa0`
- end: `0xb28`
- name: `Microsoft.Crm.Service.ObjectModel.BookableResourceService::SetDefaults`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a0`

## callees

- `0xaa0`
- `0xb30`
- `0xc80`
- `0xd20`
- `0xdc0`

## pseudocode

```c

```

## disassembly

```asm
0xaa0  ldarg.1
0xaa1  ldstr    aResourcetype// "resourcetype"
0xaa6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xaab  unbox.any ResourceTypes
0xab0  stloc.0
0xab1  ldloc.0
0xab2  ldc.i4.2
0xab3  sub
0xab4  switch   loc_AD5, loc_ACB, loc_AE9, loc_ADF
0xac9  br.s     loc_AE9
0xacb  ldarg.0
0xacc  ldarg.1
0xacd  ldarg.2
0xace  call     instance void Microsoft.Crm.Service.ObjectModel.BookableResourceService::InitializeResourceFromUser(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.BookableResource bookableResource, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xad3  br.s     loc_B0D
0xad5  ldarg.0
0xad6  ldarg.1
0xad7  ldarg.2
0xad8  call     instance void Microsoft.Crm.Service.ObjectModel.BookableResourceService::InitializeResourceFromContact(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.BookableResource bookableResource, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xadd  br.s     loc_B0D
0xadf  ldarg.0
0xae0  ldarg.1
0xae1  ldarg.2
0xae2  call     instance void Microsoft.Crm.Service.ObjectModel.BookableResourceService::InitializeResourceFromAccount(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.BookableResource bookableResource, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xae7  br.s     loc_B0D
0xae9  ldarg.1
0xaea  ldstr    aAccountid// "accountid"
0xaef  ldnull
0xaf0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xaf5  ldarg.1
0xaf6  ldstr    aUserid// "userid"
0xafb  ldnull
0xafc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xb01  ldarg.1
0xb02  ldstr    aContactid// "contactid"
0xb07  ldnull
0xb08  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xb0d  ldarg.1
0xb0e  ldstr    aCalendarid// "calendarid"
0xb13  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0xb18  brfalse.s loc_B27
0xb1a  ldloc.0
0xb1b  ldc.i4.3
0xb1c  beq.s    loc_B27
0xb1e  ldarg.0
0xb1f  ldarg.1
0xb20  ldarg.2
0xb21  ldloc.0
0xb22  call     instance void Microsoft.Crm.Service.ObjectModel.BookableResourceService::CreateDefaultCalendar(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.BookableResource bookableResource, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype ResourceTypes resourceType)
0xb27  ret
```
