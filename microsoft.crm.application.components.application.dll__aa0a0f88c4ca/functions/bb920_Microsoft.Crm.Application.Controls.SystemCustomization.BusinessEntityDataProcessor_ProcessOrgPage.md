# Microsoft.Crm.Application.Controls.SystemCustomization.BusinessEntityDataProcessor::ProcessOrgPage

- ea: `0xbb920`
- end: `0xbbd88`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.BusinessEntityDataProcessor::ProcessOrgPage`
- size: `1128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xbb880`

## callees

- `0x7c10`
- `0xbb910`
- `0xbb920`
- `0xbbd90`

## string_xrefs

- `0xbbaa3`: `roletemplateid`
- `0xbbb83`: `roletemplateid`
- `0xbbb93`: `roletemplateid`
- `0xbb9a3`: `componentTypeFilter`
- `0xbb9bd`: `componentTypeFilter`
- `0xbb9f3`: `componentSubFilter`
- `0xbba0a`: `componentSubFilter`
- `0xbbbdb`: `fieldsecurityprofile`
- `0xbbbf3`: `fieldsecurityprofileid`
- `0xbbc01`: `fieldsecurityprofileid`

## pseudocode

```c

```

## disassembly

```asm
0xbb920  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Row>::.ctor()
0xbb925  stloc.0
0xbb926  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0xbb92b  stloc.1
0xbb92c  ldc.i4   0x7D0
0xbb931  ldarg.3
0xbb932  mul
0xbb933  stloc.s  6
0xbb935  br.s     loc_BB979
0xbb937  ldloc.1
0xbb938  ldarg.1
0xbb939  ldloc.s  6
0xbb93b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Row>::get_Item(!!T0)
0xbb940  ldfld    string[] Row::columns
0xbb945  ldc.i4.0
0xbb946  ldelem.ref
0xbb947  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xbb94c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0xbb951  ldloc.0
0xbb952  ldarg.1
0xbb953  ldloc.s  6
0xbb955  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Row>::get_Item(!!T0)
0xbb95a  ldfld    string[] Row::columns
0xbb95f  ldc.i4.0
0xbb960  ldelem.ref
0xbb961  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xbb966  ldarg.1
0xbb967  ldloc.s  6
0xbb969  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Row>::get_Item(!!T0)
0xbb96e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Row>::set_Item(var<u1>, !!T0)
0xbb973  ldloc.s  6
0xbb975  ldc.i4.1
0xbb976  add
0xbb977  stloc.s  6
0xbb979  ldloc.s  6
0xbb97b  ldc.i4   0x7D0
0xbb980  ldarg.3
0xbb981  ldc.i4.1
0xbb982  add
0xbb983  mul
0xbb984  bge.s    loc_BB990
0xbb986  ldloc.s  6
0xbb988  ldarg.1
0xbb989  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Row>::get_Count()
0xbb98e  blt.s    loc_BB937
0xbb990  ldc.i4.0
0xbb991  stloc.2
0xbb992  ldarg.0
0xbb993  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Controls.SystemCustomization.BusinessEntityDataProcessor::get_Parameters()
0xbb998  brfalse  loc_BBA23
0xbb99d  ldarg.0
0xbb99e  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Controls.SystemCustomization.BusinessEntityDataProcessor::get_Parameters()
0xbb9a3  ldstr    aComponenttypef// "componentTypeFilter"
0xbb9a8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xbb9ad  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbb9b2  brtrue.s loc_BBA23
0xbb9b4  ldc.i4.m1
0xbb9b5  stloc.s  7
0xbb9b7  ldarg.0
0xbb9b8  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Controls.SystemCustomization.BusinessEntityDataProcessor::get_Parameters()
0xbb9bd  ldstr    aComponenttypef// "componentTypeFilter"
0xbb9c2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xbb9c7  ldc.i4.7
0xbb9c8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb9cd  ldloca.s 7
0xbb9cf  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0xbb9d4  brfalse.s loc_BBA23
0xbb9d6  ldloc.s  7
0xbb9d8  brfalse.s loc_BBA23
0xbb9da  ldloc.s  7
0xbb9dc  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetObjectTypeCode(int32)
0xbb9e1  stloc.s  7
0xbb9e3  ldloc.s  7
0xbb9e5  ldarg.0
0xbb9e6  ldfld    int32 Microsoft.Crm.Application.Controls.SystemCustomization.BusinessEntityDataProcessor::_typeCode
0xbb9eb  bne.un.s loc_BBA23
0xbb9ed  ldarg.0
0xbb9ee  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Controls.SystemCustomization.BusinessEntityDataProcessor::get_Parameters()
0xbb9f3  ldstr    aComponentsubfi// "componentSubFilter"
0xbb9f8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xbb9fd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbba02  brtrue.s loc_BBA23
0xbba04  ldarg.0
0xbba05  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Controls.SystemCustomization.BusinessEntityDataProcessor::get_Parameters()
0xbba0a  ldstr    aComponentsubfi// "componentSubFilter"
0xbba0f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xbba14  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbba19  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xbba1e  ldc.i4.1
0xbba1f  bne.un.s loc_BBA23
0xbba21  ldc.i4.1
0xbba22  stloc.2
0xbba23  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xbba28  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0xbba2d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xbba32  stloc.3
0xbba33  ldloc.3
0xbba34  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbba39  ldarg.0
0xbba3a  ldfld    int32 Microsoft.Crm.Application.Controls.SystemCustomization.BusinessEntityDataProcessor::_typeCode
0xbba3f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xbba44  stloc.s  4
0xbba46  ldc.i4.2
0xbba47  newarr   [mscorlib]System.String
0xbba4c  dup
0xbba4d  ldc.i4.0
0xbba4e  ldloc.s  4
0xbba50  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0xbba55  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xbba5a  stelem.ref
0xbba5b  dup
0xbba5c  ldc.i4.1
0xbba5d  ldloc.s  4
0xbba5f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0xbba64  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xbba69  stelem.ref
0xbba6a  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0xbba6f  stloc.s  5
0xbba71  ldarg.0
0xbba72  call     instance bool Microsoft.Crm.Application.Controls.SystemCustomization.BusinessEntityDataProcessor::AddDescriptionColumn()
0xbba77  brfalse.s loc_BBA85
0xbba79  ldloc.s  5
0xbba7b  ldstr    aDescription// "description"
0xbba80  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xbba85  ldarg.0
0xbba86  ldfld    int32 Microsoft.Crm.Application.Controls.SystemCustomization.BusinessEntityDataProcessor::_typeCode
0xbba8b  ldstr    aRole// "role"
0xbba90  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbba95  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbba9a  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0xbba9f  bne.un.s loc_BBAAD
0xbbaa1  ldloc.s  5
0xbbaa3  ldstr    aRoletemplateid// "roletemplateid"
0xbbaa8  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xbbaad  ldloc.s  4
0xbbaaf  ldstr    aIscustomizable// "iscustomizable"
0xbbab4  ldc.i4.1
0xbbab5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xbbaba  brfalse.s loc_BBAC8
0xbbabc  ldloc.s  5
0xbbabe  ldstr    aIscustomizable// "iscustomizable"
0xbbac3  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xbbac8  ldloc.s  4
0xbbaca  ldstr    aIsmanaged// "ismanaged"
0xbbacf  ldc.i4.1
0xbbad0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xbbad5  brfalse.s loc_BBAE3
0xbbad7  ldloc.s  5
0xbbad9  ldstr    aIsmanaged// "ismanaged"
0xbbade  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xbbae3  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor()
0xbbae8  dup
0xbbae9  ldloc.s  4
0xbbaeb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xbbaf0  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_EntityName(string)
0xbbaf5  dup
0xbbaf6  ldloc.s  5
0xbbaf8  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0xbbafd  dup
0xbbafe  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0xbbb03  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0xbbb08  ldloc.s  4
0xbbb0a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0xbbb0f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xbbb14  ldc.i4.8
0xbbb15  ldloc.1
0xbbb16  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0xbbb1b  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0xbbb20  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xbbb25  pop
0xbbb26  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbbb2b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbbb30  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0xbbb35  stloc.s  8
0xbbb37  br       loc_BBD6D
0xbbb3c  ldloc.s  8
0xbbb3e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0xbbb43  stloc.s  9
0xbbb45  ldloc.0
0xbbb46  ldloc.s  9
0xbbb48  ldloc.s  4
0xbbb4a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0xbbb4f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xbbb54  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbbb59  unbox.any [mscorlib]System.Guid
0xbbb5e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Row>::get_Item(void)
0xbbb63  stloc.s  0xA
0xbbb65  ldarg.0
0xbbb66  ldfld    int32 Microsoft.Crm.Application.Controls.SystemCustomization.BusinessEntityDataProcessor::_typeCode
0xbbb6b  ldstr    aRole// "role"
0xbbb70  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbbb75  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbbb7a  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0xbbb7f  bne.un.s loc_BBBD5
0xbbb81  ldloc.s  9
0xbbb83  ldstr    aRoletemplateid// "roletemplateid"
0xbbb88  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbbb8d  brfalse.s loc_BBBD5
0xbbb8f  ldloca.s 0xB
0xbbb91  ldloc.s  9
0xbbb93  ldstr    aRoletemplateid// "roletemplateid"
0xbbb98  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbbb9d  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xbbba2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xbbba7  call     instance void [mscorlib]System.Guid::.ctor(string)
0xbbbac  ldloca.s 0xB
0xbbbae  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Utility.SolutionUtil::SupportUserRoleId
0xbbbb3  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xbbbb8  brtrue.s loc_BBBC8
0xbbbba  ldloca.s 0xB
0xbbbbc  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Utility.SolutionUtil::SystemAdminRoleId
0xbbbc1  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xbbbc6  brfalse.s loc_BBBD5
0xbbbc8  ldarg.2
0xbbbc9  ldloc.s  0xA
0xbbbcb  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Row>::Add(var<u1>)
0xbbbd0  br       loc_BBD6D
0xbbbd5  ldarg.0
0xbbbd6  ldfld    int32 Microsoft.Crm.Application.Controls.SystemCustomization.BusinessEntityDataProcessor::_typeCode
0xbbbdb  ldstr    aFieldsecurityp_0// "fieldsecurityprofile"
0xbbbe0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbbbe5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbbbea  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0xbbbef  bne.un.s loc_BBC2D
0xbbbf1  ldloc.s  9
0xbbbf3  ldstr    aFieldsecurityp_1// "fieldsecurityprofileid"
0xbbbf8  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbbbfd  brfalse.s loc_BBC2D
0xbbbff  ldloc.s  9
0xbbc01  ldstr    aFieldsecurityp_1// "fieldsecurityprofileid"
0xbbc06  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbbc0b  unbox.any [mscorlib]System.Guid
0xbbc10  stloc.s  0xC
0xbbc12  ldloca.s 0xC
0xbbc14  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::SystemFieldSecurityProfileId
0xbbc19  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xbbc1e  brfalse.s loc_BBC2D
0xbbc20  ldarg.2
0xbbc21  ldloc.s  0xA
0xbbc23  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Row>::Add(var<u1>)
0xbbc28  br       loc_BBD6D
0xbbc2d  ldloc.s  0xA
0xbbc2f  ldfld    string[] Row::columns
0xbbc34  ldc.i4.2
0xbbc35  ldloc.s  9
0xbbc37  ldloc.s  4
0xbbc39  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0xbbc3e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xbbc43  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbbc48  isinst   [mscorlib]System.String
0xbbc4d  stelem.ref
0xbbc4e  ldloc.s  0xA
0xbbc50  ldfld    string[] Row::columns
0xbbc55  ldc.i4.3
0xbbc56  ldloc.s  9
0xbbc58  ldloc.s  4
0xbbc5a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0xbbc5f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xbbc64  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbbc69  isinst   [mscorlib]System.String
0xbbc6e  stelem.ref
0xbbc6f  ldarg.0
0xbbc70  ldfld    int32 Microsoft.Crm.Application.Controls.SystemCustomization.BusinessEntityDataProcessor::_typeCode
0xbbc75  ldstr    aRole// "role"
0xbbc7a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbbc7f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbbc84  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0xbbc89  beq.s    loc_BBCAD
0xbbc8b  ldloc.s  9
0xbbc8d  ldstr    aDescription// "description"
0xbbc92  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbbc97  isinst   [mscorlib]System.String
0xbbc9c  stloc.s  0xD
0xbbc9e  ldloc.s  0xD
0xbbca0  brfalse.s loc_BBCAD
0xbbca2  ldloc.s  0xA
0xbbca4  ldfld    string[] Row::columns
0xbbca9  ldc.i4.5
0xbbcaa  ldloc.s  0xD
0xbbcac  stelem.ref
0xbbcad  ldloc.s  9
0xbbcaf  ldstr    aIsmanaged// "ismanaged"
0xbbcb4  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0xbbcb9  brfalse.s loc_BBCDB
0xbbcbb  ldloc.s  0xA
0xbbcbd  ldfld    string[] Row::columns
0xbbcc2  ldc.i4.s 9
0xbbcc4  ldloc.s  9
0xbbcc6  ldstr    aIsmanaged// "ismanaged"
0xbbccb  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbbcd0  unbox.any [mscorlib]System.Boolean
0xbbcd5  call     string Microsoft.Crm.Utility.SolutionUtil::GetComponentManagedStateText(bool isManaged)
0xbbcda  stelem.ref
0xbbcdb  ldloc.s  9
0xbbcdd  ldstr    aIscustomizable// "iscustomizable"
0xbbce2  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0xbbce7  brfalse.s loc_BBD3D
0xbbce9  ldloc.2
0xbbcea  ldc.i4.1
0xbbceb  bne.un.s loc_BBD1D
  ... truncated ...
```
