# Microsoft.Crm.Sdk.CrmServiceSoapExtensionReflector::OnMetadataChange

- ea: `0xa380`
- end: `0xa3ed`
- name: `Microsoft.Crm.Sdk.CrmServiceSoapExtensionReflector::OnMetadataChange`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x85f0`
- `0xa380`
- `0xd6f0`

## pseudocode

```c

```

## disassembly

```asm
0xa380  ldarg.0
0xa381  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_OrganizationId()
0xa386  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa38b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa390  brfalse.s loc_A3C8
0xa392  call     class Microsoft.Crm.Sdk.ServiceDescriptionCache Microsoft.Crm.Sdk.ServiceDescriptionCache::get_Instance()
0xa397  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContextFactory::get_Current()
0xa39c  ldarg.0
0xa39d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_OrganizationId()
0xa3a2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory::GetOrganizationContext(valuetype [mscorlib]System.Guid)
0xa3a7  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class Microsoft.Crm.Sdk.ServiceDescription>::FlushNoNotification(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa3ac  call     class Microsoft.Crm.WebServices.AspNetServiceDescriptionCache Microsoft.Crm.WebServices.AspNetServiceDescriptionCache::get_Instance()
0xa3b1  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContextFactory::get_Current()
0xa3b6  ldarg.0
0xa3b7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_OrganizationId()
0xa3bc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory::GetOrganizationContext(valuetype [mscorlib]System.Guid)
0xa3c1  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class Microsoft.Crm.WebServices.AspNetServiceDescriptionCacheKey, class [System.Web.Services]System.Web.Services.Description.ServiceDescription>::FlushNoNotification(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa3c6  br.s     loc_A3E6
0xa3c8  call     class Microsoft.Crm.Sdk.ServiceDescriptionCache Microsoft.Crm.Sdk.ServiceDescriptionCache::get_Instance()
0xa3cd  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Metadata.DummyOrganizationContext::.ctor()
0xa3d2  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class Microsoft.Crm.Sdk.ServiceDescription>::FlushForAllOrganizationsNoNotification(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa3d7  call     class Microsoft.Crm.WebServices.AspNetServiceDescriptionCache Microsoft.Crm.WebServices.AspNetServiceDescriptionCache::get_Instance()
0xa3dc  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Metadata.DummyOrganizationContext::.ctor()
0xa3e1  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class Microsoft.Crm.WebServices.AspNetServiceDescriptionCacheKey, class [System.Web.Services]System.Web.Services.Description.ServiceDescription>::FlushForAllOrganizationsNoNotification(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa3e6  ldc.i4.0
0xa3e7  stsfld   int32 Microsoft.Crm.Sdk.CrmServiceSoapExtensionReflector::_callCount
0xa3ec  ret
```
