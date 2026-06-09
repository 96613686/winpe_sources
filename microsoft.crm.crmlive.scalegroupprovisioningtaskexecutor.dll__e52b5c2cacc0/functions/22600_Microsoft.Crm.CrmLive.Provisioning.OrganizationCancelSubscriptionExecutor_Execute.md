# Microsoft.Crm.CrmLive.Provisioning.OrganizationCancelSubscriptionExecutor::Execute

- ea: `0x22600`
- end: `0x22706`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationCancelSubscriptionExecutor::Execute`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x21460`
- `0x22600`

## string_xrefs

- `0x22622`: `PlatformSharedServiceURL`
- `0x22679`: `CrmProvisioningService`

## pseudocode

```c

```

## disassembly

```asm
0x22600  ldarg.1
0x22601  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x22606  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x2260b  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Services.OrganizationCancelSubscriptionInfo [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Services.OrganizationCancelSubscriptionInfo::Deserialize(string)
0x22610  stloc.0
0x22611  ldloc.0
0x22612  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.Services.BillingContext [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Services.OrganizationCancelSubscriptionInfo::get_BillingContext()
0x22617  call     class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.ClientOfferConversion.BillingContext Microsoft.Crm.CrmLive.Provisioning.SubscriptionActionUtility::Convert(class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.Services.BillingContext billingContext)
0x2261c  stloc.1
0x2261d  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x22622  ldstr    aPlatformshared// "PlatformSharedServiceURL"
0x22627  ldc.i4.0
0x22628  callvirt T0x2B000011
0x2262d  newobj   instance void [System]System.Uri::.ctor(string)
0x22632  call     class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::ConnectOfferConversion(class [System]System.Uri)
0x22637  stloc.2
0x22638  ldloc.2
0x22639  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.ClientOfferConversion.OfferConversionWsdl [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::get_OfferConversionService()
0x2263e  ldloc.1
0x2263f  ldloc.0
0x22640  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Services.OrganizationCancelSubscriptionInfo::get_SubscriptionId()
0x22645  ldloc.0
0x22646  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Services.OrganizationCancelSubscriptionInfo::get_TrackingId()
0x2264b  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.ClientOfferConversion.OfferConversionWsdl::CancelSubscription(class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.ClientOfferConversion.BillingContext, string, valuetype [mscorlib]System.Guid)
0x22650  leave.s  loc_2265C
0x22652  ldloc.2
0x22653  brfalse.s loc_2265B
0x22655  ldloc.2
0x22656  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2265b  endfinally
0x2265c  leave    loc_226F7
0x22661  stloc.3
0x22662  ldarg.1
0x22663  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x22668  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x2266d  ldc.i4.3
0x2266e  ble.s    loc_226D7
0x22670  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x22675  stloc.s  4
0x22677  ldloc.s  4
0x22679  ldstr    aCrmprovisionin// "CrmProvisioningService"
0x2267e  ldc.i4.1
0x2267f  ldc.i4   0xC0004633
0x22684  conv.u8
0x22685  ldc.i4.3
0x22686  newarr   [mscorlib]System.Object
0x2268b  dup
0x2268c  ldc.i4.0
0x2268d  ldarg.1
0x2268e  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x22693  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x22698  box      [mscorlib]System.Int32
0x2269d  stelem.ref
0x2269e  dup
0x2269f  ldc.i4.1
0x226a0  ldloc.0
0x226a1  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.Services.BillingContext [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Services.OrganizationCancelSubscriptionInfo::get_BillingContext()
0x226a6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.Services.BillingContext::get_OrganizationId()
0x226ab  box      [mscorlib]System.Guid
0x226b0  stelem.ref
0x226b1  dup
0x226b2  ldc.i4.2
0x226b3  ldarg.1
0x226b4  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x226b9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x226be  box      [mscorlib]System.Guid
0x226c3  stelem.ref
0x226c4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x226c9  leave.s  loc_226D7
0x226cb  ldloc.s  4
0x226cd  brfalse.s loc_226D6
0x226cf  ldloc.s  4
0x226d1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x226d6  endfinally
0x226d7  ldloc.3
0x226d8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x226dd  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x226e2  ldloc.3
0x226e3  ldarg.1
0x226e4  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x226e9  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x226ee  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::BuildRetry(string, class [mscorlib]System.Exception, int32)
0x226f3  stloc.s  5
0x226f5  leave.s  loc_22703
0x226f7  ldc.i4.4
0x226f8  ldstr    aSuccess// "success"
0x226fd  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x22702  ret
0x22703  ldloc.s  5
0x22705  ret
```
