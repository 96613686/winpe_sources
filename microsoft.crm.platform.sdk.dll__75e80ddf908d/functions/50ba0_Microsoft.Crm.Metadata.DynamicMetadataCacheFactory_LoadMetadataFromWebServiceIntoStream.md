# Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadMetadataFromWebServiceIntoStream

- ea: `0x50ba0`
- end: `0x50ca6`
- name: `Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadMetadataFromWebServiceIntoStream`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x509a0`

## callees

- `0x50ba0`
- `0x52340`
- `0x523d0`

## string_xrefs

- `0x50ba8`: `Loading metadata for web service for rich client for organization {0}`
- `0x50bc6`: `ASP_BEGIN_MDCACHE_GETRC_METADATA_WS`
- `0x50bd7`: `DisableMetadataCompression`
- `0x50bf0`: `LoadMetadataFromWebServiceIntoStream = compressData=`
- `0x50c81`: `LoadMetadataFromWebServiceIntoStream() got exception: {0}`
- `0x50c98`: `ASP_END_MDCACHE_GETRC_METADATA_WS`

## pseudocode

```c

```

## disassembly

```asm
0x50ba0  ldarg.0
0x50ba1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x50ba6  ldc.i4.s 0x19
0x50ba8  ldstr    aLoadingMetadat_3// "Loading metadata for web service for ri"...
0x50bad  ldc.i4.1
0x50bae  newarr   [mscorlib]System.Object
0x50bb3  dup
0x50bb4  ldc.i4.0
0x50bb5  ldarg.0
0x50bb6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x50bbb  box      [mscorlib]System.Guid
0x50bc0  stelem.ref
0x50bc1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x50bc6  ldstr    aAspBeginMdcach_3// "ASP_BEGIN_MDCACHE_GETRC_METADATA_WS"
0x50bcb  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x50bd0  ldarg.0
0x50bd1  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Crm.Metadata.Helpers::CreateOrganizationService(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x50bd6  stloc.0
0x50bd7  ldstr    aDisablemetadat// "DisableMetadataCompression"
0x50bdc  ldc.i4.0
0x50bdd  box      [mscorlib]System.Int32
0x50be2  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x50be7  unbox.any [mscorlib]System.Int32
0x50bec  ldc.i4.0
0x50bed  ceq
0x50bef  stloc.1
0x50bf0  ldstr    aLoadmetadatafr// "LoadMetadataFromWebServiceIntoStream = "...
0x50bf5  ldloca.s 1
0x50bf7  call     instance string [mscorlib]System.Boolean::ToString()
0x50bfc  call     string [mscorlib]System.String::Concat(string, string)
0x50c01  ldarg.1
0x50c02  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList parentCounter)
0x50c07  dup
0x50c08  starg.s  1
0x50c0a  stloc.2
0x50c0b  ldstr    aRetrievemetada// "RetrieveMetadataForRichClient SDK call"
0x50c10  ldarg.1
0x50c11  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList parentCounter)
0x50c16  stloc.s  4
0x50c18  ldstr    aRetrievemetada_0// "RetrieveMetadataForRichClient"
0x50c1d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor(string)
0x50c22  stloc.s  5
0x50c24  ldloc.0
0x50c25  ldloc.s  5
0x50c27  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x50c2c  ldstr    aMetadata_0// "Metadata"
0x50c31  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Item(string)
0x50c36  castclass unsigned int8[]
0x50c3b  stloc.3
0x50c3c  leave.s  loc_50C4A
0x50c3e  ldloc.s  4
0x50c40  brfalse.s loc_50C49
0x50c42  ldloc.s  4
0x50c44  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x50c49  endfinally
0x50c4a  ldloc.1
0x50c4b  brfalse.s loc_50C57
0x50c4d  ldloc.3
0x50c4e  call     class [mscorlib]System.IO.Stream [Microsoft.Crm]Microsoft.Crm.CrmCompress::GetDecompressionStream(unsigned int8[])
0x50c53  stloc.s  6
0x50c55  leave.s  loc_50CA3
0x50c57  ldloc.3
0x50c58  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x50c5d  stloc.s  6
0x50c5f  leave.s  loc_50CA3
0x50c61  ldloc.2
0x50c62  brfalse.s loc_50C6A
0x50c64  ldloc.2
0x50c65  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x50c6a  endfinally
0x50c6b  ldloc.0
0x50c6c  brfalse.s loc_50C74
0x50c6e  ldloc.0
0x50c6f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x50c74  endfinally
0x50c75  stloc.s  7
0x50c77  ldloc.s  7
0x50c79  ldarg.0
0x50c7a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x50c7f  ldc.i4.s 0x19
0x50c81  ldstr    aLoadmetadatafr_0// "LoadMetadataFromWebServiceIntoStream() "...
0x50c86  ldc.i4.1
0x50c87  newarr   [mscorlib]System.Object
0x50c8c  dup
0x50c8d  ldc.i4.0
0x50c8e  ldloc.s  7
0x50c90  stelem.ref
0x50c91  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x50c96  rethrow
0x50c98  ldstr    aAspEndMdcacheG// "ASP_END_MDCACHE_GETRC_METADATA_WS"
0x50c9d  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x50ca2  endfinally
0x50ca3  ldloc.s  6
0x50ca5  ret
```
