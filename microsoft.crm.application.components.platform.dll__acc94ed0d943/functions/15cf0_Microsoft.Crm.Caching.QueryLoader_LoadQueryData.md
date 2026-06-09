# Microsoft.Crm.Caching.QueryLoader::LoadQueryData

- ea: `0x15cf0`
- end: `0x161cd`
- name: `Microsoft.Crm.Caching.QueryLoader::LoadQueryData`
- size: `1245`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x15ce0`
- `0x7e7f0`

## callees

- `0x52f0`
- `0x5310`
- `0x5320`
- `0x5360`
- `0x5520`
- `0x5610`
- `0x56d0`
- `0x5f00`
- `0x115b0`
- `0x15cf0`
- `0x46a30`
- `0x46ae0`
- `0x46c30`
- `0x475c0`
- `0x57170`
- `0x572f0`
- `0x59720`
- `0x5bac0`
- `0x5be20`
- `0x5d670`

## string_xrefs

- `0x15cf9`: `fetchxml`
- `0x15db5`: `fetchxml`
- `0x15f7e`: `fetchxml`
- `0x15d9c`: `componentstate`
- `0x1617f`: `componentstate`
- `0x15d09`: `createdby`
- `0x15dc5`: `createdby`
- `0x15d11`: `columnsetxml`
- `0x15dcd`: `columnsetxml`
- `0x15f6b`: `columnsetxml`
- `0x15d42`: `createdon`
- `0x15dfe`: `createdon`
- `0x15d4b`: `layoutxml`
- `0x15e07`: `layoutxml`
- `0x15eea`: `layoutxml`
- `0x15d78`: `createdonbehalfby`
- `0x15e34`: `createdonbehalfby`
- `0x15f04`: `Cannot construct default layoutxml for Unknown entity.`

## pseudocode

```c

```

## disassembly

```asm
0x15cf0  ldc.i4.s 0x15
0x15cf2  newarr   [mscorlib]System.String
0x15cf7  dup
0x15cf8  ldc.i4.0
0x15cf9  ldstr    aFetchxml// "fetchxml"
0x15cfe  stelem.ref
0x15cff  dup
0x15d00  ldc.i4.1
0x15d01  ldstr    aStatecode// "statecode"
0x15d06  stelem.ref
0x15d07  dup
0x15d08  ldc.i4.2
0x15d09  ldstr    aCreatedby// "createdby"
0x15d0e  stelem.ref
0x15d0f  dup
0x15d10  ldc.i4.3
0x15d11  ldstr    aColumnsetxml// "columnsetxml"
0x15d16  stelem.ref
0x15d17  dup
0x15d18  ldc.i4.4
0x15d19  ldstr    aName// "name"
0x15d1e  stelem.ref
0x15d1f  dup
0x15d20  ldc.i4.5
0x15d21  ldstr    aQuerytype// "querytype"
0x15d26  stelem.ref
0x15d27  dup
0x15d28  ldc.i4.6
0x15d29  ldstr    aAdvancedgroupb// "advancedgroupby"
0x15d2e  stelem.ref
0x15d2f  dup
0x15d30  ldc.i4.7
0x15d31  ldstr    aModifiedby// "modifiedby"
0x15d36  stelem.ref
0x15d37  dup
0x15d38  ldc.i4.8
0x15d39  ldstr    aReturnedtypeco// "returnedtypecode"
0x15d3e  stelem.ref
0x15d3f  dup
0x15d40  ldc.i4.s 9
0x15d42  ldstr    aCreatedon// "createdon"
0x15d47  stelem.ref
0x15d48  dup
0x15d49  ldc.i4.s 0xA
0x15d4b  ldstr    aLayoutxml// "layoutxml"
0x15d50  stelem.ref
0x15d51  dup
0x15d52  ldc.i4.s 0xB
0x15d54  ldstr    aDescription_0// "description"
0x15d59  stelem.ref
0x15d5a  dup
0x15d5b  ldc.i4.s 0xC
0x15d5d  ldstr    aModifiedonbeha// "modifiedonbehalfby"
0x15d62  stelem.ref
0x15d63  dup
0x15d64  ldc.i4.s 0xD
0x15d66  ldstr    aConditionalfor// "conditionalformatting"
0x15d6b  stelem.ref
0x15d6c  dup
0x15d6d  ldc.i4.s 0xE
0x15d6f  ldstr    aStatuscode// "statuscode"
0x15d74  stelem.ref
0x15d75  dup
0x15d76  ldc.i4.s 0xF
0x15d78  ldstr    aCreatedonbehal// "createdonbehalfby"
0x15d7d  stelem.ref
0x15d7e  dup
0x15d7f  ldc.i4.s 0x10
0x15d81  ldstr    aModifiedon// "modifiedon"
0x15d86  stelem.ref
0x15d87  dup
0x15d88  ldc.i4.s 0x11
0x15d8a  ldstr    aVersionnumber// "versionnumber"
0x15d8f  stelem.ref
0x15d90  dup
0x15d91  ldc.i4.s 0x12
0x15d93  ldstr    aQueryapi_0// "queryapi"
0x15d98  stelem.ref
0x15d99  dup
0x15d9a  ldc.i4.s 0x13
0x15d9c  ldstr    aComponentstate// "componentstate"
0x15da1  stelem.ref
0x15da2  dup
0x15da3  ldc.i4.s 0x14
0x15da5  ldstr    aSolutionid_0// "solutionid"
0x15daa  stelem.ref
0x15dab  stloc.0
0x15dac  ldc.i4.s 0x12
0x15dae  newarr   [mscorlib]System.String
0x15db3  dup
0x15db4  ldc.i4.0
0x15db5  ldstr    aFetchxml// "fetchxml"
0x15dba  stelem.ref
0x15dbb  dup
0x15dbc  ldc.i4.1
0x15dbd  ldstr    aStatecode// "statecode"
0x15dc2  stelem.ref
0x15dc3  dup
0x15dc4  ldc.i4.2
0x15dc5  ldstr    aCreatedby// "createdby"
0x15dca  stelem.ref
0x15dcb  dup
0x15dcc  ldc.i4.3
0x15dcd  ldstr    aColumnsetxml// "columnsetxml"
0x15dd2  stelem.ref
0x15dd3  dup
0x15dd4  ldc.i4.4
0x15dd5  ldstr    aName// "name"
0x15dda  stelem.ref
0x15ddb  dup
0x15ddc  ldc.i4.5
0x15ddd  ldstr    aQuerytype// "querytype"
0x15de2  stelem.ref
0x15de3  dup
0x15de4  ldc.i4.6
0x15de5  ldstr    aAdvancedgroupb// "advancedgroupby"
0x15dea  stelem.ref
0x15deb  dup
0x15dec  ldc.i4.7
0x15ded  ldstr    aModifiedby// "modifiedby"
0x15df2  stelem.ref
0x15df3  dup
0x15df4  ldc.i4.8
0x15df5  ldstr    aReturnedtypeco// "returnedtypecode"
0x15dfa  stelem.ref
0x15dfb  dup
0x15dfc  ldc.i4.s 9
0x15dfe  ldstr    aCreatedon// "createdon"
0x15e03  stelem.ref
0x15e04  dup
0x15e05  ldc.i4.s 0xA
0x15e07  ldstr    aLayoutxml// "layoutxml"
0x15e0c  stelem.ref
0x15e0d  dup
0x15e0e  ldc.i4.s 0xB
0x15e10  ldstr    aDescription_0// "description"
0x15e15  stelem.ref
0x15e16  dup
0x15e17  ldc.i4.s 0xC
0x15e19  ldstr    aModifiedonbeha// "modifiedonbehalfby"
0x15e1e  stelem.ref
0x15e1f  dup
0x15e20  ldc.i4.s 0xD
0x15e22  ldstr    aConditionalfor// "conditionalformatting"
0x15e27  stelem.ref
0x15e28  dup
0x15e29  ldc.i4.s 0xE
0x15e2b  ldstr    aStatuscode// "statuscode"
0x15e30  stelem.ref
0x15e31  dup
0x15e32  ldc.i4.s 0xF
0x15e34  ldstr    aCreatedonbehal// "createdonbehalfby"
0x15e39  stelem.ref
0x15e3a  dup
0x15e3b  ldc.i4.s 0x10
0x15e3d  ldstr    aModifiedon// "modifiedon"
0x15e42  stelem.ref
0x15e43  dup
0x15e44  ldc.i4.s 0x11
0x15e46  ldstr    aVersionnumber// "versionnumber"
0x15e4b  stelem.ref
0x15e4c  stloc.1
0x15e4d  ldarg.0
0x15e4e  ldfld    string Microsoft.Crm.Caching.QueryLoader::_queryTypeEntityLogicalName
0x15e53  ldstr    aSavedquery// "savedquery"
0x15e58  ldc.i4.5
0x15e59  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x15e5e  ldc.i4.0
0x15e5f  ceq
0x15e61  stloc.2
0x15e62  ldarg.0
0x15e63  ldfld    string Microsoft.Crm.Caching.QueryLoader::_queryTypeEntityLogicalName
0x15e68  ldarg.1
0x15e69  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Caching.QueryCacheKey::get_ViewId()
0x15e6e  ldloc.2
0x15e6f  brtrue.s loc_15E74
0x15e71  ldloc.1
0x15e72  br.s     loc_15E75
0x15e74  ldloc.0
0x15e75  ldarg.3
0x15e76  ldarg.2
0x15e77  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.DataSource::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, string[] columns, bool retrieveLatest, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x15e7c  stloc.3
0x15e7d  ldloc.3
0x15e7e  ldstr    aVersionnumber// "versionnumber"
0x15e83  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x15e88  unbox.any [mscorlib]System.Int64
0x15e8d  stloc.s  4
0x15e8f  ldloc.3
0x15e90  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.Crm.Application.Platform.EntityBase::get_Properties()
0x15e95  ldstr    aVersionnumber// "versionnumber"
0x15e9a  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Remove(var<u1>)
0x15e9f  pop
0x15ea0  ldloc.3
0x15ea1  call     string Microsoft.Crm.Application.Platform.EntityProxy::Serialize(class Microsoft.Crm.Application.Platform.EntityProxy entity)
0x15ea6  stloc.s  5
0x15ea8  newobj   instance void Microsoft.Crm.ViewDetails::.ctor()
0x15ead  stloc.s  6
0x15eaf  ldarg.2
0x15eb0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x15eb5  stloc.s  7
0x15eb7  ldc.i4.0
0x15eb8  stloc.s  8
0x15eba  ldloc.s  5
0x15ebc  ldstr    aReturnedtypeco// "returnedtypecode"
0x15ec1  call     string Microsoft.Crm.Application.Utility.Util::GetNodeValue(string input, string searchName)
0x15ec6  stloc.s  9
0x15ec8  ldloc.s  9
0x15eca  ldstr    aNone// "none"
0x15ecf  ldc.i4.5
0x15ed0  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x15ed5  brfalse.s loc_15EE8
0x15ed7  ldloc.s  7
0x15ed9  ldloc.s  9
0x15edb  ldc.i4.1
0x15edc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x15ee1  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x15ee6  stloc.s  8
0x15ee8  ldloc.s  5
0x15eea  ldstr    aLayoutxml// "layoutxml"
0x15eef  call     string Microsoft.Crm.Application.Utility.Util::GetNodeValue(string input, string searchName)
0x15ef4  stloc.s  0xA
0x15ef6  ldloc.s  0xA
0x15ef8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15efd  brfalse.s loc_15F17
0x15eff  ldloc.s  8
0x15f01  ldc.i4.0
0x15f02  cgt.un
0x15f04  ldstr    aCannotConstruc// "Cannot construct default layoutxml for "...
0x15f09  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x15f0e  ldloc.s  8
0x15f10  call     string Microsoft.Crm.ViewUtility::GetDefaultLayoutXml(int32 objectTypeCode)
0x15f15  stloc.s  0xA
0x15f17  ldloc.s  6
0x15f19  ldarg.1
0x15f1a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Caching.QueryCacheKey::get_ViewId()
0x15f1f  call     string Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid guid)
0x15f24  stfld    string Microsoft.Crm.ViewDetails::ViewId
0x15f29  ldloc.s  6
0x15f2b  ldloc.s  5
0x15f2d  ldstr    aName// "name"
0x15f32  call     string Microsoft.Crm.Application.Utility.Util::GetNodeValue(string input, string searchName)
0x15f37  stfld    string Microsoft.Crm.ViewDetails::Title
0x15f3c  ldloc.s  6
0x15f3e  ldloc.s  0xA
0x15f40  ldstr    aGrid// "grid"
0x15f45  ldstr    aObject// "object"
0x15f4a  call     string Microsoft.Crm.Application.Utility.Util::GetAttrValue(string input, string nodeName, string attrName)
0x15f4f  stfld    string Microsoft.Crm.ViewDetails::ObjectTypeCode
0x15f54  ldloc.s  6
0x15f56  ldloc.s  5
0x15f58  ldstr    aQueryapi_0// "queryapi"
0x15f5d  call     string Microsoft.Crm.Application.Utility.Util::GetNodeValue(string input, string searchName)
0x15f62  stfld    string Microsoft.Crm.ViewDetails::QueryApi
0x15f67  ldloc.s  6
0x15f69  ldloc.s  5
0x15f6b  ldstr    aColumnsetxml// "columnsetxml"
0x15f70  call     string Microsoft.Crm.Application.Utility.Util::GetNodeValue(string input, string searchName)
0x15f75  stfld    string Microsoft.Crm.ViewDetails::ColumnXml
0x15f7a  ldloc.s  6
0x15f7c  ldloc.s  5
0x15f7e  ldstr    aFetchxml// "fetchxml"
0x15f83  call     string Microsoft.Crm.Application.Utility.Util::GetNodeValue(string input, string searchName)
0x15f88  stfld    string Microsoft.Crm.ViewDetails::FetchXml
0x15f8d  ldloc.s  6
0x15f8f  ldfld    string Microsoft.Crm.ViewDetails::FetchXml
0x15f94  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15f99  brtrue.s loc_15FC4
0x15f9b  ldloc.s  6
0x15f9d  ldloc.s  0xA
0x15f9f  ldloc.s  6
0x15fa1  ldfld    string Microsoft.Crm.ViewDetails::FetchXml
0x15fa6  ldloc.s  6
0x15fa8  ldfld    string Microsoft.Crm.ViewDetails::ObjectTypeCode
0x15fad  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15fb2  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x15fb7  ldarg.2
0x15fb8  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ColumnUtility::PopulateLayoutWithRelationshipInfo(string, string, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x15fbd  stfld    string Microsoft.Crm.ViewDetails::HeaderXml
0x15fc2  br.s     loc_15FCD
0x15fc4  ldloc.s  6
0x15fc6  ldloc.s  0xA
0x15fc8  stfld    string Microsoft.Crm.ViewDetails::HeaderXml
0x15fcd  ldloc.s  6
0x15fcf  ldloc.s  0xA
0x15fd1  ldstr    aGrid// "grid"
0x15fd6  ldstr    aJump_0// "jump"
0x15fdb  call     string Microsoft.Crm.Application.Utility.Util::GetAttrValue(string input, string nodeName, string attrName)
0x15fe0  stfld    string Microsoft.Crm.ViewDetails::JumpCriteria
0x15fe5  ldloc.s  6
0x15fe7  ldloc.s  5
0x15fe9  ldstr    aQuerytype// "querytype"
0x15fee  ldc.i4.m1
0x15fef  call     int32 Microsoft.Crm.Application.Utility.Util::GetNodeValueAsInt(string input, string searchName, int32 defaultValue)
0x15ff4  stfld    int32 Microsoft.Crm.ViewDetails::QueryType
0x15ff9  ldloc.s  6
0x15ffb  ldloc.s  0xA
0x15ffd  ldstr    aGrid// "grid"
0x16002  ldstr    aPreview// "preview"
0x16007  call     string Microsoft.Crm.Application.Utility.Util::GetAttrValue(string input, string nodeName, string attrName)
  ... truncated ...
```
