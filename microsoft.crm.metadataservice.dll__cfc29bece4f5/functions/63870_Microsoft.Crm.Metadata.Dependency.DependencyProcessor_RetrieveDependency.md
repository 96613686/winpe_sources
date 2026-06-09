# Microsoft.Crm.Metadata.Dependency.DependencyProcessor::RetrieveDependency

- ea: `0x63870`
- end: `0x63c5a`
- name: `Microsoft.Crm.Metadata.Dependency.DependencyProcessor::RetrieveDependency`
- size: `1002`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x2b550`
- `0x2b8c0`

## callees

- `0x63770`
- `0x63870`
- `0x63c60`
- `0x64570`
- `0x64590`
- `0x645b0`
- `0x64700`
- `0x64b60`
- `0x64c00`
- `0x64cf0`
- `0x75380`

## string_xrefs

- `0x638fb`: `requiredcomponenttype`
- `0x63a50`: `requiredcomponenttype`

## pseudocode

```c

```

## disassembly

```asm
0x63870  ldarg.2
0x63871  ldstr    aExecutionconte_0// "executionContext"
0x63876  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6387b  ldc.i4.0
0x6387c  stloc.0
0x6387d  br       loc_63C53
0x63882  ldarg.1
0x63883  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem>::get_Values()
0x63888  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem>::get_Count()
0x6388d  stloc.1
0x6388e  ldarg.1
0x6388f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem>::get_Values()
0x63894  call     T0x2B00005C
0x63899  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem>::GetEnumerator()
0x6389e  stloc.2
0x6389f  br       loc_63C28
0x638a4  ldloca.s 2
0x638a6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem>::get_Current()
0x638ab  stloc.3
0x638ac  ldloc.3
0x638ad  callvirt instance valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItemStatus [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_Status()
0x638b2  brtrue   loc_63C28
0x638b7  ldloc.3
0x638b8  callvirt instance object [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_Data()
0x638bd  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x638c2  brfalse  loc_639B0
0x638c7  ldloc.3
0x638c8  callvirt instance object [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_Data()
0x638cd  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x638d2  stloc.s  4
0x638d4  ldarg.0
0x638d5  ldloc.s  4
0x638d7  ldarg.2
0x638d8  call     instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GetAllDependencies(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x638dd  newobj   instance void Microsoft.Crm.Metadata.Dependency.SolutionComponentMapper::.ctor()
0x638e2  stloc.s  5
0x638e4  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::GetEnumerator()
0x638e9  stloc.s  6
0x638eb  br       loc_63986
0x638f0  ldloca.s 6
0x638f2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::get_Current()
0x638f7  stloc.s  7
0x638f9  ldloc.s  7
0x638fb  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x63900  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x63905  unbox.any [mscorlib]System.Int32
0x6390a  stloc.s  8
0x6390c  ldarg.0
0x6390d  ldloc.s  7
0x6390f  call     instance object Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GetRequiredComponentObjectId(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity item)
0x63914  stloc.s  9
0x63916  ldloc.s  8
0x63918  ldc.i4.s 0x1D
0x6391a  bne.un.s loc_63973
0x6391c  ldloc.s  4
0x6391e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x63923  ldstr    aWorkflow// "Workflow"
0x63928  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6392d  brfalse.s loc_63973
0x6392f  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x63934  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x63939  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_BpfActionSupportPUV2()
0x6393e  ldarg.2
0x6393f  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x63944  brfalse.s loc_63986
0x63946  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x6394b  ldarg.2
0x6394c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x63951  ldarg.2
0x63952  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x63957  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsActionSupportFeatureEnabled()
0x6395c  brfalse.s loc_63986
0x6395e  ldloc.s  5
0x63960  ldarg.1
0x63961  ldloc.s  8
0x63963  ldloc.s  9
0x63965  ldloc.3
0x63966  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_QueryContext()
0x6396b  ldarg.2
0x6396c  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.IComponentMapper::Map(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem>, int32, object, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x63971  br.s     loc_63986
0x63973  ldloc.s  5
0x63975  ldarg.1
0x63976  ldloc.s  8
0x63978  ldloc.s  9
0x6397a  ldloc.3
0x6397b  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_QueryContext()
0x63980  ldarg.2
0x63981  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.IComponentMapper::Map(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem>, int32, object, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x63986  ldloca.s 6
0x63988  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::MoveNext()
0x6398d  brtrue   loc_638F0
0x63992  leave.s  loc_639A2
0x63994  ldloca.s 6
0x63996  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>
0x6399c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x639a1  endfinally
0x639a2  ldarg.0
0x639a3  ldarg.1
0x639a4  ldloc.3
0x639a5  ldarg.2
0x639a6  call     instance void Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GenerateDependencies(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem> roots, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem candidate, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x639ab  br       loc_63C21
0x639b0  ldloc.3
0x639b1  callvirt instance object [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_Data()
0x639b6  isinst   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>
0x639bb  brtrue   loc_63C21
0x639c0  ldloc.3
0x639c1  callvirt instance object [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_Data()
0x639c6  isinst   [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.OtherItem
0x639cb  brfalse  loc_63A9A
0x639d0  ldloc.3
0x639d1  callvirt instance object [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_Data()
0x639d6  castclass [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.OtherItem
0x639db  callvirt instance valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.OtherCandidateType [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.OtherItem::get_CandidateType()
0x639e0  ldc.i4.5
0x639e1  bne.un   loc_63C21
0x639e6  ldloc.3
0x639e7  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_QueryContext()
0x639ec  ldarg.2
0x639ed  call     object [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.SiteMapGenerator::GetSiteMap(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x639f2  stloc.s  0xA
0x639f4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x639f9  stloc.s  0xB
0x639fb  ldloc.s  0xA
0x639fd  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x63a02  ldstr    aSitemapid_0// "SiteMapId"
0x63a07  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x63a0c  ldloc.s  0xA
0x63a0e  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object)
0x63a13  unbox.any [mscorlib]System.Guid
0x63a18  stloc.s  0xB
0x63a1a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::.ctor()
0x63a1f  dup
0x63a20  ldarg.0
0x63a21  ldloc.s  0xB
0x63a23  ldc.i4.s 0x3E
0x63a25  ldarg.2
0x63a26  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GetRuntimeDependenciesByDependentComponentIdAndType(valuetype [mscorlib]System.Guid dependentComponentNodeId, int32 dependentComponentType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x63a2b  call     T0x2B00005D
0x63a30  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x63a35  newobj   instance void Microsoft.Crm.Metadata.Dependency.SolutionComponentMapper::.ctor()
0x63a3a  stloc.s  0xC
0x63a3c  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::GetEnumerator()
0x63a41  stloc.s  6
0x63a43  br.s     loc_63A7E
0x63a45  ldloca.s 6
0x63a47  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::get_Current()
0x63a4c  stloc.s  0xD
0x63a4e  ldloc.s  0xD
0x63a50  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x63a55  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x63a5a  unbox.any [mscorlib]System.Int32
0x63a5f  stloc.s  0xE
0x63a61  ldarg.0
0x63a62  ldloc.s  0xD
0x63a64  call     instance object Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GetRequiredComponentObjectId(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity item)
0x63a69  stloc.s  0xF
0x63a6b  ldloc.s  0xC
0x63a6d  ldarg.1
0x63a6e  ldloc.s  0xE
0x63a70  ldloc.s  0xF
0x63a72  ldloc.3
0x63a73  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_QueryContext()
0x63a78  ldarg.2
0x63a79  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.IComponentMapper::Map(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem>, int32, object, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x63a7e  ldloca.s 6
0x63a80  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::MoveNext()
0x63a85  brtrue.s loc_63A45
0x63a87  leave    loc_63C21
0x63a8c  ldloca.s 6
0x63a8e  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>
0x63a94  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x63a99  endfinally
0x63a9a  ldloc.3
0x63a9b  callvirt instance object [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_Data()
0x63aa0  isinst   [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.MetadataContext
0x63aa5  brfalse  loc_63C21
0x63aaa  ldloc.3
0x63aab  callvirt instance object [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_Data()
0x63ab0  isinst   [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.MetadataContext
0x63ab5  stloc.s  0x10
0x63ab7  ldloc.s  0x10
0x63ab9  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.MetadataContext::get_MetadataType()
0x63abe  stloc.s  0x11
0x63ac0  ldloc.s  0x11
0x63ac2  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x63ac7  stloc.s  0x12
0x63ac9  ldloc.s  0x12
0x63acb  ldc.i4   0x53270006
0x63ad0  bgt.un.s loc_63B12
0x63ad2  ldloc.s  0x12
0x63ad4  ldc.i4   0x2F2D75B6
0x63ad9  bgt.un.s loc_63AF8
0x63adb  ldloc.s  0x12
0x63add  ldc.i4   0x1E0E9F1B
0x63ae2  beq      loc_63B72
0x63ae7  ldloc.s  0x12
0x63ae9  ldc.i4   0x2F2D75B6
0x63aee  beq      loc_63B85
0x63af3  br       loc_63C21
0x63af8  ldloc.s  0x12
0x63afa  ldc.i4   0x4058C747
0x63aff  beq.s    loc_63B4C
0x63b01  ldloc.s  0x12
0x63b03  ldc.i4   0x53270006
0x63b08  beq      loc_63BC8
0x63b0d  br       loc_63C21
0x63b12  ldloc.s  0x12
0x63b14  ldc.i4   0x9BCCF7A0
0x63b19  bgt.un.s loc_63B35
0x63b1b  ldloc.s  0x12
0x63b1d  ldc.i4   0x63073EDD
0x63b22  beq.s    loc_63B5F
0x63b24  ldloc.s  0x12
0x63b26  ldc.i4   0x9BCCF7A0
0x63b2b  beq      loc_63BB8
0x63b30  br       loc_63C21
0x63b35  ldloc.s  0x12
0x63b37  ldc.i4   0x9CA2F9B9
0x63b3c  beq.s    loc_63BA8
0x63b3e  ldloc.s  0x12
0x63b40  ldc.i4   0xCEB27113
0x63b45  beq.s    loc_63B98
0x63b47  br       loc_63C21
0x63b4c  ldloc.s  0x11
0x63b4e  ldstr    aForm// "form"
0x63b53  call     bool [mscorlib]System.String::op_Equality(string, string)
0x63b58  brtrue.s loc_63BD8
0x63b5a  br       loc_63C21
0x63b5f  ldloc.s  0x11
0x63b61  ldstr    aSavedview// "savedview"
0x63b66  call     bool [mscorlib]System.String::op_Equality(string, string)
0x63b6b  brtrue.s loc_63BEA
0x63b6d  br       loc_63C21
0x63b72  ldloc.s  0x11
0x63b74  ldstr    aUserview// "userview"
0x63b79  call     bool [mscorlib]System.String::op_Equality(string, string)
0x63b7e  brtrue.s loc_63BEA
0x63b80  br       loc_63C21
0x63b85  ldloc.s  0x11
0x63b87  ldstr    aWorkspace// "workspace"
0x63b8c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x63b91  brtrue.s loc_63BFC
0x63b93  br       loc_63C21
0x63b98  ldloc.s  0x11
0x63b9a  ldstr    aUserworkspace// "userworkspace"
0x63b9f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x63ba4  brtrue.s loc_63BFC
0x63ba6  br.s     loc_63C21
0x63ba8  ldloc.s  0x11
0x63baa  ldstr    aSystemworkspac// "systemworkspace"
0x63baf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x63bb4  brtrue.s loc_63BFC
0x63bb6  br.s     loc_63C21
0x63bb8  ldloc.s  0x11
0x63bba  ldstr    aSavedvisualiza// "savedvisualization"
0x63bbf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x63bc4  brtrue.s loc_63C0E
0x63bc6  br.s     loc_63C21
0x63bc8  ldloc.s  0x11
0x63bca  ldstr    aUservisualizat// "uservisualization"
0x63bcf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x63bd4  brtrue.s loc_63C0E
0x63bd6  br.s     loc_63C21
0x63bd8  ldarg.0
0x63bd9  ldarg.1
0x63bda  ldloc.s  0x10
0x63bdc  ldloc.3
0x63bdd  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_QueryContext()
0x63be2  ldarg.2
0x63be3  call     instance void Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GenerateFormContext(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem> roots, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.MetadataContext metadataContext, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext queryContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x63be8  br.s     loc_63C21
0x63bea  ldarg.0
0x63beb  ldarg.1
0x63bec  ldloc.s  0x10
0x63bee  ldloc.3
0x63bef  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_QueryContext()
0x63bf4  ldarg.2
0x63bf5  call     instance void Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GenerateViewContext(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem> roots, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.MetadataContext metadataContext, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext queryContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x63bfa  br.s     loc_63C21
0x63bfc  ldarg.0
0x63bfd  ldarg.1
0x63bfe  ldloc.s  0x10
0x63c00  ldloc.3
0x63c01  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_QueryContext()
0x63c06  ldarg.2
0x63c07  call     instance void Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GenerateDashboardContext(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem> roots, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.MetadataContext metadataContext, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext queryContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x63c0c  br.s     loc_63C21
0x63c0e  ldloc.s  0x10
0x63c10  ldstr    aVisualizations// "visualizationselector"
0x63c15  ldarg.1
0x63c16  ldloc.3
0x63c17  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_QueryContext()
0x63c1c  call     void Microsoft.Crm.Metadata.Dependency.DependencyProcessor::AddSelectorCandidateItem(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.MetadataContext metadataContext, string selectorType, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem> roots, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext queryContext)
0x63c21  ldloc.3
0x63c22  ldc.i4.1
0x63c23  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::set_Status(valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItemStatus)
0x63c28  ldloca.s 2
0x63c2a  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem>::MoveNext()
  ... truncated ...
```
