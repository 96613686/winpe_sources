# Microsoft.Crm.Application.MasterSiteMap::LoadMasterSiteMapInternal

- ea: `0x240a0`
- end: `0x241b4`
- name: `Microsoft.Crm.Application.MasterSiteMap::LoadMasterSiteMapInternal`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x24060`

## callees

- `0x23a30`
- `0x23a50`
- `0x23ab0`
- `0x24080`
- `0x240a0`
- `0x241c0`
- `0x24280`
- `0x242c0`
- `0x47920`
- `0x47940`
- `0x5bb40`
- `0x5be20`

## string_xrefs

- `0x240d9`: `sitemapxml`
- `0x2412d`: `sitemapxml`
- `0x24111`: `SitemapId {0}: SitemapXml{1}`

## pseudocode

```c

```

## disassembly

```asm
0x240a0  ldstr    aLoadmastersite// "LoadMasterSiteMap"
0x240a5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::.ctor(string)
0x240aa  stloc.0
0x240ab  ldloc.0
0x240ac  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Start()
0x240b1  ldc.i4.0
0x240b2  ldarg.1
0x240b3  ldarg.2
0x240b4  ldarg.3
0x240b5  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.MasterSiteMap::RetrieveSiteMap(bool useReferenceXml, bool retrieveLatest, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, bool isAppModuleDataRequired)
0x240ba  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.MasterSiteMap>::.ctor()
0x240bf  stloc.1
0x240c0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x240c5  stloc.2
0x240c6  br       loc_24195
0x240cb  ldloc.2
0x240cc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x240d1  stloc.3
0x240d2  ldnull
0x240d3  stloc.s  4
0x240d5  ldc.i4.0
0x240d6  stloc.s  5
0x240d8  ldloc.3
0x240d9  ldstr    aSitemapxml// "sitemapxml"
0x240de  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x240e3  castclass [mscorlib]System.String
0x240e8  ldarg.0
0x240e9  ldarg.2
0x240ea  call     class Microsoft.Crm.Application.MasterSiteMap Microsoft.Crm.Application.MasterSiteMap::ValidateSiteMapXml(string siteMapXml, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache metadataCache, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x240ef  stloc.s  4
0x240f1  leave.s  loc_24158
0x240f3  stloc.s  6
0x240f5  ldloc.s  6
0x240f7  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x240fc  ldc.i4   0x8063110E
0x24101  beq.s    loc_24105
0x24103  rethrow
0x24105  ldloc.s  6
0x24107  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x2410c  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x24111  ldstr    aSitemapid0Site// "SitemapId {0}: SitemapXml{1}"
0x24116  ldc.i4.2
0x24117  newarr   [mscorlib]System.Object
0x2411c  dup
0x2411d  ldc.i4.0
0x2411e  ldloc.3
0x2411f  ldstr    aSitemapid// "sitemapid"
0x24124  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x24129  stelem.ref
0x2412a  dup
0x2412b  ldc.i4.1
0x2412c  ldloc.3
0x2412d  ldstr    aSitemapxml// "sitemapxml"
0x24132  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x24137  stelem.ref
0x24138  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2413d  ldc.i4.1
0x2413e  stloc.s  5
0x24140  leave.s  loc_24158
0x24142  ldloc.s  5
0x24144  brfalse.s loc_24157
0x24146  ldarg.0
0x24147  ldarg.2
0x24148  call     class Microsoft.Crm.Application.MasterSiteMap Microsoft.Crm.Application.MasterSiteMap::GetReferenceSiteMap(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache metadataCache, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2414d  stloc.s  4
0x2414f  ldloc.s  4
0x24151  ldc.i4.1
0x24152  callvirt instance void Microsoft.Crm.Application.SiteMap::set_IsFromReferenceXml(bool value)
0x24157  endfinally
0x24158  ldloc.s  4
0x2415a  brfalse.s loc_24195
0x2415c  ldloc.s  4
0x2415e  ldloc.3
0x2415f  callvirt instance string Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x24164  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x24169  callvirt instance void Microsoft.Crm.Application.SiteMap::set_SiteMapId(valuetype [mscorlib]System.Guid value)
0x2416e  ldarg.2
0x2416f  call     bool Microsoft.Crm.Application.MasterSiteMap::IsAppAwareExists(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x24174  brfalse.s loc_2418D
0x24176  ldloc.s  4
0x24178  ldloc.3
0x24179  ldstr    aIsappaware// "isappaware"
0x2417e  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x24183  unbox.any [mscorlib]System.Boolean
0x24188  callvirt instance void Microsoft.Crm.Application.SiteMap::set_IsAppAware(bool value)
0x2418d  ldloc.1
0x2418e  ldloc.s  4
0x24190  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.MasterSiteMap>::Add(var<u1>)
0x24195  ldloc.2
0x24196  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2419b  brtrue   loc_240CB
0x241a0  leave.s  loc_241AC
0x241a2  ldloc.2
0x241a3  brfalse.s loc_241AB
0x241a5  ldloc.2
0x241a6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x241ab  endfinally
0x241ac  ldloc.0
0x241ad  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Stop()
0x241b2  ldloc.1
0x241b3  ret
```
