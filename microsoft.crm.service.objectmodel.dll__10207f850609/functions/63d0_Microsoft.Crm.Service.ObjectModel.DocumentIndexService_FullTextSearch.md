# Microsoft.Crm.Service.ObjectModel.DocumentIndexService::FullTextSearch

- ea: `0x63d0`
- end: `0x65c2`
- name: `Microsoft.Crm.Service.ObjectModel.DocumentIndexService::FullTextSearch`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x61d0`

## callees

- `0x63d0`
- `0x65d0`
- `0x6650`
- `0x7c20`

## pseudocode

```c

```

## disassembly

```asm
0x63d0  ldarg.s  7
0x63d2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x63d7  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.DocumentIndex::.ctor(valuetype [mscorlib]System.Guid)
0x63dc  dup
0x63dd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x63e2  ldarg.s  7
0x63e4  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x63e9  stloc.0
0x63ea  ldarg.s  6
0x63ec  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x63f1  ldarg.s  6
0x63f3  ldstr    aDocumentid// "documentid"
0x63f8  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::ContainsColumn(string)
0x63fd  brtrue.s loc_640B
0x63ff  ldarg.s  6
0x6401  ldstr    aDocumentid// "documentid"
0x6406  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x640b  ldarg.s  6
0x640d  ldstr    aSubjectid// "subjectid"
0x6412  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::ContainsColumn(string)
0x6417  brtrue.s loc_6425
0x6419  ldarg.s  6
0x641b  ldstr    aSubjectid// "subjectid"
0x6420  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x6425  ldarg.s  6
0x6427  ldstr    aOrganizationid// "organizationid"
0x642c  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::ContainsColumn(string)
0x6431  brtrue.s loc_643F
0x6433  ldarg.s  6
0x6435  ldstr    aOrganizationid// "organizationid"
0x643a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x643f  ldarg.s  6
0x6441  ldstr    aIspublished// "ispublished"
0x6446  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::ContainsColumn(string)
0x644b  brtrue.s loc_6459
0x644d  ldarg.s  6
0x644f  ldstr    aIspublished// "ispublished"
0x6454  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x6459  ldarg.s  6
0x645b  ldarg.s  5
0x645d  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::ContainsColumn(string)
0x6462  brtrue.s loc_646D
0x6464  ldarg.s  6
0x6466  ldarg.s  5
0x6468  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x646d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x6472  ldarg.s  7
0x6474  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6479  stloc.1
0x647a  ldloc.1
0x647b  ldstr    aOrganizationid// "organizationid"
0x6480  ldc.i4.0
0x6481  ldarg.s  7
0x6483  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6488  box      [mscorlib]System.Guid
0x648d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6492  pop
0x6493  ldarg.2
0x6494  ldc.i4.0
0x6495  clt
0x6497  ldarg.3
0x6498  and
0x6499  brfalse.s loc_64AE
0x649b  ldloc.1
0x649c  ldstr    aIslatestversio// "islatestversion"
0x64a1  ldc.i4.0
0x64a2  ldc.i4.1
0x64a3  box      [mscorlib]System.Boolean
0x64a8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x64ad  pop
0x64ae  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0x64b3  brfalse.s loc_64C5
0x64b5  ldloc.1
0x64b6  ldarg.s  5
0x64b8  ldc.i4.6
0x64b9  ldarg.1
0x64ba  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x64bf  pop
0x64c0  br       loc_6581
0x64c5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x64ca  ldarg.s  7
0x64cc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x64d1  ldarg.s  7
0x64d3  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x64d8  ldarg.s  7
0x64da  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::GetCulture(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x64df  ldarg.1
0x64e0  stloc.2
0x64e1  ldarg.1
0x64e2  ldstr    aAnd// " AND "
0x64e7  callvirt instance int32 [mscorlib]System.String::IndexOf(string)
0x64ec  ldc.i4.m1
0x64ed  bne.un.s loc_6523
0x64ef  ldarg.1
0x64f0  ldstr    aOr// " OR "
0x64f5  callvirt instance int32 [mscorlib]System.String::IndexOf(string)
0x64fa  ldc.i4.m1
0x64fb  bne.un.s loc_6523
0x64fd  ldarg.1
0x64fe  ldstr    aAnd// " AND "
0x6503  ldstr    asc_1EEAA// " "
0x6508  ldc.i4.1
0x6509  call     string [System]System.Text.RegularExpressions.Regex::Replace(string, string, string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x650e  starg.s  1
0x6510  ldarg.1
0x6511  ldstr    aOr// " OR "
0x6516  ldstr    asc_1EEAA// " "
0x651b  ldc.i4.1
0x651c  call     string [System]System.Text.RegularExpressions.Regex::Replace(string, string, string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x6521  starg.s  1
0x6523  newobj   instance void Microsoft.Crm.Service.ObjectModel.NoiseWordsLoader::.ctor()
0x6528  newobj   instance void [Microsoft.Crm]Microsoft.Crm.SearchParser::.ctor(class [mscorlib]System.Globalization.CultureInfo, class [Microsoft.Crm]Microsoft.Crm.INoiseWordsLoader)
0x652d  ldarg.0
0x652e  ldarg.1
0x652f  call     instance string Microsoft.Crm.Service.ObjectModel.DocumentIndexService::ConvertSearchText(string searchText)
0x6534  ldarg.s  4
0x6536  callvirt instance string [Microsoft.Crm]Microsoft.Crm.SearchParser::ParseSearch(string, bool)
0x653b  starg.s  1
0x653d  ldarg.1
0x653e  ldstr    asc_1EE70// "*"
0x6543  callvirt instance bool [mscorlib]System.String::Contains(string)
0x6548  brfalse.s loc_656D
0x654a  ldloc.2
0x654b  callvirt instance string [mscorlib]System.String::Trim()
0x6550  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6555  ldc.i4.1
0x6556  ble.s    loc_6581
0x6558  ldloc.1
0x6559  ldarg.s  5
0x655b  ldc.i4.6
0x655c  ldarg.0
0x655d  ldloc.2
0x655e  ldarg.s  5
0x6560  call     instance string Microsoft.Crm.Service.ObjectModel.DocumentIndexService::ConvertUserFindToLike(string searchValue, string searchAttribute)
0x6565  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x656a  pop
0x656b  br.s     loc_6581
0x656d  ldarg.1
0x656e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6573  brtrue.s loc_6581
0x6575  ldloc.1
0x6576  ldarg.s  5
0x6578  ldc.i4.s 0x31
0x657a  ldarg.1
0x657b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6580  pop
0x6581  ldloc.1
0x6582  ldstr    aIspublished// "ispublished"
0x6587  ldc.i4.0
0x6588  ldc.i4.1
0x6589  box      [mscorlib]System.Boolean
0x658e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6593  pop
0x6594  ldloc.0
0x6595  ldarg.s  6
0x6597  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_ColumnSet(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression)
0x659c  ldloc.0
0x659d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x65a2  ldloc.1
0x65a3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x65a8  ldloc.0
0x65a9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.TopExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Top()
0x65ae  ldc.i4   0x3E8
0x65b3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.TopExpression::set_Count(int32)
0x65b8  ldarg.0
0x65b9  ldloc.0
0x65ba  ldarg.s  7
0x65bc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x65c1  ret
```
