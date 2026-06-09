# Microsoft.Crm.ApplicationQuery::BuildQuery

- ea: `0x17b0`
- end: `0x1c64`
- name: `Microsoft.Crm.ApplicationQuery::BuildQuery`
- size: `1204`
- prototype: ``
- caller_count: `2`
- callee_count: `37`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1730`
- `0x7d980`

## callees

- `0x1260`
- `0x1280`
- `0x1510`
- `0x15f0`
- `0x1610`
- `0x1630`
- `0x1650`
- `0x1660`
- `0x1690`
- `0x16f0`
- `0x17b0`
- `0x1c70`
- `0x1cc0`
- `0x1d40`
- `0x1d70`
- `0x2070`
- `0x2090`
- `0x2200`
- `0x2370`
- `0x23f0`
- `0x2810`
- `0x4670`
- `0x5900`
- `0x5a350`
- `0x5be20`
- `0x6a0d0`
- `0x6a330`
- `0x87ae0`
- `0x87af0`
- `0x9b8c0`
- `0x9b8e0`
- `0x9cb30`
- `0x9cb50`
- `0x9cb70`
- `0x9cc10`
- `0x9f430`
- `0x9f900`

## string_xrefs

- `0x1a13`: `isFetchXmlNotFinal`
- `0x1a4b`: `teamTemplateId`
- `0x1c4d`: `effectiveFetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x17b0  ldarg.0
0x17b1  ldfld    class Microsoft.Crm.View Microsoft.Crm.ApplicationQuery::_view
0x17b6  brtrue.s loc_17C3
0x17b8  ldstr    aEitherTheViewO// "Either the view or view id must be set."
0x17bd  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x17c2  throw
0x17c3  ldarg.0
0x17c4  ldfld    class Microsoft.Crm.View Microsoft.Crm.ApplicationQuery::_view
0x17c9  callvirt instance string Microsoft.Crm.View::get_QueryApi()
0x17ce  ldstr    aAuto// "AUTO"
0x17d3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17d8  brfalse.s loc_17F5
0x17da  ldarg.0
0x17db  ldfld    string Microsoft.Crm.ApplicationQuery::_autoQueryApi
0x17e0  brtrue.s loc_17F5
0x17e2  ldarg.0
0x17e3  call     instance bool Microsoft.Crm.ApplicationQuery::get_IgnoreViewApi()
0x17e8  brtrue.s loc_17F5
0x17ea  ldstr    aThisSavedQuery// "This Saved Query has a QueryApi of AUTO"...
0x17ef  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x17f4  throw
0x17f5  ldarg.0
0x17f6  call     instance void Microsoft.Crm.ApplicationQuery::AddStateCodeFilterToDepthRelViewColumnset()
0x17fb  ldarg.0
0x17fc  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x1801  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x1806  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x180b  brtrue.s loc_1829
0x180d  ldarg.0
0x180e  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x1813  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x1818  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x181d  ldstr    aActivitypointe// "activitypointer"
0x1822  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1827  brfalse.s loc_182F
0x1829  ldarg.0
0x182a  call     instance void Microsoft.Crm.ApplicationQuery::AddActivityFilter()
0x182f  ldarg.0
0x1830  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x1835  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x183a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x183f  ldstr    aSharepointdocu// "sharepointdocument"
0x1844  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1849  brfalse.s loc_1851
0x184b  ldarg.0
0x184c  call     instance void Microsoft.Crm.ApplicationQuery::AddSharePointFilter()
0x1851  ldarg.0
0x1852  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x1857  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x185c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1861  ldstr    aQueueitem// "queueitem"
0x1866  call     bool [mscorlib]System.String::op_Equality(string, string)
0x186b  brfalse.s loc_1873
0x186d  ldarg.0
0x186e  call     instance void Microsoft.Crm.ApplicationQuery::AddQueueFilter()
0x1873  ldarg.0
0x1874  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x1879  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x187e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1883  ldstr    aDataperformanc// "dataperformance"
0x1888  call     bool [mscorlib]System.String::op_Equality(string, string)
0x188d  brfalse.s loc_1895
0x188f  ldarg.0
0x1890  call     instance void Microsoft.Crm.ApplicationQuery::AddDataPerformanceFilter()
0x1895  ldarg.0
0x1896  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x189b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x18a0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x18a5  ldstr    aWorkflow// "workflow"
0x18aa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18af  brfalse.s loc_18B7
0x18b1  ldarg.0
0x18b2  call     instance void Microsoft.Crm.ApplicationQuery::AddWorkflowFilter()
0x18b7  ldarg.0
0x18b8  ldarg.0
0x18b9  call     instance class ApiCommand Microsoft.Crm.ApplicationQuery::GetApiCommand()
0x18be  stfld    class ApiCommand Microsoft.Crm.ApplicationQuery::_apiCommand
0x18c3  ldarg.0
0x18c4  ldfld    class ApiCommand Microsoft.Crm.ApplicationQuery::_apiCommand
0x18c9  isinst   RetrieveListByObjectCommand
0x18ce  brtrue.s loc_18E0
0x18d0  ldarg.0
0x18d1  ldfld    class ApiCommand Microsoft.Crm.ApplicationQuery::_apiCommand
0x18d6  isinst   RetrievePartQueryForRollupAttribCommand
0x18db  brfalse  loc_19F6
0x18e0  ldarg.0
0x18e1  call     instance string Microsoft.Crm.ApplicationQuery::get_QuickFindXml()
0x18e6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x18eb  brtrue   loc_19F6
0x18f0  ldarg.0
0x18f1  ldfld    class ApiCommand Microsoft.Crm.ApplicationQuery::_apiCommand
0x18f6  isinst   RetrievePartQueryForRollupAttribCommand
0x18fb  brfalse.s loc_1910
0x18fd  ldarg.0
0x18fe  ldfld    class ApiCommand Microsoft.Crm.ApplicationQuery::_apiCommand
0x1903  isinst   RetrievePartQueryForRollupAttribCommand
0x1908  callvirt instance string RetrievePartQueryForRollupAttribCommand::AddQueryFilters()
0x190d  stloc.3
0x190e  br.s     loc_1921
0x1910  ldarg.0
0x1911  ldfld    class ApiCommand Microsoft.Crm.ApplicationQuery::_apiCommand
0x1916  isinst   RetrieveListByObjectCommand
0x191b  callvirt instance string RetrieveListByObjectCommand::AddListFilters()
0x1920  stloc.3
0x1921  ldloc.3
0x1922  brfalse  loc_19E9
0x1927  ldarg.0
0x1928  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x192d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x1932  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::get_Count()
0x1937  stloc.s  4
0x1939  ldarg.0
0x193a  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x193f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x1944  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::get_PageBack()
0x1949  stloc.s  5
0x194b  ldarg.0
0x194c  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x1951  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x1956  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::get_PageNumber()
0x195b  stloc.s  6
0x195d  ldarg.0
0x195e  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x1963  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x1968  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::get_PagingCookie()
0x196d  stloc.s  7
0x196f  ldarg.0
0x1970  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x1975  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x197a  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::get_ReturnTotalRecordCount()
0x197f  stloc.s  8
0x1981  ldarg.0
0x1982  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x1987  ldloc.3
0x1988  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::DeserializeFromFetchXml(string)
0x198d  ldarg.0
0x198e  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x1993  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x1998  ldloc.s  4
0x199a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_Count(int32)
0x199f  ldarg.0
0x19a0  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x19a5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x19aa  ldloc.s  5
0x19ac  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_PageBack(int32)
0x19b1  ldarg.0
0x19b2  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x19b7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x19bc  ldloc.s  6
0x19be  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_PageNumber(int32)
0x19c3  ldarg.0
0x19c4  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x19c9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x19ce  ldloc.s  7
0x19d0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_PagingCookie(string)
0x19d5  ldarg.0
0x19d6  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x19db  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x19e0  ldloc.s  8
0x19e2  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_ReturnTotalRecordCount(bool)
0x19e7  br.s     loc_1A01
0x19e9  ldarg.0
0x19ea  ldfld    class ApiCommand Microsoft.Crm.ApplicationQuery::_apiCommand
0x19ef  callvirt instance void ApiCommand::DecorateQuery()
0x19f4  br.s     loc_1A01
0x19f6  ldarg.0
0x19f7  ldfld    class ApiCommand Microsoft.Crm.ApplicationQuery::_apiCommand
0x19fc  callvirt instance void ApiCommand::DecorateQuery()
0x1a01  ldarg.0
0x1a02  ldarg.0
0x1a03  ldfld    class ApiCommand Microsoft.Crm.ApplicationQuery::_apiCommand
0x1a08  callvirt instance bool ApiCommand::get_IsCustomQuery()
0x1a0d  call     instance void Microsoft.Crm.ApplicationQuery::set_IsCustomQuery(bool value)
0x1a12  ldarg.0
0x1a13  ldstr    aIsfetchxmlnotf// "isFetchXmlNotFinal"
0x1a18  ldarg.0
0x1a19  call     instance bool Microsoft.Crm.ApplicationQuery::get_IsCustomQuery()
0x1a1e  stloc.s  9
0x1a20  ldloca.s 9
0x1a22  call     instance string [mscorlib]System.Boolean::ToString()
0x1a27  ldc.i4.1
0x1a28  call     instance void Microsoft.Crm.ApplicationQuery::AddParameter(string key, string value, valuetype Microsoft.Crm.Application.Platform.Grid.GridParamRequirementLevel requiredLevel)
0x1a2d  ldarg.0
0x1a2e  ldfld    class ApiCommand Microsoft.Crm.ApplicationQuery::_apiCommand
0x1a33  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression ApiCommand::get_CurrentQueryExpression()
0x1a38  stloc.0
0x1a39  ldloc.0
0x1a3a  ldarg.0
0x1a3b  ldfld    bool Microsoft.Crm.ApplicationQuery::_noLock
0x1a40  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_NoLock(bool)
0x1a45  ldarg.0
0x1a46  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.ApplicationQuery::get_Parameters()
0x1a4b  ldstr    aTeamtemplateid// "teamTemplateId"
0x1a50  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1a55  stloc.1
0x1a56  ldarg.0
0x1a57  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.ApplicationQuery::get_Parameters()
0x1a5c  ldstr    aRelname// "relName"
0x1a61  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1a66  stloc.2
0x1a67  ldloc.1
0x1a68  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a6d  brtrue.s loc_1AAB
0x1a6f  ldloc.1
0x1a70  ldarg.0
0x1a71  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.ApplicationQuery::get_Parameters()
0x1a76  ldstr    aOid// "oId"
0x1a7b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1a80  newobj   instance void Microsoft.Crm.Application.Components.Platform.Data.TeamTemplateQueryDecorator::.ctor(string teamTemplateId, string recordId)
0x1a85  ldloc.0
0x1a86  callvirt instance void Microsoft.Crm.Application.Components.Platform.Data.TeamTemplateQueryDecorator::DecorateQuery(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query)
0x1a8b  ldloc.0
0x1a8c  ldarg.0
0x1a8d  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.ApplicationQuery::get_OrganizationContext()
0x1a92  call     string Microsoft.Crm.Application.Platform.DataSource::QueryExpressionToFetchXml(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1a97  stloc.s  0xA
0x1a99  ldarg.0
0x1a9a  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x1a9f  ldloc.s  0xA
0x1aa1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::DeserializeFromFetchXml(string)
0x1aa6  br       loc_1C4C
0x1aab  ldloc.2
0x1aac  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ab1  brtrue   loc_1C19
0x1ab6  ldarg.0
0x1ab7  ldfld    class ApiCommand Microsoft.Crm.ApplicationQuery::_apiCommand
0x1abc  callvirt instance bool ApiCommand::get_IsCustomRelationship()
0x1ac1  brtrue   loc_1C19
0x1ac6  ldloc.2
0x1ac7  ldstr    aImportfileAsyn// "ImportFile_AsyncOperations"
0x1acc  ldc.i4.4
0x1acd  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1ad2  brfalse  loc_1C19
0x1ad7  ldarg.0
0x1ad8  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.ApplicationQuery::get_Parameters()
0x1add  ldstr    aOtype// "oType"
0x1ae2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1ae7  ldarg.0
0x1ae8  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.ApplicationQuery::get_Parameters()
0x1aed  ldstr    aOid// "oId"
0x1af2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1af7  stloc.s  0xB
0x1af9  dup
0x1afa  ldarg.0
0x1afb  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.ApplicationQuery::get_OrganizationContext()
0x1b00  newobj   instance void Microsoft.Crm.Application.Platform.EntityType::.ctor(string logicalName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1b05  call     instance string Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x1b0a  stloc.s  0xD
0x1b0c  ldarg.0
0x1b0d  ldloc.s  0xD
0x1b0f  ldloc.s  0xB
0x1b11  ldloca.s 0xC
0x1b13  call     instance void Microsoft.Crm.ApplicationQuery::SetCustomQueryForDynamicList(string parentEntityName, string entityId, [out] class Microsoft.Crm.Application.Platform.Entity& list)
0x1b18  ldarg.0
0x1b19  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.ApplicationQuery::get_Parameters()
0x1b1e  ldstr    aRdependattr// "rDependAttr"
0x1b23  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b28  stloc.s  0xE
0x1b2a  ldarg.0
0x1b2b  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.ApplicationQuery::get_Parameters()
0x1b30  ldstr    aRoleord// "roleOrd"
0x1b35  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b3a  stloc.s  0xF
0x1b3c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b41  brtrue.s loc_1B4C
0x1b43  ldloc.s  0xB
0x1b45  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b4a  brfalse.s loc_1B57
0x1b4c  ldstr    aRelationshipBa// "Relationship based queries must define "...
0x1b51  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1b56  throw
0x1b57  ldloca.s 0x10
0x1b59  ldloc.s  0xB
0x1b5b  call     instance void [mscorlib]System.Guid::.ctor(string)
0x1b60  ldc.i4.m1
0x1b61  stloc.s  0x11
0x1b63  ldloc.s  0xF
0x1b65  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b6a  brtrue.s loc_1B7A
0x1b6c  ldloc.s  0xF
0x1b6e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b73  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x1b78  stloc.s  0x11
0x1b7a  ldloc.s  0xD
0x1b7c  ldloc.s  0x10
0x1b7e  ldloc.2
0x1b7f  ldloc.s  0x11
0x1b81  ldloc.s  0xE
0x1b83  ldarg.0
0x1b84  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.ApplicationQuery::_context
0x1b89  call     class Microsoft.Crm.Application.Platform.QueryDecorators.RetrieveByObjectQueryDecorator Microsoft.Crm.Application.Platform.QueryDecorators.RetrieveByObjectQueryDecorator::GetInstance(string parentEntityName, valuetype [mscorlib]System.Guid parentEntityId, string relationshipName, int32 relationshipRoleOrdinal, string dependentAttributeName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1b8e  stloc.s  0x12
0x1b90  ldarg.0
0x1b91  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x1b96  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x1b9b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1ba0  ldstr    aActivitymimeat// "activitymimeattachment"
0x1ba5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1baa  brfalse.s loc_1BB5
0x1bac  ldarg.0
  ... truncated ...
```
