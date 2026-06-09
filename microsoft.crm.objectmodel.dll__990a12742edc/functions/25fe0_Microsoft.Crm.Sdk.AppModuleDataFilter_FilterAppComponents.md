# Microsoft.Crm.Sdk.AppModuleDataFilter::FilterAppComponents

- ea: `0x25fe0`
- end: `0x2628b`
- name: `Microsoft.Crm.Sdk.AppModuleDataFilter::FilterAppComponents`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1f280`

## callees

- `0x20b40`
- `0x20b50`
- `0x20c80`
- `0x20ed0`
- `0x25fa0`
- `0x25fe0`
- `0x27080`
- `0x27130`
- `0x27170`
- `0x27220`
- `0x27260`
- `0x27870`
- `0x27b20`
- `0x27ba0`

## string_xrefs

- `0x25fe8`: `AppModuleDataFilter.FilterAppComponents(): context.PrimaryEntityName:{0}`
- `0x2603f`: `AppModuleDataFilter.FilterAppComponents(): [AppId:{0}]`
- `0x2606d`: `AppModuleDataFilter.FilterAppComponents(): Appid is empty no filtering required.`
- `0x260a6`: `AppModuleDataFilter.FilterAppComponents(): userData is null: {0}.`
- `0x260eb`: `AppModuleDataFilter.FilterAppComponents(): isSystemAdminOrSystemCustomizer: {0}.`
- `0x2616d`: `AppModuleDataFilter.FilterAppComponents(): AppModule [appmoduleid:{0}] Not available for user [isSystemAdminOrSystemCustomizer:{1}], User AppModule Privilege:{2}.`
- `0x261a3`: `AppModuleDataFilter.FilterAppComponents(): [MessageName:{0}].`
- `0x2620c`: `RetrieveEntityGroupConfiguration`
- `0x2625c`: `AppModuleDataFilter.FilterAppComponents(): [appid:{0}], Error Filtering [{1}], Exception: {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x25fe0  ldarg.1
0x25fe1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.PipelineExecutionContext::get_OrganizationId()
0x25fe6  ldc.i4.s 0x47
0x25fe8  ldstr    aAppmoduledataf// "AppModuleDataFilter.FilterAppComponents"...
0x25fed  ldc.i4.1
0x25fee  newarr   [mscorlib]System.Object
0x25ff3  dup
0x25ff4  ldc.i4.0
0x25ff5  ldarg.1
0x25ff6  callvirt instance string Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PrimaryEntityName()
0x25ffb  stelem.ref
0x25ffc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x26001  ldarg.1
0x26002  callvirt instance string Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PrimaryEntityName()
0x26007  ldstr    aSitemap// "SiteMap"
0x2600c  ldc.i4.5
0x2600d  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x26012  brfalse.s loc_2602F
0x26014  ldarg.1
0x26015  callvirt instance string Microsoft.Crm.Extensibility.PipelineExecutionContext::get_MessageName()
0x2601a  ldstr    aRetrievemultip// "RetrieveMultiple"
0x2601f  ldc.i4.5
0x26020  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x26025  brfalse.s loc_2602F
0x26027  ldarg.0
0x26028  ldarg.1
0x26029  call     instance void Microsoft.Crm.Sdk.AppModuleDataFilter::FilterSiteMapRetrieve(class Microsoft.Crm.Extensibility.PipelineExecutionContext context)
0x2602e  ret
0x2602f  ldarg.0
0x26030  ldarg.1
0x26031  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.AppModuleDataFilter::GetAppId(class Microsoft.Crm.Extensibility.PipelineExecutionContext context)
0x26036  stloc.0
0x26037  ldarg.1
0x26038  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.PipelineExecutionContext::get_OrganizationId()
0x2603d  ldc.i4.s 0x47
0x2603f  ldstr    aAppmoduledataf_0// "AppModuleDataFilter.FilterAppComponents"...
0x26044  ldc.i4.1
0x26045  newarr   [mscorlib]System.Object
0x2604a  dup
0x2604b  ldc.i4.0
0x2604c  ldloc.0
0x2604d  box      [mscorlib]System.Guid
0x26052  stelem.ref
0x26053  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x26058  ldloc.0
0x26059  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2605e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x26063  brfalse.s loc_2607E
0x26065  ldarg.1
0x26066  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.PipelineExecutionContext::get_OrganizationId()
0x2606b  ldc.i4.s 0x47
0x2606d  ldstr    aAppmoduledataf_1// "AppModuleDataFilter.FilterAppComponents"...
0x26072  ldc.i4.0
0x26073  newarr   [mscorlib]System.Object
0x26078  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2607d  ret
0x2607e  nop
0x2607f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x26084  ldarg.1
0x26085  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x2608a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x2608f  ldarg.1
0x26090  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x26095  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::TryLookupEntry(void, var<u1>)
0x2609a  stloc.1
0x2609b  ldloc.1
0x2609c  brtrue.s loc_260C7
0x2609e  ldarg.1
0x2609f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.PipelineExecutionContext::get_OrganizationId()
0x260a4  ldc.i4.s 0x47
0x260a6  ldstr    aAppmoduledataf_2// "AppModuleDataFilter.FilterAppComponents"...
0x260ab  ldc.i4.1
0x260ac  newarr   [mscorlib]System.Object
0x260b1  dup
0x260b2  ldc.i4.0
0x260b3  ldloc.1
0x260b4  ldnull
0x260b5  ceq
0x260b7  box      [mscorlib]System.Boolean
0x260bc  stelem.ref
0x260bd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x260c2  leave    loc_2628A
0x260c7  ldloc.1
0x260c8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_IsAdministrator()
0x260cd  brtrue.s loc_260DF
0x260cf  ldloc.1
0x260d0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_IsCustomizer()
0x260d5  brtrue.s loc_260DF
0x260d7  ldloc.1
0x260d8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_IsSystemUser()
0x260dd  br.s     loc_260E0
0x260df  ldc.i4.1
0x260e0  stloc.2
0x260e1  ldc.i4.m1
0x260e2  stloc.3
0x260e3  ldarg.1
0x260e4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.PipelineExecutionContext::get_OrganizationId()
0x260e9  ldc.i4.s 0x47
0x260eb  ldstr    aAppmoduledataf_3// "AppModuleDataFilter.FilterAppComponents"...
0x260f0  ldc.i4.1
0x260f1  newarr   [mscorlib]System.Object
0x260f6  dup
0x260f7  ldc.i4.0
0x260f8  ldloc.2
0x260f9  box      [mscorlib]System.Boolean
0x260fe  stelem.ref
0x260ff  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x26104  ldloc.2
0x26105  brtrue.s loc_2613D
0x26107  ldarg.1
0x26108  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2610d  ldstr    aAppmodule// "AppModule"
0x26112  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x26117  ldc.i4.1
0x26118  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType)
0x2611d  stloc.s  4
0x2611f  ldarg.1
0x26120  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x26125  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x2612a  ldloc.s  4
0x2612c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x26131  ldarg.1
0x26132  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x26137  call     int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::TryCheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2613c  stloc.3
0x2613d  ldloc.2
0x2613e  brtrue.s loc_2619B
0x26140  ldloc.3
0x26141  brtrue.s loc_26151
0x26143  ldloc.0
0x26144  ldarg.1
0x26145  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x2614a  call     bool Microsoft.Crm.Sdk.AppModuleCacheUtils::IsAppModuleAvailableForUser(valuetype [mscorlib]System.Guid appModuleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2614f  brtrue.s loc_2619B
0x26151  ldc.i4   0x80050116
0x26156  ldc.i4.0
0x26157  newarr   [mscorlib]System.Object
0x2615c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x26161  stloc.s  5
0x26163  ldloc.s  5
0x26165  ldarg.1
0x26166  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.PipelineExecutionContext::get_OrganizationId()
0x2616b  ldc.i4.s 0x47
0x2616d  ldstr    aAppmoduledataf_4// "AppModuleDataFilter.FilterAppComponents"...
0x26172  ldc.i4.3
0x26173  newarr   [mscorlib]System.Object
0x26178  dup
0x26179  ldc.i4.0
0x2617a  ldloc.0
0x2617b  box      [mscorlib]System.Guid
0x26180  stelem.ref
0x26181  dup
0x26182  ldc.i4.1
0x26183  ldloc.2
0x26184  box      [mscorlib]System.Boolean
0x26189  stelem.ref
0x2618a  dup
0x2618b  ldc.i4.2
0x2618c  ldloc.3
0x2618d  box      [mscorlib]System.Int32
0x26192  stelem.ref
0x26193  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x26198  ldloc.s  5
0x2619a  throw
0x2619b  ldarg.1
0x2619c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.PipelineExecutionContext::get_OrganizationId()
0x261a1  ldc.i4.s 0x47
0x261a3  ldstr    aAppmoduledataf_5// "AppModuleDataFilter.FilterAppComponents"...
0x261a8  ldc.i4.1
0x261a9  newarr   [mscorlib]System.Object
0x261ae  dup
0x261af  ldc.i4.0
0x261b0  ldarg.1
0x261b1  callvirt instance string Microsoft.Crm.Extensibility.PipelineExecutionContext::get_MessageName()
0x261b6  stelem.ref
0x261b7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x261bc  ldarg.1
0x261bd  callvirt instance string Microsoft.Crm.Extensibility.PipelineExecutionContext::get_MessageName()
0x261c2  stloc.s  6
0x261c4  ldloc.s  6
0x261c6  ldstr    aRetrieveallent// "RetrieveAllEntities"
0x261cb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x261d0  brtrue.s loc_2621A
0x261d2  ldloc.s  6
0x261d4  ldstr    aRetrievedashbo// "RetrieveDashboardForms"
0x261d9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x261de  brtrue.s loc_26223
0x261e0  ldloc.s  6
0x261e2  ldstr    aRetrievemultip// "RetrieveMultiple"
0x261e7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x261ec  brtrue.s loc_2622C
0x261ee  ldloc.s  6
0x261f0  ldstr    aRetrievemetada// "RetrieveMetadataChanges"
0x261f5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x261fa  brtrue.s loc_26235
0x261fc  ldloc.s  6
0x261fe  ldstr    aRetrieveproces// "RetrieveProcessWithFallback"
0x26203  call     bool [mscorlib]System.String::op_Equality(string, string)
0x26208  brtrue.s loc_2623E
0x2620a  ldloc.s  6
0x2620c  ldstr    aRetrieveentity// "RetrieveEntityGroupConfiguration"
0x26211  call     bool [mscorlib]System.String::op_Equality(string, string)
0x26216  brtrue.s loc_26247
0x26218  br.s     loc_2624E
0x2621a  ldarg.0
0x2621b  ldarg.1
0x2621c  call     instance void Microsoft.Crm.Sdk.AppModuleDataFilter::FilterEntityMetadata(class Microsoft.Crm.Extensibility.PipelineExecutionContext context)
0x26221  br.s     loc_2624E
0x26223  ldarg.0
0x26224  ldarg.1
0x26225  call     instance void Microsoft.Crm.Sdk.AppModuleDataFilter::FilterEntityReferenceCollection(class Microsoft.Crm.Extensibility.PipelineExecutionContext context)
0x2622a  br.s     loc_2624E
0x2622c  ldarg.0
0x2622d  ldarg.1
0x2622e  call     instance void Microsoft.Crm.Sdk.AppModuleDataFilter::FilterEntityCollection(class Microsoft.Crm.Extensibility.PipelineExecutionContext context)
0x26233  br.s     loc_2624E
0x26235  ldarg.0
0x26236  ldarg.1
0x26237  call     instance void Microsoft.Crm.Sdk.AppModuleDataFilter::FilterMetadataChanges(class Microsoft.Crm.Extensibility.PipelineExecutionContext context)
0x2623c  br.s     loc_2624E
0x2623e  ldarg.0
0x2623f  ldarg.1
0x26240  call     instance void Microsoft.Crm.Sdk.AppModuleDataFilter::FilterProcessWithFallback(class Microsoft.Crm.Extensibility.PipelineExecutionContext context)
0x26245  br.s     loc_2624E
0x26247  ldarg.0
0x26248  ldarg.1
0x26249  call     instance void Microsoft.Crm.Sdk.AppModuleDataFilter::FilterRetrieveEntityGroupConfiguration(class Microsoft.Crm.Extensibility.PipelineExecutionContext context)
0x2624e  leave.s  loc_2628A
0x26250  stloc.s  7
0x26252  ldloc.s  7
0x26254  ldarg.1
0x26255  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.PipelineExecutionContext::get_OrganizationId()
0x2625a  ldc.i4.s 0x47
0x2625c  ldstr    aAppmoduledataf_6// "AppModuleDataFilter.FilterAppComponents"...
0x26261  ldc.i4.3
0x26262  newarr   [mscorlib]System.Object
0x26267  dup
0x26268  ldc.i4.0
0x26269  ldloc.0
0x2626a  box      [mscorlib]System.Guid
0x2626f  stelem.ref
0x26270  dup
0x26271  ldc.i4.1
0x26272  ldarg.1
0x26273  callvirt instance string Microsoft.Crm.Extensibility.PipelineExecutionContext::get_MessageName()
0x26278  stelem.ref
0x26279  dup
0x2627a  ldc.i4.2
0x2627b  ldloc.s  7
0x2627d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x26282  stelem.ref
0x26283  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x26288  rethrow
0x2628a  ret
```
