# Microsoft.Crm.Sdk.Metadata.MetadataServiceProvider::RetrieveMetadataChanges

- ea: `0xe8c0`
- end: `0xeade`
- name: `Microsoft.Crm.Sdk.Metadata.MetadataServiceProvider::RetrieveMetadataChanges`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x623f0`

## callees

- `0xdc00`
- `0xdc30`
- `0xe8c0`
- `0xeae0`
- `0xeb10`
- `0xec60`
- `0x10130`
- `0x101b0`
- `0x101d0`
- `0x15c00`
- `0x15c70`
- `0x60c00`
- `0x60fc0`
- `0x60fd0`
- `0x75560`

## string_xrefs

- `0xe8e8`: `prvReadEntity`
- `0xe906`: `prvReadAttribute`
- `0xe924`: `prvReadRelationship`

## pseudocode

```c

```

## disassembly

```asm
0xe8c0  ldarg.s  4
0xe8c2  ldstr    aContext// "context"
0xe8c7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xe8cc  newobj   instance void Microsoft.Crm.Sdk.Metadata.MetadataPerformanceCounter::.ctor()
0xe8d1  stloc.0
0xe8d2  newobj   instance void <>c__DisplayClass30_0::.ctor()
0xe8d7  stloc.1
0xe8d8  ldarg.s  4
0xe8da  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xe8df  stloc.2
0xe8e0  ldarg.s  4
0xe8e2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0xe8e7  ldloc.2
0xe8e8  ldstr    aPrvreadentity// "prvReadEntity"
0xe8ed  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(string)
0xe8f2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0xe8f7  ldarg.s  4
0xe8f9  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe8fe  ldarg.s  4
0xe900  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0xe905  ldloc.2
0xe906  ldstr    aPrvreadattribu// "prvReadAttribute"
0xe90b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(string)
0xe910  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0xe915  ldarg.s  4
0xe917  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe91c  ldarg.s  4
0xe91e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0xe923  ldloc.2
0xe924  ldstr    aPrvreadrelatio// "prvReadRelationship"
0xe929  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(string)
0xe92e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0xe933  ldarg.s  4
0xe935  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe93a  ldarg.3
0xe93b  ldarg.s  4
0xe93d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0xe942  newobj   instance void Microsoft.Crm.Sdk.Metadata.VersionStamp::.ctor(string versionStamp, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0xe947  stloc.3
0xe948  leave.s  loc_E95B
0xe94a  pop
0xe94b  ldstr    aInvalidVersion// "Invalid version stamp"
0xe950  ldc.i4   0x80044183
0xe955  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xe95a  throw
0xe95b  ldloc.3
0xe95c  callvirt instance bool Microsoft.Crm.Sdk.Metadata.VersionStamp::get_HasExpired()
0xe961  brfalse.s loc_E974
0xe963  ldc.i4   0x80044352
0xe968  ldc.i4.0
0xe969  newarr   [mscorlib]System.Object
0xe96e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xe973  throw
0xe974  ldarg.s  6
0xe976  ldnull
0xe977  stind.ref
0xe978  ldloc.3
0xe979  callvirt instance int64 Microsoft.Crm.Sdk.Metadata.VersionStamp::get_VersionNumber()
0xe97e  stloc.s  4
0xe980  ldloc.1
0xe981  ldarg.s  4
0xe983  ldloc.s  4
0xe985  newobj   instance void Microsoft.Crm.Sdk.Metadata.MetadataConversionContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, int64 clientVersionNumber)
0xe98a  stfld    class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext <>c__DisplayClass30_0::conversionContext
0xe98f  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadataCollection::.ctor()
0xe994  stloc.s  5
0xe996  ldarg.s  4
0xe998  call     class Microsoft.Crm.Sdk.Metadata.VersionStamp Microsoft.Crm.Sdk.Metadata.MetadataServiceProvider::BuildServerVersionStamp(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0xe99d  stloc.s  6
0xe99f  ldarg.s  5
0xe9a1  ldloc.s  6
0xe9a3  callvirt instance string [mscorlib]System.Object::ToString()
0xe9a8  stind.ref
0xe9a9  ldloc.s  4
0xe9ab  ldloc.s  6
0xe9ad  callvirt instance int64 Microsoft.Crm.Sdk.Metadata.VersionStamp::get_VersionNumber()
0xe9b2  blt.s    loc_E9BD
0xe9b4  ldloc.s  5
0xe9b6  stloc.s  8
0xe9b8  leave    loc_EADB
0xe9bd  ldarg.0
0xe9be  ldarg.s  4
0xe9c0  ldloc.1
0xe9c1  ldfld    class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext <>c__DisplayClass30_0::conversionContext
0xe9c6  ldloc.s  6
0xe9c8  call     instance void Microsoft.Crm.Sdk.Metadata.MetadataServiceProvider::FlushMetadataCacheIfNeeded(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext conversionContext, class Microsoft.Crm.Sdk.Metadata.VersionStamp metadataVersionStamp)
0xe9cd  ldarg.1
0xe9ce  brfalse.s loc_E9F4
0xe9d0  ldloc.1
0xe9d1  ldfld    class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext <>c__DisplayClass30_0::conversionContext
0xe9d6  newobj   instance void Microsoft.Crm.Metadata.Query.SelectFromMetadataCacheStrategy::.ctor(class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0xe9db  dup
0xe9dc  newobj   instance void Microsoft.Crm.Metadata.Query.MetadataQuerySelectVisitor::.ctor(class Microsoft.Crm.Metadata.Query.IMetadataSelectionStrategy strategy)
0xe9e1  stloc.s  9
0xe9e3  ldarg.1
0xe9e4  ldloc.s  9
0xe9e6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataQueryBase::Accept(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.IMetadataQueryExpressionVisitor)
0xe9eb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata> Microsoft.Crm.Metadata.Query.SelectFromMetadataCacheStrategy::get_SelectedEntities()
0xe9f0  stloc.s  7
0xe9f2  br.s     loc_EA21
0xe9f4  ldloc.1
0xe9f5  ldfld    class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext <>c__DisplayClass30_0::conversionContext
0xe9fa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Sdk.Metadata.MetadataConversionContext::get_MetadataCache()
0xe9ff  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Entities()
0xea04  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0xea09  call     T0x2B00000C
0xea0e  ldloc.1
0xea0f  ldftn    instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata <>c__DisplayClass30_0::<RetrieveMetadataChanges>b__0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity)
0xea15  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::.ctor(object, native int)
0xea1a  call     T0x2B00000D
0xea1f  stloc.s  7
0xea21  nop
0xea22  ldloc.s  7
0xea24  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::GetEnumerator()
0xea29  stloc.s  0xA
0xea2b  br.s     loc_EA43
0xea2d  ldloc.s  0xA
0xea2f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::get_Current()
0xea34  stloc.s  0xB
0xea36  ldloc.s  0xB
0xea38  brfalse.s loc_EA43
0xea3a  ldloc.s  5
0xea3c  ldloc.s  0xB
0xea3e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::Add(var<u1>)
0xea43  ldloc.s  0xA
0xea45  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xea4a  brtrue.s loc_EA2D
0xea4c  leave.s  loc_EA5A
0xea4e  ldloc.s  0xA
0xea50  brfalse.s loc_EA59
0xea52  ldloc.s  0xA
0xea54  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xea59  endfinally
0xea5a  leave.s  loc_EAA6
0xea5c  stloc.s  0xC
0xea5e  ldarg.s  4
0xea60  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xea65  ldc.i4.s 0x1A
0xea67  ldstr    a0// "{0}"
0xea6c  ldc.i4.1
0xea6d  newarr   [mscorlib]System.Object
0xea72  dup
0xea73  ldc.i4.0
0xea74  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xea79  ldstr    aExceptionEvalu// "Exception evaluating metadata query: {0"...
0xea7e  ldc.i4.1
0xea7f  newarr   [mscorlib]System.Object
0xea84  dup
0xea85  ldc.i4.0
0xea86  ldloc.s  0xC
0xea88  stelem.ref
0xea89  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xea8e  stelem.ref
0xea8f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xea94  ldstr    aUnableToEvalua// "Unable to evaluate query"
0xea99  ldloc.s  0xC
0xea9b  ldc.i4   0x80044183
0xeaa0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception, int32)
0xeaa5  throw
0xeaa6  ldarga.s 2
0xeaa8  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.DeletedMetadataFilters>::get_HasValue()
0xeaad  brfalse.s loc_EAC5
0xeaaf  ldarg.s  6
0xeab1  ldarg.0
0xeab2  ldloc.1
0xeab3  ldfld    class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext <>c__DisplayClass30_0::conversionContext
0xeab8  ldarga.s 2
0xeaba  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.DeletedMetadataFilters>::get_Value()
0xeabf  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.DeletedMetadataCollection Microsoft.Crm.Sdk.Metadata.MetadataServiceProvider::GetDeletedMetadata(class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.DeletedMetadataFilters filters)
0xeac4  stind.ref
0xeac5  ldloc.0
0xeac6  callvirt instance void Microsoft.Crm.Sdk.Metadata.MetadataPerformanceCounter::TrackSuccessfulRequest()
0xeacb  ldloc.s  5
0xeacd  stloc.s  8
0xeacf  leave.s  loc_EADB
0xead1  ldloc.0
0xead2  brfalse.s loc_EADA
0xead4  ldloc.0
0xead5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xeada  endfinally
0xeadb  ldloc.s  8
0xeadd  ret
```
