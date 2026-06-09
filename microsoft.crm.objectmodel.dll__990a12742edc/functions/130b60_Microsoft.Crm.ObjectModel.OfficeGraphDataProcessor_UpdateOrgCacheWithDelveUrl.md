# Microsoft.Crm.ObjectModel.OfficeGraphDataProcessor::UpdateOrgCacheWithDelveUrl

- ea: `0x130b60`
- end: `0x130c6c`
- name: `Microsoft.Crm.ObjectModel.OfficeGraphDataProcessor::UpdateOrgCacheWithDelveUrl`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x130a40`

## callees

- `0x130b10`
- `0x130b60`
- `0x130c70`
- `0x131310`
- `0x131320`

## string_xrefs

- `0x130b8a`: `UpdateOrgCacheWithDelveUrl`
- `0x130c03`: `UpdateOrgCacheWithDelveUrl`
- `0x130c31`: `UpdateOrgCacheWithDelveUrl`
- `0x130b95`: `OfficeGraphDataProcessor.UpdateOrgCacheWithDelveUrl`
- `0x130c0e`: `OfficeGraphDataProcessor.UpdateOrgCacheWithDelveUrl`
- `0x130c3c`: `OfficeGraphDataProcessor.UpdateOrgCacheWithDelveUrl`
- `0x130b9a`: `Delve url is already present in Org cache. Delve url : `
- `0x130bc0`: `Delve Url is not present in Organization cache, trying to retrieve it from SharePoint`
- `0x130c13`: `Delve url is not present in Org cache, retrieve it from SharePoint and update as Delve url : `

## pseudocode

```c

```

## disassembly

```asm
0x130b60  ldsfld   string [mscorlib]System.String::Empty
0x130b65  stloc.0
0x130b66  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x130b6b  ldarg.1
0x130b6c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x130b71  ldarg.1
0x130b72  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x130b77  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OfficeGraphDelveUrl()
0x130b7c  stloc.0
0x130b7d  ldloc.0
0x130b7e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x130b83  brtrue.s loc_130BAB
0x130b85  call     class Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource::get_Instance()
0x130b8a  ldstr    aUpdateorgcache// "UpdateOrgCacheWithDelveUrl"
0x130b8f  ldarg.1
0x130b90  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x130b95  ldstr    aOfficegraphdat_0// "OfficeGraphDataProcessor.UpdateOrgCache"...
0x130b9a  ldstr    aDelveUrlIsAlre// "Delve url is already present in Org cac"...
0x130b9f  ldloc.0
0x130ba0  call     string [mscorlib]System.String::Concat(string, string)
0x130ba5  callvirt instance void Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource::LogInformation(string EventName, valuetype [mscorlib]System.Guid organizationId, string CallingMethod, string EventDetails)
0x130baa  ret
0x130bab  ldarg.1
0x130bac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x130bb1  ldc.i4.s 0x11
0x130bb3  ldstr    a0_0// "{0}"
0x130bb8  ldc.i4.1
0x130bb9  newarr   [mscorlib]System.Object
0x130bbe  dup
0x130bbf  ldc.i4.0
0x130bc0  ldstr    aDelveUrlIsNotP// "Delve Url is not present in Organizatio"...
0x130bc5  stelem.ref
0x130bc6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x130bcb  ldarg.0
0x130bcc  ldarg.1
0x130bcd  call     instance string Microsoft.Crm.ObjectModel.OfficeGraphDataProcessor::GetOneDriveMainSite(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x130bd2  stloc.0
0x130bd3  ldloc.0
0x130bd4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x130bd9  brtrue.s loc_130C2C
0x130bdb  ldloc.0
0x130bdc  newobj   instance void [System]System.Uri::.ctor(string)
0x130be1  stloc.1
0x130be2  ldloc.1
0x130be3  callvirt instance string [System]System.Uri::get_Scheme()
0x130be8  ldstr    asc_2B0E52// "://"
0x130bed  ldloc.1
0x130bee  callvirt instance string [System]System.Uri::get_Authority()
0x130bf3  ldstr    aLayouts15MeAsp// "/_layouts/15/me.aspx"
0x130bf8  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x130bfd  stloc.0
0x130bfe  call     class Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource::get_Instance()
0x130c03  ldstr    aUpdateorgcache// "UpdateOrgCacheWithDelveUrl"
0x130c08  ldarg.1
0x130c09  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x130c0e  ldstr    aOfficegraphdat_0// "OfficeGraphDataProcessor.UpdateOrgCache"...
0x130c13  ldstr    aDelveUrlIsNotP_0// "Delve url is not present in Org cache, "...
0x130c18  ldloc.0
0x130c19  call     string [mscorlib]System.String::Concat(string, string)
0x130c1e  callvirt instance void Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource::LogInformation(string EventName, valuetype [mscorlib]System.Guid organizationId, string CallingMethod, string EventDetails)
0x130c23  ldarg.0
0x130c24  ldloc.0
0x130c25  ldarg.1
0x130c26  call     instance void Microsoft.Crm.ObjectModel.OfficeGraphDataProcessor::UpdateDelveUrlToOrgCache(string delveUrl, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x130c2b  ret
0x130c2c  call     class Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource::get_Instance()
0x130c31  ldstr    aUpdateorgcache// "UpdateOrgCacheWithDelveUrl"
0x130c36  ldarg.1
0x130c37  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x130c3c  ldstr    aOfficegraphdat_0// "OfficeGraphDataProcessor.UpdateOrgCache"...
0x130c41  ldstr    aThePersonalSit// "The personal site returned by GetOneDri"...
0x130c46  callvirt instance void Microsoft.Crm.ObjectModel.OfficeGraphDocumentEventSource::LogInformation(string EventName, valuetype [mscorlib]System.Guid organizationId, string CallingMethod, string EventDetails)
0x130c4b  ldarg.1
0x130c4c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x130c51  ldc.i4.s 0x11
0x130c53  ldstr    a0_0// "{0}"
0x130c58  ldc.i4.1
0x130c59  newarr   [mscorlib]System.Object
0x130c5e  dup
0x130c5f  ldc.i4.0
0x130c60  ldstr    aThePersonalSit// "The personal site returned by GetOneDri"...
0x130c65  stelem.ref
0x130c66  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x130c6b  ret
```
