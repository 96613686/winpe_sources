# Microsoft.Crm.Metadata.ClientMetadataService::AddUserContext

- ea: `0x2bad0`
- end: `0x2bc91`
- name: `Microsoft.Crm.Metadata.ClientMetadataService::AddUserContext`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x2b3d0`

## callees

- `0x2b870`
- `0x2b8c0`
- `0x2bad0`
- `0x2bca0`

## string_xrefs

- `0x2bb9a`: `quickcreatemenu`
- `0x2bc09`: `taskbasedflowglobalmenu`

## pseudocode

```c

```

## disassembly

```asm
0x2bad0  ldarg.2
0x2bad1  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery)
0x2bad6  ldc.i4.m1
0x2bad7  ldarg.3
0x2bad8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2badd  ldc.i4.m1
0x2bade  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.MetadataSyncEventReporter::.ctor(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext, int32, valuetype [mscorlib]System.Guid, int32)
0x2bae3  stloc.0
0x2bae4  ldloc.0
0x2bae5  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.MetadataServiceEventReporter::ReportAddUserContextStartEvent()
0x2baea  ldarg.2
0x2baeb  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery::get_AppId()
0x2baf0  stloc.2
0x2baf1  ldloca.s 2
0x2baf3  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x2baf8  brfalse  loc_2BC61
0x2bafd  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem>::.ctor()
0x2bb02  stloc.3
0x2bb03  ldarg.3
0x2bb04  call     int64 [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.UserMetadataVersionGenerator::GetUserMetadataVersion(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2bb09  stloc.s  0xD
0x2bb0b  ldloca.s 0xD
0x2bb0d  call     instance string [mscorlib]System.Int64::ToString()
0x2bb12  stloc.s  4
0x2bb14  ldarg.2
0x2bb15  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery::get_AppId()
0x2bb1a  stloc.s  5
0x2bb1c  ldstr    aAppmodules// "appmodules"
0x2bb21  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery Microsoft.Crm.Metadata.ClientMetadataService::GetUserContextSubQueryBase(string metadataType)
0x2bb26  stloc.s  6
0x2bb28  ldloc.s  6
0x2bb2a  ldloc.s  5
0x2bb2c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery::set_MetadataId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x2bb31  ldloc.s  6
0x2bb33  ldstr    aAppmodules// "appmodules"
0x2bb38  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery::set_MetadataName(string)
0x2bb3d  ldloc.s  6
0x2bb3f  ldloc.s  5
0x2bb41  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery::set_AppId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x2bb46  ldloc.3
0x2bb47  ldloc.s  6
0x2bb49  ldarg.3
0x2bb4a  call     void Microsoft.Crm.Metadata.ClientMetadataService::FindRootsForQueryAndCombine(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem> combinedRoots, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery clientMetadataQuery, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x2bb4f  ldstr    aEntity// "entity"
0x2bb54  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery Microsoft.Crm.Metadata.ClientMetadataService::GetUserContextSubQueryBase(string metadataType)
0x2bb59  stloc.s  7
0x2bb5b  ldloc.s  7
0x2bb5d  ldstr    aActivitypartyN// "{\"activityparty\":null}"
0x2bb62  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery::set_MetadataSubtype(string)
0x2bb67  ldloc.s  7
0x2bb69  ldloc.s  5
0x2bb6b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery::set_AppId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x2bb70  ldloc.3
0x2bb71  ldloc.s  7
0x2bb73  ldarg.3
0x2bb74  call     void Microsoft.Crm.Metadata.ClientMetadataService::FindRootsForQueryAndCombine(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem> combinedRoots, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery clientMetadataQuery, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x2bb79  ldstr    aAppmodules// "appmodules"
0x2bb7e  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery Microsoft.Crm.Metadata.ClientMetadataService::GetUserContextSubQueryBase(string metadataType)
0x2bb83  stloc.s  8
0x2bb85  ldloc.s  8
0x2bb87  ldstr    aAppmodule// "AppModule"
0x2bb8c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery::set_EntityLogicalName(string)
0x2bb91  ldloc.3
0x2bb92  ldloc.s  8
0x2bb94  ldarg.3
0x2bb95  call     void Microsoft.Crm.Metadata.ClientMetadataService::FindRootsForQueryAndCombine(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem> combinedRoots, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery clientMetadataQuery, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x2bb9a  ldstr    aQuickcreatemen// "quickcreatemenu"
0x2bb9f  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery Microsoft.Crm.Metadata.ClientMetadataService::GetUserContextSubQueryBase(string metadataType)
0x2bba4  stloc.s  9
0x2bba6  ldloc.s  9
0x2bba8  ldloc.s  4
0x2bbaa  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery::set_ChangedAfter(string)
0x2bbaf  ldloc.s  9
0x2bbb1  ldloc.s  5
0x2bbb3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery::set_AppId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x2bbb8  ldloc.3
0x2bbb9  ldloc.s  9
0x2bbbb  ldarg.3
0x2bbbc  call     void Microsoft.Crm.Metadata.ClientMetadataService::FindRootsForQueryAndCombine(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem> combinedRoots, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery clientMetadataQuery, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x2bbc1  ldstr    aRibbon// "ribbon"
0x2bbc6  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery Microsoft.Crm.Metadata.ClientMetadataService::GetUserContextSubQueryBase(string metadataType)
0x2bbcb  stloc.s  0xA
0x2bbcd  ldloc.s  0xA
0x2bbcf  ldc.i4.1
0x2bbd0  newarr   [mscorlib]System.String
0x2bbd5  dup
0x2bbd6  ldc.i4.0
0x2bbd7  ldstr    aGlobal// "Global"
0x2bbdc  stelem.ref
0x2bbdd  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery::set_MetadataNames(string[])
0x2bbe2  ldloc.s  0xA
0x2bbe4  ldstr    aNull_0// "null"
0x2bbe9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery::set_EntityLogicalName(string)
0x2bbee  ldloc.s  0xA
0x2bbf0  ldloc.s  4
0x2bbf2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery::set_ChangedAfter(string)
0x2bbf7  ldloc.s  0xA
0x2bbf9  ldloc.s  5
0x2bbfb  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery::set_AppId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x2bc00  ldloc.3
0x2bc01  ldloc.s  0xA
0x2bc03  ldarg.3
0x2bc04  call     void Microsoft.Crm.Metadata.ClientMetadataService::FindRootsForQueryAndCombine(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem> combinedRoots, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery clientMetadataQuery, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x2bc09  ldstr    aTaskbasedflowg// "taskbasedflowglobalmenu"
0x2bc0e  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery Microsoft.Crm.Metadata.ClientMetadataService::GetUserContextSubQueryBase(string metadataType)
0x2bc13  stloc.s  0xB
0x2bc15  ldloc.s  0xB
0x2bc17  ldloc.s  4
0x2bc19  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery::set_ChangedAfter(string)
0x2bc1e  ldloc.s  0xB
0x2bc20  ldloc.s  5
0x2bc22  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery::set_AppId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x2bc27  ldloc.3
0x2bc28  ldloc.s  0xB
0x2bc2a  ldarg.3
0x2bc2b  call     void Microsoft.Crm.Metadata.ClientMetadataService::FindRootsForQueryAndCombine(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem> combinedRoots, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery clientMetadataQuery, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x2bc30  ldstr    aSitemap_0// "sitemap"
0x2bc35  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery Microsoft.Crm.Metadata.ClientMetadataService::GetUserContextSubQueryBase(string metadataType)
0x2bc3a  stloc.s  0xC
0x2bc3c  ldloc.s  0xC
0x2bc3e  ldloc.s  4
0x2bc40  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery::set_ChangedAfter(string)
0x2bc45  ldloc.s  0xC
0x2bc47  ldloc.s  5
0x2bc49  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery::set_AppId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x2bc4e  ldloc.3
0x2bc4f  ldloc.s  0xC
0x2bc51  ldarg.3
0x2bc52  call     void Microsoft.Crm.Metadata.ClientMetadataService::FindRootsForQueryAndCombine(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem> combinedRoots, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery clientMetadataQuery, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x2bc57  ldloc.0
0x2bc58  ldloc.3
0x2bc59  ldarg.1
0x2bc5a  ldarg.2
0x2bc5b  ldarg.3
0x2bc5c  call     void Microsoft.Crm.Metadata.ClientMetadataService::AddClientMetadataFromRoots(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.MetadataSyncEventReporter eventReporter, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem> roots, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>> internalPayloadRepresentation, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery clientMetadataQuery, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x2bc61  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.UserContextGenerator::.ctor()
0x2bc66  ldarg.2
0x2bc67  ldarg.3
0x2bc68  callvirt instance object [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.UserContextGenerator::GetUserContext(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataQuery, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2bc6d  stloc.1
0x2bc6e  ldarg.1
0x2bc6f  ldsfld   string [Microsoft.Crm.ObjectModel]Microsoft.Crm.MetadataService.Utility.MetadataConstants::UserContext
0x2bc74  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x2bc79  dup
0x2bc7a  ldloc.1
0x2bc7b  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.MetadataService.Utility.ClientMetadataHelper::SerializeObject(object)
0x2bc80  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2bc85  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::Add(var<u1>, !!T0)
0x2bc8a  ldloc.0
0x2bc8b  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.MetadataServiceEventReporter::ReportAddUserContextCompleteEvent()
0x2bc90  ret
```
