# Microsoft.Crm.Application.Utility.MailMergeUtility::RetrieveQueryExpression

- ea: `0x3f180`
- end: `0x3f492`
- name: `Microsoft.Crm.Application.Utility.MailMergeUtility::RetrieveQueryExpression`
- size: `786`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3dcf0`

## callees

- `0xfd20`
- `0x2fb90`
- `0x2fbc0`
- `0x3a980`
- `0x3ed20`
- `0x3f180`
- `0x3f6e0`
- `0x3f850`
- `0x3fb50`
- `0x59710`
- `0x5a330`
- `0x5b8b0`

## string_xrefs

- `0x3f3a8`: `fetchxml`
- `0x3f3be`: `fetchxml`
- `0x3f35e`: `/grid/parameters/fetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x3f180  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0x3f185  stloc.0
0x3f186  ldarg.0
0x3f187  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.Utility.MailMergeUtility::_metadata
0x3f18c  ldarg.1
0x3f18d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x3f192  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x3f197  stloc.1
0x3f198  ldarg.2
0x3f199  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3f19e  brtrue.s loc_3F1EB
0x3f1a0  ldarg.2
0x3f1a1  call     class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Application.Utility.MailMergeUtility::StringToGuidList(string idsParameter)
0x3f1a6  stloc.3
0x3f1a7  ldloc.0
0x3f1a8  ldloc.1
0x3f1a9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0x3f1ae  ldloc.0
0x3f1af  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x3f1b4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0x3f1b9  ldarg.0
0x3f1ba  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.Utility.MailMergeUtility::_metadata
0x3f1bf  ldloc.1
0x3f1c0  ldc.i4.1
0x3f1c1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x3f1c6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x3f1cb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x3f1d0  ldc.i4.8
0x3f1d1  ldloc.3
0x3f1d2  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Collections.ICollection)
0x3f1d7  stloc.s  4
0x3f1d9  ldloc.0
0x3f1da  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x3f1df  ldloc.s  4
0x3f1e1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression)
0x3f1e6  br       loc_3F472
0x3f1eb  ldarg.3
0x3f1ec  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3f1f1  brtrue   loc_3F472
0x3f1f6  ldarg.3
0x3f1f7  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x3f1fc  stloc.s  5
0x3f1fe  ldc.i4.0
0x3f1ff  stloc.s  6
0x3f201  ldarg.s  4
0x3f203  brfalse.s loc_3F222
0x3f205  ldloc.s  5
0x3f207  ldstr    aGridPagenum// "/grid/pageNum"
0x3f20c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3f211  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3f216  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3f21b  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3f220  stloc.s  6
0x3f222  ldloc.s  5
0x3f224  ldstr    aGridParameters// "/grid/parameters/viewid"
0x3f229  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3f22e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3f233  stloc.s  7
0x3f235  ldloc.s  5
0x3f237  ldstr    aGridParameters_0// "/grid/parameters/viewtype"
0x3f23c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3f241  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3f246  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3f24b  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3f250  stloc.s  8
0x3f252  ldloc.s  5
0x3f254  ldstr    aGridParameters_1// "/grid/parameters/oId"
0x3f259  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3f25e  stloc.s  9
0x3f260  ldloc.s  9
0x3f262  brfalse  loc_3F35C
0x3f267  ldloca.s 0xA
0x3f269  ldloc.s  9
0x3f26b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3f270  call     instance void [mscorlib]System.Guid::.ctor(string)
0x3f275  ldloc.s  5
0x3f277  ldstr    aGridParameters_2// "/grid/parameters/oType"
0x3f27c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3f281  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3f286  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3f28b  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3f290  stloc.s  0xB
0x3f292  ldloc.s  5
0x3f294  ldstr    aGridParameters_3// "/grid/parameters/relName"
0x3f299  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3f29e  stloc.s  0xC
0x3f2a0  ldloc.s  5
0x3f2a2  ldstr    aGridParameters_4// "/grid/parameters/roleOrd"
0x3f2a7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3f2ac  stloc.s  0xD
0x3f2ae  ldloc.s  0xC
0x3f2b0  brfalse.s loc_3F2B6
0x3f2b2  ldloc.s  0xD
0x3f2b4  brtrue.s loc_3F2BD
0x3f2b6  ldsfld   string [mscorlib]System.String::Empty
0x3f2bb  br.s     loc_3F2C4
0x3f2bd  ldloc.s  0xC
0x3f2bf  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3f2c4  stloc.s  0xE
0x3f2c6  ldloc.s  0xE
0x3f2c8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3f2cd  brtrue.s loc_3F2D3
0x3f2cf  ldloc.s  0xD
0x3f2d1  brtrue.s loc_3F2D6
0x3f2d3  ldc.i4.m1
0x3f2d4  br.s     loc_3F2E7
0x3f2d6  ldloc.s  0xD
0x3f2d8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3f2dd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3f2e2  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3f2e7  stloc.s  0xF
0x3f2e9  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3f2ee  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x3f2f3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x3f2f8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3f2fd  ldloc.s  0xB
0x3f2ff  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x3f304  stloc.s  0x10
0x3f306  ldloc.1
0x3f307  ldloc.s  0x10
0x3f309  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x3f30e  ldloc.s  0xA
0x3f310  ldloc.s  0xE
0x3f312  ldloc.s  0xF
0x3f314  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression Microsoft.Crm.Application.Utility.MailMergeUtility::GetAssociatedQuery(string targetEntity, string parentEntity, valuetype [mscorlib]System.Guid parentEntityId, string relationshipName, int32 relationshipRoleOrdinal)
0x3f319  stloc.0
0x3f31a  ldarg.0
0x3f31b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.Utility.MailMergeUtility::_metadata
0x3f320  ldloc.1
0x3f321  ldc.i4.1
0x3f322  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x3f327  ldstr    aStatecode// "statecode"
0x3f32c  ldc.i4.1
0x3f32d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x3f332  brfalse  loc_3F440
0x3f337  ldloc.0
0x3f338  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x3f33d  ldstr    aStatecode// "statecode"
0x3f342  ldc.i4.0
0x3f343  ldc.i4.1
0x3f344  newarr   [mscorlib]System.Object
0x3f349  dup
0x3f34a  ldc.i4.0
0x3f34b  ldc.i4.0
0x3f34c  box      [mscorlib]System.Int32
0x3f351  stelem.ref
0x3f352  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x3f357  br       loc_3F440
0x3f35c  ldloc.s  5
0x3f35e  ldstr    aGridParameters_5// "/grid/parameters/fetchXml"
0x3f363  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3f368  stloc.s  0x11
0x3f36a  ldloc.s  0x11
0x3f36c  brfalse.s loc_3F377
0x3f36e  ldloc.s  0x11
0x3f370  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3f375  br.s     loc_3F37C
0x3f377  ldsfld   string [mscorlib]System.String::Empty
0x3f37c  stloc.s  0x12
0x3f37e  ldloc.s  0x12
0x3f380  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3f385  brfalse.s loc_3F3CF
0x3f387  ldarg.0
0x3f388  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.Utility.MailMergeUtility::_metadata
0x3f38d  ldloc.s  8
0x3f38f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x3f394  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x3f399  ldloc.s  7
0x3f39b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3f3a0  ldc.i4.1
0x3f3a1  newarr   [mscorlib]System.String
0x3f3a6  dup
0x3f3a7  ldc.i4.0
0x3f3a8  ldstr    aFetchxml// "fetchxml"
0x3f3ad  stelem.ref
0x3f3ae  ldarg.0
0x3f3af  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Utility.MailMergeUtility::_orgContext
0x3f3b4  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.DataSource::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, string[] columns, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3f3b9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Application.Platform.EntityBase::get_InnerEntity()
0x3f3be  ldstr    aFetchxml// "fetchxml"
0x3f3c3  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3f3c8  castclass [mscorlib]System.String
0x3f3cd  stloc.s  0x12
0x3f3cf  ldloc.s  5
0x3f3d1  ldstr    aGridParameters_6// "/grid/parameters/quickfind"
0x3f3d6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3f3db  stloc.s  0x13
0x3f3dd  ldloc.s  0x13
0x3f3df  brfalse.s loc_3F431
0x3f3e1  ldloc.s  0x13
0x3f3e3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3f3e8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3f3ed  brtrue.s loc_3F431
0x3f3ef  ldarg.1
0x3f3f0  ldloc.s  0x12
0x3f3f2  ldarg.0
0x3f3f3  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Utility.MailMergeUtility::_orgContext
0x3f3f8  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.QuickFindUtil::FixQuickFindFilter(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3f3fd  stloc.s  0x12
0x3f3ff  ldc.i4.0
0x3f400  stloc.s  0x14
0x3f402  ldloc.s  0x13
0x3f404  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3f409  ldloca.s 0x14
0x3f40b  ldloc.s  0x12
0x3f40d  ldarg.1
0x3f40e  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x3f413  ldarg.0
0x3f414  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Utility.MailMergeUtility::_orgContext
0x3f419  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.QuickFindUtil::ProcessQuickFindSearchCriteria(string, bool&, string, int32, class [mscorlib]System.Globalization.CultureInfo, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3f41e  stloc.s  0x15
0x3f420  ldloc.s  0x14
0x3f422  brfalse.s loc_3F431
0x3f424  ldloc.s  0x15
0x3f426  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3f42b  brtrue.s loc_3F431
0x3f42d  ldloc.s  0x15
0x3f42f  stloc.s  0x12
0x3f431  ldloc.s  0x12
0x3f433  ldc.i4.1
0x3f434  ldarg.0
0x3f435  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Utility.MailMergeUtility::_orgContext
0x3f43a  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression Microsoft.Crm.Application.Platform.DataSource::FetchXmlToQueryExpression(string fetchXml, bool xrmQuery, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3f43f  stloc.0
0x3f440  ldloc.s  6
0x3f442  ldc.i4.0
0x3f443  ble.s    loc_3F472
0x3f445  ldloc.0
0x3f446  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo::.ctor()
0x3f44b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_PageInfo(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo)
0x3f450  ldloc.0
0x3f451  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_PageInfo()
0x3f456  ldloc.s  6
0x3f458  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo::set_PageNumber(int32)
0x3f45d  ldloc.0
0x3f45e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_PageInfo()
0x3f463  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser Microsoft.Crm.Security.User::get_Current()
0x3f468  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_RecordsPerPage()
0x3f46d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo::set_Count(int32)
0x3f472  ldnull
0x3f473  stloc.2
0x3f474  ldarg.s  6
0x3f476  brfalse.s loc_3F483
0x3f478  ldarg.1
0x3f479  ldarg.s  5
0x3f47b  ldloc.0
0x3f47c  ldc.i4.0
0x3f47d  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression Microsoft.Crm.Application.Utility.MailMergeUtility::AddPrivacyConditions(int32 otc, int32 mergeType, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query, bool privacyValue)
0x3f482  stloc.2
0x3f483  ldarg.s  7
0x3f485  brfalse.s loc_3F490
0x3f487  ldarg.1
0x3f488  ldloc.0
0x3f489  ldc.i4.0
0x3f48a  ldloc.2
0x3f48b  call     void Microsoft.Crm.Application.Utility.MailMergeUtility::AddActiveRecordsCondition(int32 otc, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query, bool activeRecordsConditionValue, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression privacyFilter)
0x3f490  ldloc.0
0x3f491  ret
```
