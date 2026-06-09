# Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::CheckIfServerVersionIsDifferent

- ea: `0x50700`
- end: `0x507dd`
- name: `Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::CheckIfServerVersionIsDifferent`
- size: `221`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x4e9c0`
- `0x503a0`

## callees

- `0x49670`
- `0x50700`
- `0x52340`
- `0x523d0`

## string_xrefs

- `0x5070f`: `ASP_BEGIN_MDCACHE_CHECKVERSIONWS`
- `0x50794`: `ASP_END_MDCACHE_CHECKVERSIONWS`

## pseudocode

```c

```

## disassembly

```asm
0x50700  ldstr    aCheckifserverv// "CheckIfServerVersionIsDifferent"
0x50705  ldarg.2
0x50706  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList parentCounter)
0x5070b  dup
0x5070c  starg.s  2
0x5070e  stloc.0
0x5070f  ldstr    aAspBeginMdcach_1// "ASP_BEGIN_MDCACHE_CHECKVERSIONWS"
0x50714  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x50719  ldarg.1
0x5071a  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Crm.Metadata.Helpers::CreateOrganizationService(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x5071f  stloc.1
0x50720  ldstr    aRetrievetimest// "RetrieveTimestamp"
0x50725  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor(string)
0x5072a  stloc.2
0x5072b  ldloc.1
0x5072c  ldloc.2
0x5072d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x50732  ldstr    aTimestamp_1// "Timestamp"
0x50737  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Item(string)
0x5073c  castclass [mscorlib]System.String
0x50741  ldarg.0
0x50742  callvirt instance string Microsoft.Crm.Metadata.DynamicMetadataCache::get_TimeStamp()
0x50747  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5074c  stloc.3
0x5074d  ldloc.3
0x5074e  brfalse.s loc_50773
0x50750  ldarg.1
0x50751  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x50756  ldc.i4.s 0x19
0x50758  ldstr    aClientVersion0// "Client Version = {0} is different from "...
0x5075d  ldc.i4.1
0x5075e  newarr   [mscorlib]System.Object
0x50763  dup
0x50764  ldc.i4.0
0x50765  ldarg.0
0x50766  callvirt instance string Microsoft.Crm.Metadata.DynamicMetadataCache::get_TimeStamp()
0x5076b  stelem.ref
0x5076c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x50771  br.s     loc_50794
0x50773  ldarg.1
0x50774  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x50779  ldc.i4.s 0x19
0x5077b  ldstr    aClientVersion0_0// "Client Version = {0} is same as Server "...
0x50780  ldc.i4.1
0x50781  newarr   [mscorlib]System.Object
0x50786  dup
0x50787  ldc.i4.0
0x50788  ldarg.0
0x50789  callvirt instance string Microsoft.Crm.Metadata.DynamicMetadataCache::get_TimeStamp()
0x5078e  stelem.ref
0x5078f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x50794  ldstr    aAspEndMdcacheC// "ASP_END_MDCACHE_CHECKVERSIONWS"
0x50799  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x5079e  ldloc.3
0x5079f  stloc.s  4
0x507a1  leave.s  loc_507DA
0x507a3  ldloc.1
0x507a4  brfalse.s loc_507AC
0x507a6  ldloc.1
0x507a7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x507ac  endfinally
0x507ad  stloc.s  5
0x507af  ldloc.s  5
0x507b1  ldarg.1
0x507b2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x507b7  ldc.i4.s 0x19
0x507b9  ldstr    aCheckifserverv_0// "CheckIfServerVersionIsDifferent() got e"...
0x507be  ldc.i4.1
0x507bf  newarr   [mscorlib]System.Object
0x507c4  dup
0x507c5  ldc.i4.0
0x507c6  ldloc.s  5
0x507c8  stelem.ref
0x507c9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x507ce  rethrow
0x507d0  ldloc.0
0x507d1  brfalse.s loc_507D9
0x507d3  ldloc.0
0x507d4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x507d9  endfinally
0x507da  ldloc.s  4
0x507dc  ret
```
