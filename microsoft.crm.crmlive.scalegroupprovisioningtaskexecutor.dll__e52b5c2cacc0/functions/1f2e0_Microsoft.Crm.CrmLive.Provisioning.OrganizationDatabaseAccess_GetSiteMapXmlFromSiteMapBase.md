# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::GetSiteMapXmlFromSiteMapBase

- ea: `0x1f2e0`
- end: `0x1f38c`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::GetSiteMapXmlFromSiteMapBase`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1f2e0`

## string_xrefs

- `0x1f319`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\OrganizationDatabaseAccess.cs`
- `0x1f2eb`: `select SiteMapIdUnique, SiteMapXml from sitemapbase`
- `0x1f314`: `GetSiteMapXmlFromSiteMapBase`
- `0x1f329`: `SiteMapXml`

## pseudocode

```c

```

## disassembly

```asm
0x1f2e0  ldarg.1
0x1f2e1  ldstr    aOrganizationid// "organizationId"
0x1f2e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1f2eb  ldstr    aSelectSitemapi// "select SiteMapIdUnique, SiteMapXml from"...
0x1f2f0  stloc.0
0x1f2f1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::.ctor()
0x1f2f6  stloc.1
0x1f2f7  ldarg.1
0x1f2f8  ldc.i4.0
0x1f2f9  ldc.i4.0
0x1f2fa  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1f2ff  stloc.2
0x1f300  ldloc.2
0x1f301  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1f306  ldloc.2
0x1f307  ldloc.0
0x1f308  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x1f30d  stloc.3
0x1f30e  ldloc.3
0x1f30f  ldc.i4   0x9D8
0x1f314  ldstr    aGetsitemapxmlf// "GetSiteMapXmlFromSiteMapBase"
0x1f319  ldstr    aDDbsShDccm2110_31// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x1f31e  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x1f323  stloc.s  4
0x1f325  br.s     loc_1F357
0x1f327  ldloc.s  4
0x1f329  ldstr    aSitemapxml_0// "SiteMapXml"
0x1f32e  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1f333  castclass [mscorlib]System.String
0x1f338  stloc.s  5
0x1f33a  ldloc.s  4
0x1f33c  ldstr    aSitemapiduniqu// "SiteMapIdUnique"
0x1f341  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1f346  unbox.any [mscorlib]System.Guid
0x1f34b  stloc.s  6
0x1f34d  ldloc.1
0x1f34e  ldloc.s  6
0x1f350  ldloc.s  5
0x1f352  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::set_Item(var<u1>, !!T0)
0x1f357  ldloc.s  4
0x1f359  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x1f35e  brtrue.s loc_1F327
0x1f360  leave.s  loc_1F378
0x1f362  ldloc.s  4
0x1f364  brfalse.s loc_1F36D
0x1f366  ldloc.s  4
0x1f368  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f36d  endfinally
0x1f36e  ldloc.3
0x1f36f  brfalse.s loc_1F377
0x1f371  ldloc.3
0x1f372  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f377  endfinally
0x1f378  ldloc.2
0x1f379  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x1f37e  leave.s  loc_1F38A
0x1f380  ldloc.2
0x1f381  brfalse.s loc_1F389
0x1f383  ldloc.2
0x1f384  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f389  endfinally
0x1f38a  ldloc.1
0x1f38b  ret
```
