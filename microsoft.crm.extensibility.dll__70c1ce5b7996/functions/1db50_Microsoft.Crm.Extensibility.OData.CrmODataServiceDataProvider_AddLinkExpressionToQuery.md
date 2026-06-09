# Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::AddLinkExpressionToQuery

- ea: `0x1db50`
- end: `0x1dd33`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::AddLinkExpressionToQuery`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d750`

## callees

- `0xfb60`
- `0xfbd0`
- `0xfbf0`
- `0xfe80`
- `0x1db20`
- `0x1db50`
- `0x1dd40`
- `0x1dd70`
- `0x1f140`

## string_xrefs

- `0x1dcf9`: `_LinkEntityAliasPrefix_`

## pseudocode

```c

```

## disassembly

```asm
0x1db50  ldnull
0x1db51  stloc.0
0x1db52  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::.ctor()
0x1db57  pop
0x1db58  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1db5d  stloc.1
0x1db5e  ldarg.2
0x1db5f  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1db64  call     class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ExpandedNavigationSelectItem> Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::GetExpandedProperties(class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption selecExpandQueryOption)
0x1db69  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ExpandedNavigationSelectItem>::GetEnumerator()
0x1db6e  stloc.2
0x1db6f  br       loc_1DD1A
0x1db74  ldloc.2
0x1db75  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ExpandedNavigationSelectItem>::get_Current()
0x1db7a  stloc.3
0x1db7b  ldloc.3
0x1db7c  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataExpandPath [Microsoft.OData.Core]Microsoft.OData.UriParser.ExpandedReferenceSelectItem::get_PathToNavigationProperty()
0x1db81  call     T0x2B000007
0x1db86  castclass [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertySegment
0x1db8b  stloc.s  4
0x1db8d  ldarg.1
0x1db8e  ldarg.0
0x1db8f  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1db94  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityNameFromCollectionName(string entityCollectionName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1db99  stloc.s  5
0x1db9b  ldloc.s  4
0x1db9d  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertySegment::get_NavigationProperty()
0x1dba2  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x1dba7  ldloc.s  5
0x1dba9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::GetEntityRelationshipFromNavigation(string edmNavigationPropertyName, string entityName)
0x1dbae  stloc.s  6
0x1dbb0  ldloc.1
0x1dbb1  ldloc.s  4
0x1dbb3  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertySegment::get_NavigationProperty()
0x1dbb8  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x1dbbd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1dbc2  ldloc.s  5
0x1dbc4  ldloc.s  4
0x1dbc6  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertySegment::get_NavigationProperty()
0x1dbcb  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x1dbd0  ldarg.0
0x1dbd1  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1dbd6  ldc.i4.0
0x1dbd7  call     bool Microsoft.Crm.Extensibility.OData.EdmUtilities::IsManyToOneRelationship(string edmEntityName, string navigationPropertyName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] bool isMetadataEntity)
0x1dbdc  brfalse  loc_1DD1A
0x1dbe1  ldloc.3
0x1dbe2  call     void Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::ValidateExpandedReferenceForValidParameters(class [Microsoft.OData.Core]Microsoft.OData.UriParser.ExpandedNavigationSelectItem expNavSelectItem)
0x1dbe7  ldloc.s  6
0x1dbe9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_Relationships()
0x1dbee  ldc.i4.0
0x1dbef  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataArrayList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship>::get_Item(!!T0)
0x1dbf4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x1dbf9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x1dbfe  stloc.s  7
0x1dc00  ldloc.s  6
0x1dc02  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_Relationships()
0x1dc07  ldc.i4.0
0x1dc08  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataArrayList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship>::get_Item(!!T0)
0x1dc0d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencedAttribute()
0x1dc12  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x1dc17  stloc.s  8
0x1dc19  ldloc.s  4
0x1dc1b  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertySegment::get_NavigationProperty()
0x1dc20  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty::get_Partner()
0x1dc25  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::DeclaringEntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty)
0x1dc2a  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x1dc2f  stloc.s  9
0x1dc31  ldloc.s  9
0x1dc33  ldarg.0
0x1dc34  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1dc39  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetXrmEntityLogicalNameFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1dc3e  stloc.s  0xA
0x1dc40  ldloc.s  0xA
0x1dc42  ldarg.3
0x1dc43  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.Expression::get_UserAndOrganizationContext()
0x1dc48  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1dc4d  stloc.0
0x1dc4e  ldloc.3
0x1dc4f  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [Microsoft.OData.Core]Microsoft.OData.UriParser.ExpandedNavigationSelectItem::get_SelectAndExpand()
0x1dc54  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectItem> [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause::get_SelectedItems()
0x1dc59  call     T0x2B000068
0x1dc5e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.PathSelectItem>::GetEnumerator()
0x1dc63  stloc.s  0xB
0x1dc65  br.s     loc_1DCB4
0x1dc67  ldloc.s  0xB
0x1dc69  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.PathSelectItem>::get_Current()
0x1dc6e  stloc.s  0xC
0x1dc70  ldloc.s  0xC
0x1dc72  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataSelectPath [Microsoft.OData.Core]Microsoft.OData.UriParser.PathSelectItem::get_SelectedPath()
0x1dc77  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPath::get_FirstSegment()
0x1dc7c  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.PropertySegment
0x1dc81  brfalse.s loc_1DCB4
0x1dc83  ldloc.s  0xA
0x1dc85  ldloc.s  0xC
0x1dc87  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataSelectPath [Microsoft.OData.Core]Microsoft.OData.UriParser.PathSelectItem::get_SelectedPath()
0x1dc8c  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPath::get_FirstSegment()
0x1dc91  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.PropertySegment
0x1dc96  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuralProperty [Microsoft.OData.Core]Microsoft.OData.UriParser.PropertySegment::get_Property()
0x1dc9b  ldarg.0
0x1dc9c  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1dca1  call     string Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetCrmAttributeNameFromEdmProperty(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuralProperty edmStructuralProperty, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1dca6  stloc.s  0xD
0x1dca8  ldloc.s  0xD
0x1dcaa  brfalse.s loc_1DCB4
0x1dcac  ldloc.0
0x1dcad  ldloc.s  0xD
0x1dcaf  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x1dcb4  ldloc.s  0xB
0x1dcb6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1dcbb  brtrue.s loc_1DC67
0x1dcbd  leave.s  loc_1DCCB
0x1dcbf  ldloc.s  0xB
0x1dcc1  brfalse.s loc_1DCCA
0x1dcc3  ldloc.s  0xB
0x1dcc5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1dcca  endfinally
0x1dccb  ldloc.0
0x1dccc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::get_Attributes()
0x1dcd1  call     T0x2B0000B9
0x1dcd6  brtrue.s loc_1DCF0
0x1dcd8  ldloc.0
0x1dcd9  ldloc.s  9
0x1dcdb  ldarg.0
0x1dcdc  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1dce1  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Crm.Extensibility.OData.EdmUtilities::GetCrmAttributeNamesForRead(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1dce6  call     T0x2B00002B
0x1dceb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x1dcf0  ldarg.3
0x1dcf1  ldloc.s  0xA
0x1dcf3  ldloc.s  8
0x1dcf5  ldloc.s  7
0x1dcf7  ldc.i4.0
0x1dcf8  ldc.i4.1
0x1dcf9  ldstr    aLinkentityalia// "_LinkEntityAliasPrefix_"
0x1dcfe  ldloc.s  4
0x1dd00  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertySegment::get_NavigationProperty()
0x1dd05  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x1dd0a  call     string [mscorlib]System.String::Concat(string, string)
0x1dd0f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator, string)
0x1dd14  ldloc.0
0x1dd15  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::set_ColumnSet(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression)
0x1dd1a  ldloc.2
0x1dd1b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1dd20  brtrue   loc_1DB74
0x1dd25  leave.s  loc_1DD31
0x1dd27  ldloc.2
0x1dd28  brfalse.s loc_1DD30
0x1dd2a  ldloc.2
0x1dd2b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1dd30  endfinally
0x1dd31  ldloc.1
0x1dd32  ret
```
