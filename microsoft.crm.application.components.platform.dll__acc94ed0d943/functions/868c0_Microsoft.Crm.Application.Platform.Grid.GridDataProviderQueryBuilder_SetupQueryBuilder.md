# Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::SetupQueryBuilder

- ea: `0x868c0`
- end: `0x86bfd`
- name: `Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::SetupQueryBuilder`
- size: `829`
- prototype: ``
- caller_count: `1`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x86370`

## callees

- `0xbe0`
- `0x1560`
- `0x1570`
- `0x15c0`
- `0x1600`
- `0x1620`
- `0x1690`
- `0x4a30`
- `0x4a50`
- `0x4a70`
- `0x4b30`
- `0x4bc0`
- `0x4cc0`
- `0x4d50`
- `0x4e90`
- `0x5080`
- `0x5880`
- `0x58e0`
- `0x115b0`
- `0x82a00`
- `0x82a30`
- `0x82a40`
- `0x84df0`
- `0x84e00`
- `0x84e40`
- `0x84e60`
- `0x84e80`
- `0x84e90`
- `0x84ee0`
- `0x84f80`
- `0x84fa0`
- `0x84fb0`
- `0x85040`
- `0x86830`
- `0x868c0`
- `0x86c00`
- `0x86d10`
- `0x86db0`
- `0x86f10`
- `0x86fd0`

## string_xrefs

- `0x8697f`: `processid`
- `0x86994`: `processid`
- `0x868c6`: `fetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x868c0  ldarg.0
0x868c1  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x868c6  ldstr    aFetchxml_0// "fetchXml"
0x868cb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x868d0  stloc.0
0x868d1  ldloc.0
0x868d2  brfalse.s loc_86907
0x868d4  ldloc.0
0x868d5  callvirt instance int32 [mscorlib]System.String::get_Length()
0x868da  brfalse.s loc_86907
0x868dc  ldarg.1
0x868dd  callvirt instance class Microsoft.Crm.ApplicationQuery Microsoft.Crm.QueryBuilder::get_Query()
0x868e2  ldloc.0
0x868e3  callvirt instance void Microsoft.Crm.ApplicationQuery::set_QueryXml(string value)
0x868e8  ldarg.1
0x868e9  callvirt instance class Microsoft.Crm.ApplicationQuery Microsoft.Crm.QueryBuilder::get_Query()
0x868ee  ldnull
0x868ef  callvirt instance void Microsoft.Crm.ApplicationQuery::set_QueryApi(string value)
0x868f4  ldarg.1
0x868f5  callvirt instance class Microsoft.Crm.ApplicationQuery Microsoft.Crm.QueryBuilder::get_Query()
0x868fa  ldc.i4.1
0x868fb  callvirt instance void Microsoft.Crm.ApplicationQuery::set_IgnoreViewApi(bool value)
0x86900  ldarg.1
0x86901  ldc.i4.0
0x86902  callvirt instance void Microsoft.Crm.QueryBuilder::set_UseViewApi(bool value)
0x86907  ldarg.0
0x86908  ldarg.1
0x86909  call     instance bool Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::processQuickFindParameter(class Microsoft.Crm.QueryBuilder queryBuilder)
0x8690e  stloc.1
0x8690f  ldloc.1
0x86910  brtrue.s loc_86914
0x86912  ldc.i4.0
0x86913  ret
0x86914  ldarg.0
0x86915  ldarg.1
0x86916  ldarg.2
0x86917  call     instance void Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::processGuidsParameter(class Microsoft.Crm.QueryBuilder queryBuilder, class Microsoft.Crm.View view)
0x8691c  ldarg.0
0x8691d  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x86922  ldstr    aDynamicfilter// "dynamicfilter"
0x86927  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8692c  stloc.2
0x8692d  ldloc.2
0x8692e  brfalse.s loc_8693F
0x86930  ldloc.2
0x86931  callvirt instance int32 [mscorlib]System.String::get_Length()
0x86936  brfalse.s loc_8693F
0x86938  ldarg.1
0x86939  ldloc.2
0x8693a  callvirt instance void Microsoft.Crm.QueryBuilder::ProcessDynamicFilter(string dynamicFilter)
0x8693f  ldarg.0
0x86940  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x86945  ldstr    aQueryapi_0// "queryapi"
0x8694a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8694f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x86954  brtrue.s loc_86971
0x86956  ldarg.1
0x86957  callvirt instance class Microsoft.Crm.ApplicationQuery Microsoft.Crm.QueryBuilder::get_Query()
0x8695c  ldarg.0
0x8695d  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x86962  ldstr    aQueryapi_0// "queryapi"
0x86967  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8696c  callvirt instance void Microsoft.Crm.ApplicationQuery::set_QueryApi(string value)
0x86971  ldarg.0
0x86972  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::get_CurrentMetadata()
0x86977  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsBusinessProcessEnabled()
0x8697c  brfalse.s loc_869C6
0x8697e  ldarg.0
0x8697f  ldstr    aProcessid// "processid"
0x86984  ldarg.0
0x86985  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::get_CurrentMetadata()
0x8698a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x8698f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_Name()
0x86994  ldstr    aProcessid// "processid"
0x86999  ldc.i4.0
0x8699a  ldc.i4.0
0x8699b  ldc.i4.1
0x8699c  ldc.i4.0
0x8699d  call     instance void Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::AddColumn(string name, string entityName, string label, unsigned int32 width, bool isSortable, bool isHidden, bool isMetadataBound)
0x869a2  ldarg.0
0x869a3  ldstr    aProcessts// "processts"
0x869a8  ldarg.0
0x869a9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::get_CurrentMetadata()
0x869ae  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x869b3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_Name()
0x869b8  ldstr    aProcessts// "processts"
0x869bd  ldc.i4.0
0x869be  ldc.i4.0
0x869bf  ldc.i4.1
0x869c0  ldc.i4.0
0x869c1  call     instance void Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::AddColumn(string name, string entityName, string label, unsigned int32 width, bool isSortable, bool isHidden, bool isMetadataBound)
0x869c6  ldarg.0
0x869c7  call     instance bool Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::shouldShowHierarchyIcon()
0x869cc  brfalse.s loc_86A22
0x869ce  ldarg.1
0x869cf  callvirt instance class Microsoft.Crm.ApplicationQuery Microsoft.Crm.QueryBuilder::get_Query()
0x869d4  ldc.i4.1
0x869d5  callvirt instance void Microsoft.Crm.ApplicationQuery::set_RetrieveHierarchyInformation(bool value)
0x869da  ldarg.0
0x869db  ldstr    aHierarchydatap// "HierarchyDataParentID6dcd9e4c001441b092"...
0x869e0  ldarg.0
0x869e1  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::get_CurrentMetadata()
0x869e6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x869eb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_Name()
0x869f0  ldstr    aHierarchydatap// "HierarchyDataParentID6dcd9e4c001441b092"...
0x869f5  ldc.i4.0
0x869f6  ldc.i4.0
0x869f7  ldc.i4.1
0x869f8  ldc.i4.0
0x869f9  call     instance void Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::AddColumn(string name, string entityName, string label, unsigned int32 width, bool isSortable, bool isHidden, bool isMetadataBound)
0x869fe  ldarg.0
0x869ff  ldstr    aHierarchydatac// "HierarchyDataChildCount6dcd9e4c001441b0"...
0x86a04  ldarg.0
0x86a05  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::get_CurrentMetadata()
0x86a0a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x86a0f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_Name()
0x86a14  ldstr    aHierarchydatac// "HierarchyDataChildCount6dcd9e4c001441b0"...
0x86a19  ldc.i4.0
0x86a1a  ldc.i4.0
0x86a1b  ldc.i4.1
0x86a1c  ldc.i4.0
0x86a1d  call     instance void Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::AddColumn(string name, string entityName, string label, unsigned int32 width, bool isSortable, bool isHidden, bool isMetadataBound)
0x86a22  ldarg.1
0x86a23  callvirt instance class Microsoft.Crm.ApplicationQuery Microsoft.Crm.QueryBuilder::get_Query()
0x86a28  callvirt instance string Microsoft.Crm.ApplicationQuery::get_QueryXml()
0x86a2d  brfalse.s loc_86AA6
0x86a2f  ldarg.1
0x86a30  callvirt instance class Microsoft.Crm.ApplicationQuery Microsoft.Crm.QueryBuilder::get_Query()
0x86a35  callvirt instance string Microsoft.Crm.ApplicationQuery::get_QueryXml()
0x86a3a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x86a3f  ldc.i4.0
0x86a40  ble.s    loc_86AA6
0x86a42  ldarg.0
0x86a43  call     instance class Microsoft.Crm.Application.Platform.Grid.ColumnCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Columns()
0x86a48  brfalse.s loc_86AA6
0x86a4a  ldarg.0
0x86a4b  call     instance class Microsoft.Crm.Application.Platform.Grid.ColumnCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Columns()
0x86a50  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x86a55  stloc.s  4
0x86a57  br.s     loc_86A86
0x86a59  ldloc.s  4
0x86a5b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x86a60  castclass Microsoft.Crm.Application.Platform.Grid.Column
0x86a65  stloc.s  5
0x86a67  ldloc.s  5
0x86a69  callvirt instance bool Microsoft.Crm.Application.Platform.Grid.Column::get_IsMetadataBound()
0x86a6e  brfalse.s loc_86A86
0x86a70  ldloc.s  5
0x86a72  callvirt instance bool Microsoft.Crm.Application.Platform.Grid.Column::get_IsFromRelatedEntity()
0x86a77  brtrue.s loc_86A86
0x86a79  ldarg.1
0x86a7a  ldloc.s  5
0x86a7c  callvirt instance string Microsoft.Crm.Application.Platform.Grid.Column::get_Name()
0x86a81  callvirt instance void Microsoft.Crm.QueryBuilder::AddColumn(string columnName)
0x86a86  ldloc.s  4
0x86a88  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x86a8d  brtrue.s loc_86A59
0x86a8f  leave.s  loc_86AA6
0x86a91  ldloc.s  4
0x86a93  isinst   [mscorlib]System.IDisposable
0x86a98  stloc.s  6
0x86a9a  ldloc.s  6
0x86a9c  brfalse.s loc_86AA5
0x86a9e  ldloc.s  6
0x86aa0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x86aa5  endfinally
0x86aa6  ldarg.0
0x86aa7  call     instance unsigned int32 Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_RecordsPerPage()
0x86aac  brtrue.s loc_86AD3
0x86aae  ldarg.0
0x86aaf  call     instance unsigned int32 Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_RecordsPerPage()
0x86ab4  ldc.i4.0
0x86ab5  cgt.un
0x86ab7  ldstr    aGridDataProvid// "Grid data provider must always specify "...
0x86abc  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x86ac1  ldstr    aGridRequestedA// "Grid requested all records.  Setting Re"...
0x86ac6  call     void Microsoft.Crm.Util::TraceWarning(string message)
0x86acb  ldarg.0
0x86acc  ldc.i4.s 0x32
0x86ace  call     instance void Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::set_RecordsPerPage(unsigned int32 value)
0x86ad3  ldarg.1
0x86ad4  ldarg.0
0x86ad5  call     instance unsigned int32 Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_PageNumber()
0x86ada  stloc.s  7
0x86adc  ldloca.s 7
0x86ade  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x86ae3  call     instance string [mscorlib]System.UInt32::ToString(class [mscorlib]System.IFormatProvider)
0x86ae8  ldarg.0
0x86ae9  call     instance unsigned int32 Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_RecordsPerPage()
0x86aee  ldarg.0
0x86aef  callvirt instance bool Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_ReturnTotalRecordCount()
0x86af4  callvirt instance void Microsoft.Crm.QueryBuilder::SetPageCriteria(string pageNumber, int32 pageSize, bool returnTotalRecordCount)
0x86af9  ldarg.1
0x86afa  callvirt instance class Microsoft.Crm.ApplicationQuery Microsoft.Crm.QueryBuilder::get_Query()
0x86aff  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x86b04  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Order()
0x86b09  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression::get_Orders()
0x86b0e  callvirt instance void [mscorlib]System.Collections.ArrayList::Clear()
0x86b13  ldarg.0
0x86b14  ldarg.1
0x86b15  call     instance void Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::FixSortOrder(class Microsoft.Crm.QueryBuilder queryBuilder)
0x86b1a  ldarg.0
0x86b1b  call     instance class Microsoft.Crm.GridSortColumnCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_SortColumns()
0x86b20  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.QueryColumnSortInfo>::GetEnumerator()
0x86b25  stloc.s  8
0x86b27  br.s     loc_86B3A
0x86b29  ldloca.s 8
0x86b2b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.QueryColumnSortInfo>::get_Current()
0x86b30  stloc.s  9
0x86b32  ldarg.1
0x86b33  ldloc.s  9
0x86b35  callvirt instance void Microsoft.Crm.QueryBuilder::AddSortCriteria(class Microsoft.Crm.QueryColumnSortInfo sortInfo)
0x86b3a  ldloca.s 8
0x86b3c  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.QueryColumnSortInfo>::MoveNext()
0x86b41  brtrue.s loc_86B29
0x86b43  leave.s  loc_86B53
0x86b45  ldloca.s 8
0x86b47  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.QueryColumnSortInfo>
0x86b4d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x86b52  endfinally
0x86b53  ldarg.0
0x86b54  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x86b59  ldstr    aFilter// "filter"
0x86b5e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x86b63  stloc.3
0x86b64  ldloc.3
0x86b65  brfalse  loc_86BEF
0x86b6a  ldloc.3
0x86b6b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x86b70  ldc.i4.0
0x86b71  ble.s    loc_86BEF
0x86b73  ldarg.0
0x86b74  ldnull
0x86b75  call     instance void Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::set_JumpField(string value)
0x86b7a  ldarg.0
0x86b7b  call     instance class Microsoft.Crm.GridSortColumnCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_SortColumns()
0x86b80  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.QueryColumnSortInfo>::get_Count()
0x86b85  ldc.i4.0
0x86b86  ble.s    loc_86BA5
0x86b88  ldarg.0
0x86b89  ldarg.0
0x86b8a  ldarg.0
0x86b8b  call     instance class Microsoft.Crm.GridSortColumnCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_SortColumns()
0x86b90  ldc.i4.0
0x86b91  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.QueryColumnSortInfo>::get_Item(!!T0)
0x86b96  callvirt instance string Microsoft.Crm.QueryColumnSortInfo::get_Name()
0x86b9b  call     instance string Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::GetJumpField(string sortColumnName)
0x86ba0  call     instance void Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::set_JumpField(string value)
0x86ba5  ldarg.0
0x86ba6  call     instance string Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_JumpField()
0x86bab  brtrue.s loc_86BBF
0x86bad  ldarg.0
0x86bae  ldarg.0
0x86baf  ldarg.2
0x86bb0  callvirt instance string Microsoft.Crm.View::get_JumpField()
0x86bb5  call     instance string Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::GetJumpField(string sortColumnName)
0x86bba  call     instance void Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::set_JumpField(string value)
0x86bbf  ldarg.0
0x86bc0  call     instance string Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_JumpField()
0x86bc5  brtrue.s loc_86BE2
0x86bc7  ldstr    aTheJumpFieldIn// "The Jump Field in view '"
0x86bcc  ldarg.2
0x86bcd  callvirt instance string Microsoft.Crm.View::get_Title()
0x86bd2  ldstr    aIsNotSetCorrec// "' is not set correctly in the metadata"
0x86bd7  call     string [mscorlib]System.String::Concat(string, string, string)
0x86bdc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x86be1  throw
0x86be2  ldarg.1
0x86be3  ldarg.0
0x86be4  call     instance string Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_JumpField()
0x86be9  ldloc.3
0x86bea  callvirt instance void Microsoft.Crm.QueryBuilder::SetJumpCriteria(string jumpField, string jumpCriteria)
0x86bef  ldarg.1
0x86bf0  ldarg.0
0x86bf1  callvirt instance string Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_PagingCookie()
0x86bf6  callvirt instance void Microsoft.Crm.QueryBuilder::SetPagingCookie(string pagingCookie)
0x86bfb  ldloc.1
0x86bfc  ret
```
