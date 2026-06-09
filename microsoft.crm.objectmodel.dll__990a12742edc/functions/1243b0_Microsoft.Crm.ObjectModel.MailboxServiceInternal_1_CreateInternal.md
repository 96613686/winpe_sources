# Microsoft.Crm.ObjectModel.MailboxServiceInternal`1::CreateInternal

- ea: `0x1243b0`
- end: `0x1244a8`
- name: `Microsoft.Crm.ObjectModel.MailboxServiceInternal`1::CreateInternal`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1243b0`

## string_xrefs

- `0x12442a`: `incomingemaildeliverymethod`
- `0x124437`: `incomingemaildeliverymethod`
- `0x1243b1`: `testemailconfigurationscheduled`
- `0x1243be`: `testemailconfigurationscheduled`
- `0x1243ee`: `postponetestemailconfigurationuntil`
- `0x1243fb`: `postponetestemailconfigurationuntil`
- `0x1243d0`: `testemailconfigurationretrycount`
- `0x1243dd`: `testemailconfigurationretrycount`
- `0x124487`: `Setting PostponeMailboxProcessingUntil as DateTime.Max in case the mailbox is not active or not configured for any processing during creation of the mailbox.`

## pseudocode

```c

```

## disassembly

```asm
0x1243b0  ldarg.1
0x1243b1  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x1243b6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1243bb  brtrue.s loc_12440A
0x1243bd  ldarg.1
0x1243be  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x1243c3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1243c8  unbox.any [mscorlib]System.Boolean
0x1243cd  brfalse.s loc_12440A
0x1243cf  ldarg.1
0x1243d0  ldstr    aTestemailconfi_0// "testemailconfigurationretrycount"
0x1243d5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1243da  brfalse.s loc_1243ED
0x1243dc  ldarg.1
0x1243dd  ldstr    aTestemailconfi_0// "testemailconfigurationretrycount"
0x1243e2  ldc.i4.1
0x1243e3  box      [mscorlib]System.Int32
0x1243e8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1243ed  ldarg.1
0x1243ee  ldstr    aPostponetestem// "postponetestemailconfigurationuntil"
0x1243f3  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1243f8  brfalse.s loc_12440A
0x1243fa  ldarg.1
0x1243fb  ldstr    aPostponetestem// "postponetestemailconfigurationuntil"
0x124400  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalNow()
0x124405  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x12440a  ldarg.1
0x12440b  ldstr    aStatecode// "statecode"
0x124410  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x124415  brtrue.s loc_124429
0x124417  ldarg.1
0x124418  ldstr    aStatecode// "statecode"
0x12441d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x124422  unbox.any [mscorlib]System.Int32
0x124427  brtrue.s loc_124469
0x124429  ldarg.1
0x12442a  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x12442f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x124434  brtrue.s loc_124497
0x124436  ldarg.1
0x124437  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x12443c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x124441  unbox.any [mscorlib]System.Int32
0x124446  ldc.i4.2
0x124447  beq.s    loc_124497
0x124449  ldarg.1
0x12444a  ldstr    aActdeliverymet// "actdeliverymethod"
0x12444f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x124454  brtrue.s loc_124497
0x124456  ldarg.1
0x124457  ldstr    aActdeliverymet// "actdeliverymethod"
0x12445c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x124461  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ACTDeliveryMethod
0x124466  ldc.i4.1
0x124467  beq.s    loc_124497
0x124469  ldarg.1
0x12446a  ldstr    aPostponemailbo// "postponemailboxprocessinguntil"
0x12446f  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::MaxValue
0x124474  ldc.i4.1
0x124475  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x12447a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x12447f  ldarg.2
0x124480  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x124485  ldc.i4.s 0x11
0x124487  ldstr    aSettingPostpon// "Setting PostponeMailboxProcessingUntil "...
0x12448c  ldc.i4.0
0x12448d  newarr   [mscorlib]System.Object
0x124492  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x124497  ldarg.0
0x124498  ldarg.1
0x124499  ldarg.2
0x12449a  call     instance void class Microsoft.Crm.ObjectModel.MailboxServiceInternal`1<var<u1>>::UpdateACTDeliveryMethodIfNeeded(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x12449f  ldarg.0
0x1244a0  ldarg.1
0x1244a1  ldarg.2
0x1244a2  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker class Microsoft.Crm.ObjectModel.ProvisionedEntity`1<var<u1>>::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1244a7  ret
```
