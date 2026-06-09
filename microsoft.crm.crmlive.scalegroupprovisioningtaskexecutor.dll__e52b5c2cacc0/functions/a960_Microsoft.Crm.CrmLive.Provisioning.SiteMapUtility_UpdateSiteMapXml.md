# Microsoft.Crm.CrmLive.Provisioning.SiteMapUtility::UpdateSiteMapXml

- ea: `0xa960`
- end: `0xa9f2`
- name: `Microsoft.Crm.CrmLive.Provisioning.SiteMapUtility::UpdateSiteMapXml`
- size: `146`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x8380`
- `0xa810`

## callees

- `0xa960`

## string_xrefs

- `0xa97f`: `sitemapxml`

## pseudocode

```c

```

## disassembly

```asm
0xa960  ldarg.0
0xa961  ldstr    aOrganizationid// "organizationId"
0xa966  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xa96b  ldstr    aSitemap// "SiteMap"
0xa970  ldarg.0
0xa971  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, valuetype [mscorlib]System.Guid)
0xa976  stloc.0
0xa977  ldarg.0
0xa978  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SiteMap::.ctor(valuetype [mscorlib]System.Guid)
0xa97d  stloc.1
0xa97e  ldloc.1
0xa97f  ldstr    aSitemapxml// "sitemapxml"
0xa984  ldarg.1
0xa985  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xa98a  ldloc.1
0xa98b  ldstr    aSitemapid// "sitemapid"
0xa990  ldarg.0
0xa991  ldstr    aSitemapid// "sitemapid"
0xa996  call     T0x2B000030
0xa99b  box      [mscorlib]System.Guid
0xa9a0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xa9a5  ldarg.0
0xa9a6  ldc.i4.0
0xa9a7  ldc.i4.0
0xa9a8  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xa9ad  stloc.2
0xa9ae  ldloc.2
0xa9af  ldc.i4.0
0xa9b0  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemExecutionOperationContext::.ctor()
0xa9b5  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionOperationContext)
0xa9ba  ldloc.2
0xa9bb  ldc.i4.0
0xa9bc  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0xa9c1  stloc.3
0xa9c2  ldloc.0
0xa9c3  ldloc.1
0xa9c4  ldloc.2
0xa9c5  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xa9ca  leave.s  loc_A9D6
0xa9cc  ldloc.3
0xa9cd  brfalse.s loc_A9D5
0xa9cf  ldloc.3
0xa9d0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa9d5  endfinally
0xa9d6  ldloc.2
0xa9d7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0xa9dc  leave.s  loc_A9F1
0xa9de  pop
0xa9df  ldloc.2
0xa9e0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0xa9e5  rethrow
0xa9e7  ldloc.2
0xa9e8  brfalse.s loc_A9F0
0xa9ea  ldloc.2
0xa9eb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa9f0  endfinally
0xa9f1  ret
```
