# Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveEdmEntity

- ea: `0x1de20`
- end: `0x1df84`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveEdmEntity`
- size: `356`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x10bc0`
- `0x11540`

## callees

- `0xfab0`
- `0x13460`
- `0x147b0`
- `0x14880`
- `0x1da80`
- `0x1de20`
- `0x1e2a0`
- `0x1f380`
- `0x21370`
- `0x24e10`
- `0x28fe0`

## pseudocode

```c

```

## disassembly

```asm
0x1de20  ldarg.0
0x1de21  ldarg.s  4
0x1de23  ldarg.2
0x1de24  call     instance void Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::ThrowIfExpandWithRefForNonLookupNavProp(class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions, string edmEntityName)
0x1de29  ldarg.0
0x1de2a  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1de2f  ldarg.1
0x1de30  newobj   instance void Microsoft.Crm.Extensibility.OData.DataQueryOptionsConverter::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x1de35  stloc.0
0x1de36  ldarg.1
0x1de37  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1de3c  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::QueryParameterDictionary(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x1de41  call     bool Microsoft.Crm.Extensibility.OData.EdmUtilities::ValidateAndReturnNoLock(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParams)
0x1de46  stloc.1
0x1de47  ldnull
0x1de48  stloc.2
0x1de49  ldarg.s  4
0x1de4b  brfalse.s loc_1DE60
0x1de4d  ldloc.0
0x1de4e  ldarg.s  4
0x1de50  ldarg.2
0x1de51  ldarg.1
0x1de52  ldnull
0x1de53  callvirt instance var<u1> class Microsoft.Crm.Extensibility.OData.QueryOptionsConverterBase`4<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::GetQueryExpression(!!T0, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions, string, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext)
0x1de58  stloc.2
0x1de59  ldloc.2
0x1de5a  ldloc.1
0x1de5b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_NoLock(bool)
0x1de60  ldarg.2
0x1de61  ldarg.3
0x1de62  ldarg.0
0x1de63  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1de68  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetXrmEntityReferenceForKeys(string edmEntityName, string key, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1de6d  stloc.3
0x1de6e  ldloc.0
0x1de6f  ldloc.2
0x1de70  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x1de75  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1de7a  ldarg.s  4
0x1de7c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelationshipQueryCollection Microsoft.Crm.Extensibility.OData.DataQueryOptionsConverter::GetRelatedEntitiesRelationshipQueryCollection(string crmEntityName, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions)
0x1de81  stloc.s  4
0x1de83  ldloc.2
0x1de84  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1de89  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::get_Attributes()
0x1de8e  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpression, string> <>c::<>9__11_0
0x1de93  dup
0x1de94  brtrue.s loc_1DEAD
0x1de96  pop
0x1de97  ldsfld   class <>c <>c::<>9
0x1de9c  ldftn    instance string <>c::<RetrieveEdmEntity>b__11_0(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpression s)
0x1dea2  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpression, string>::.ctor(object, native int)
0x1dea7  dup
0x1dea8  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpression, string> <>c::<>9__11_0
0x1dead  call     T0x2B0000BA
0x1deb2  stloc.s  5
0x1deb4  ldarg.1
0x1deb5  ldloc.3
0x1deb6  ldloc.s  5
0x1deb8  call     T0x2B00002B
0x1debd  ldloc.s  4
0x1debf  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveEntityWithRelatedRecords(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference primaryEntityReference, string[] columns, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelationshipQueryCollection relatedEntitiesQuery)
0x1dec4  stloc.s  6
0x1dec6  ldarg.s  4
0x1dec8  brfalse.s loc_1DEF4
0x1deca  ldarg.s  4
0x1decc  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1ded1  brfalse.s loc_1DEF4
0x1ded3  ldarg.s  4
0x1ded5  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1deda  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x1dedf  brfalse.s loc_1DEF4
0x1dee1  ldarg.s  4
0x1dee3  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1dee8  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x1deed  callvirt instance bool [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause::get_AllSelected()
0x1def2  br.s     loc_1DEF5
0x1def4  ldc.i4.1
0x1def5  stloc.s  7
0x1def7  ldloc.s  6
0x1def9  ldarg.2
0x1defa  ldarg.0
0x1defb  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1df00  ldc.i4.0
0x1df01  ldloc.s  7
0x1df03  ldloc.1
0x1df04  call     class [System.Web.OData]System.Web.OData.EdmEntityObject Microsoft.Crm.Extensibility.OData.EdmTypeConverter::ConvertToEdmEntityObject(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] bool isDeltaEntity, [opt] bool fillAllProperties, [opt] bool noLock)
0x1df09  stloc.s  8
0x1df0b  ldarg.s  4
0x1df0d  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1df12  brfalse.s loc_1DF6A
0x1df14  ldarg.s  4
0x1df16  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1df1b  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x1df20  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectItem> [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause::get_SelectedItems()
0x1df25  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectItem>::GetEnumerator()
0x1df2a  stloc.s  9
0x1df2c  br.s     loc_1DF53
0x1df2e  ldloc.s  9
0x1df30  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectItem>::get_Current()
0x1df35  stloc.s  0xA
0x1df37  ldloc.s  0xA
0x1df39  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.ExpandedNavigationSelectItem
0x1df3e  brfalse.s loc_1DF53
0x1df40  ldloc.s  0xA
0x1df42  castclass [Microsoft.OData.Core]Microsoft.OData.UriParser.ExpandedNavigationSelectItem
0x1df47  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [Microsoft.OData.Core]Microsoft.OData.UriParser.ExpandedNavigationSelectItem::get_SelectAndExpand()
0x1df4c  callvirt instance bool [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause::get_AllSelected()
0x1df51  stloc.s  7
0x1df53  ldloc.s  9
0x1df55  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1df5a  brtrue.s loc_1DF2E
0x1df5c  leave.s  loc_1DF6A
0x1df5e  ldloc.s  9
0x1df60  brfalse.s loc_1DF69
0x1df62  ldloc.s  9
0x1df64  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1df69  endfinally
0x1df6a  ldloc.s  6
0x1df6c  ldloc.s  8
0x1df6e  ldarg.1
0x1df6f  ldarg.s  4
0x1df71  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1df76  ldarg.0
0x1df77  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1df7c  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::SetRelatedEntitiesInEdmEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, class [System.Web.OData]System.Web.OData.EdmEntityObject edmEntity, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption selectExpand, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1df81  ldloc.s  8
0x1df83  ret
```
