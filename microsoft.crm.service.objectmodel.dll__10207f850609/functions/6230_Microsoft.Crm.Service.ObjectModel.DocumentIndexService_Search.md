# Microsoft.Crm.Service.ObjectModel.DocumentIndexService::Search

- ea: `0x6230`
- end: `0x63ca`
- name: `Microsoft.Crm.Service.ObjectModel.DocumentIndexService::Search`
- size: `410`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x61b0`
- `0x61f0`
- `0x6210`

## callees

- `0x6230`
- `0x6650`
- `0x7c20`
- `0xb250`

## pseudocode

```c

```

## disassembly

```asm
0x6230  ldarg.s  6
0x6232  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6237  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.DocumentIndex::.ctor(valuetype [mscorlib]System.Guid)
0x623c  ldarg.s  5
0x623e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x6243  ldarg.s  5
0x6245  ldstr    aDocumentid// "documentid"
0x624a  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::ContainsColumn(string)
0x624f  brtrue.s loc_625D
0x6251  ldarg.s  5
0x6253  ldstr    aDocumentid// "documentid"
0x6258  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x625d  ldarg.s  5
0x625f  ldstr    aSubjectid// "subjectid"
0x6264  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::ContainsColumn(string)
0x6269  brtrue.s loc_6277
0x626b  ldarg.s  5
0x626d  ldstr    aSubjectid// "subjectid"
0x6272  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x6277  ldarg.s  5
0x6279  ldstr    aOrganizationid// "organizationid"
0x627e  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::ContainsColumn(string)
0x6283  brtrue.s loc_6291
0x6285  ldarg.s  5
0x6287  ldstr    aOrganizationid// "organizationid"
0x628c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x6291  ldarg.s  5
0x6293  ldstr    aIspublished// "ispublished"
0x6298  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::ContainsColumn(string)
0x629d  brtrue.s loc_62AB
0x629f  ldarg.s  5
0x62a1  ldstr    aIspublished// "ispublished"
0x62a6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x62ab  ldarg.s  5
0x62ad  ldarg.s  4
0x62af  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::ContainsColumn(string)
0x62b4  brtrue.s loc_62BF
0x62b6  ldarg.s  5
0x62b8  ldarg.s  4
0x62ba  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x62bf  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x62c4  ldarg.s  6
0x62c6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x62cb  stloc.0
0x62cc  ldloc.0
0x62cd  ldstr    aOrganizationid// "organizationid"
0x62d2  ldc.i4.0
0x62d3  ldarg.s  6
0x62d5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x62da  box      [mscorlib]System.Guid
0x62df  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x62e4  pop
0x62e5  ldarg.2
0x62e6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x62eb  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x62f0  brfalse.s loc_6309
0x62f2  ldarg.2
0x62f3  ldarg.s  6
0x62f5  call     valuetype [mscorlib]System.Guid[] Microsoft.Crm.Service.ObjectModel.SubjectService::GetSubjectHierarchy(valuetype [mscorlib]System.Guid subjectId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x62fa  stloc.1
0x62fb  ldloc.0
0x62fc  ldstr    aSubjectid// "subjectid"
0x6301  ldc.i4.8
0x6302  ldloc.1
0x6303  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x6308  pop
0x6309  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0x630e  brfalse.s loc_6320
0x6310  ldloc.0
0x6311  ldarg.s  4
0x6313  ldc.i4.6
0x6314  ldarg.1
0x6315  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x631a  pop
0x631b  br       loc_63AB
0x6320  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x6325  ldarg.s  6
0x6327  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x632c  ldarg.s  6
0x632e  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x6333  ldarg.s  6
0x6335  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::GetCulture(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x633a  ldarg.1
0x633b  stloc.2
0x633c  newobj   instance void Microsoft.Crm.Service.ObjectModel.NoiseWordsLoader::.ctor()
0x6341  newobj   instance void [Microsoft.Crm]Microsoft.Crm.SearchParser::.ctor(class [mscorlib]System.Globalization.CultureInfo, class [Microsoft.Crm]Microsoft.Crm.INoiseWordsLoader)
0x6346  ldarg.1
0x6347  ldarg.3
0x6348  callvirt instance string [Microsoft.Crm]Microsoft.Crm.SearchParser::ParseSearch(string, bool)
0x634d  starg.s  1
0x634f  ldarg.1
0x6350  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6355  brfalse.s loc_636F
0x6357  ldloc.0
0x6358  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x635d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x6362  ldarg.s  6
0x6364  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6369  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x636e  ret
0x636f  ldarg.1
0x6370  ldstr    asc_1EE70// "*"
0x6375  callvirt instance bool [mscorlib]System.String::Contains(string)
0x637a  brfalse.s loc_639F
0x637c  ldloc.2
0x637d  callvirt instance string [mscorlib]System.String::Trim()
0x6382  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6387  ldc.i4.1
0x6388  ble.s    loc_63AB
0x638a  ldloc.0
0x638b  ldarg.s  4
0x638d  ldc.i4.6
0x638e  ldarg.0
0x638f  ldloc.2
0x6390  ldarg.s  4
0x6392  call     instance string Microsoft.Crm.Service.ObjectModel.DocumentIndexService::ConvertUserFindToLike(string searchValue, string searchAttribute)
0x6397  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x639c  pop
0x639d  br.s     loc_63AB
0x639f  ldloc.0
0x63a0  ldarg.s  4
0x63a2  ldc.i4.s 0x31
0x63a4  ldarg.1
0x63a5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x63aa  pop
0x63ab  ldloc.0
0x63ac  ldstr    aIspublished// "ispublished"
0x63b1  ldc.i4.0
0x63b2  ldc.i4.1
0x63b3  box      [mscorlib]System.Boolean
0x63b8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x63bd  pop
0x63be  ldarg.0
0x63bf  ldloc.0
0x63c0  ldarg.s  5
0x63c2  ldarg.s  6
0x63c4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x63c9  ret
```
