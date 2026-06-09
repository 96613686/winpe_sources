# Microsoft.Crm.Caching.SimilarityRulesData::GetSimilarityRuleFromRuleSet

- ea: `0x8f6d0`
- end: `0x8f8ba`
- name: `Microsoft.Crm.Caching.SimilarityRulesData::GetSimilarityRuleFromRuleSet`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8f690`

## callees

- `0x4440`
- `0x13470`
- `0x16a70`
- `0x49380`
- `0x4de70`
- `0x4e050`
- `0x4e2a0`
- `0x81f50`
- `0x81f60`
- `0x8f240`
- `0x8f6d0`
- `0x8f910`
- `0x8f930`
- `0x8f950`
- `0x8f970`
- `0x8f990`
- `0x8f9b0`
- `0x8f9d0`
- `0x8f9e0`
- `0x8f9f0`
- `0x8fa10`
- `0x8fa20`

## string_xrefs

- `0x8f862`: `activerulefetchxml`
- `0x8f870`: `activerulefetchxml`
- `0x8f885`: `ruleconditionxml`
- `0x8f893`: `ruleconditionxml`

## pseudocode

```c

```

## disassembly

```asm
0x8f6d0  ldarg.1
0x8f6d1  callvirt instance class Microsoft.Crm.Caching.ICacheEntityWrapper Microsoft.Crm.Caching.SimilarityRuleSet::get_SimilarityRule()
0x8f6d6  brtrue.s loc_8F6DA
0x8f6d8  ldnull
0x8f6d9  ret
0x8f6da  ldarg.1
0x8f6db  callvirt instance class Microsoft.Crm.Caching.ICacheEntityWrapper Microsoft.Crm.Caching.SimilarityRuleSet::get_SimilarityRule()
0x8f6e0  stloc.0
0x8f6e1  newobj   instance void Microsoft.Crm.Caching.ShareableSimilarityRule::.ctor()
0x8f6e6  stloc.1
0x8f6e7  ldloc.0
0x8f6e8  ldstr    aSimilarityrule// "similarityruleid"
0x8f6ed  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8f6f2  brtrue.s loc_8F70A
0x8f6f4  ldloc.1
0x8f6f5  ldloc.0
0x8f6f6  ldstr    aSimilarityrule// "similarityruleid"
0x8f6fb  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8f700  unbox.any [mscorlib]System.Guid
0x8f705  callvirt instance void Microsoft.Crm.Caching.ShareableSimilarityRule::set_Id(valuetype [mscorlib]System.Guid value)
0x8f70a  ldloc.0
0x8f70b  ldstr    aName_0// "name"
0x8f710  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8f715  brtrue.s loc_8F72D
0x8f717  ldloc.1
0x8f718  ldloc.0
0x8f719  ldstr    aName_0// "name"
0x8f71e  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8f723  castclass [mscorlib]System.String
0x8f728  callvirt instance void Microsoft.Crm.Caching.ShareableSimilarityRule::set_Name(string value)
0x8f72d  ldloc.0
0x8f72e  ldstr    aStatecode// "statecode"
0x8f733  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8f738  brtrue   loc_8F7F8
0x8f73d  ldloc.0
0x8f73e  ldstr    aStatecode// "statecode"
0x8f743  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8f748  stloc.2
0x8f749  ldloc.2
0x8f74a  isinst   [mscorlib]System.Int32
0x8f74f  brfalse.s loc_8F76C
0x8f751  ldloc.1
0x8f752  ldloc.0
0x8f753  ldstr    aStatecode// "statecode"
0x8f758  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8f75d  unbox.any [mscorlib]System.Int32
0x8f762  callvirt instance void Microsoft.Crm.Caching.ShareableSimilarityRule::set_StateCode(int32 value)
0x8f767  br       loc_8F7F8
0x8f76c  ldloc.2
0x8f76d  isinst   [mscorlib]System.String
0x8f772  brfalse  loc_8F7F8
0x8f777  ldloc.2
0x8f778  isinst   [mscorlib]System.String
0x8f77d  stloc.3
0x8f77e  ldarg.0
0x8f77f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.SimilarityRulesData::_organizationId
0x8f784  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x8f789  call     class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x8f78e  ldstr    aSimilarityrule_0// "SimilarityRule"
0x8f793  ldc.i4.0
0x8f794  callvirt instance class Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string entityName, valuetype Microsoft.Crm.Metadata.NameMappingType mapping)
0x8f799  callvirt instance class Microsoft.Crm.Metadata.IAttributeMetadataCollection Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x8f79e  ldstr    aStatecode// "statecode"
0x8f7a3  callvirt instance var<u1> class Microsoft.Crm.Metadata.IMetadataHashtable`1<class Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x8f7a8  isinst   Microsoft.Crm.Metadata.StateAttributeMetadata
0x8f7ad  callvirt instance class Microsoft.Crm.Metadata.IStateOptionsByValueCollection Microsoft.Crm.Metadata.StateAttributeMetadata::get_StateOptions()
0x8f7b2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Metadata.StateOption>::GetEnumerator()
0x8f7b7  stloc.s  4
0x8f7b9  br.s     loc_8F7E1
0x8f7bb  ldloc.s  4
0x8f7bd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Metadata.StateOption>::get_Current()
0x8f7c2  stloc.s  5
0x8f7c4  ldloc.s  5
0x8f7c6  callvirt instance string Microsoft.Crm.Metadata.StateOption::get_InvariantName()
0x8f7cb  ldloc.3
0x8f7cc  ldc.i4.5
0x8f7cd  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x8f7d2  brtrue.s loc_8F7E1
0x8f7d4  ldloc.1
0x8f7d5  ldloc.s  5
0x8f7d7  callvirt instance int32 Microsoft.Crm.Metadata.EnumOption::get_Value()
0x8f7dc  callvirt instance void Microsoft.Crm.Caching.ShareableSimilarityRule::set_StateCode(int32 value)
0x8f7e1  ldloc.s  4
0x8f7e3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8f7e8  brtrue.s loc_8F7BB
0x8f7ea  leave.s  loc_8F7F8
0x8f7ec  ldloc.s  4
0x8f7ee  brfalse.s loc_8F7F7
0x8f7f0  ldloc.s  4
0x8f7f2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8f7f7  endfinally
0x8f7f8  ldloc.0
0x8f7f9  ldstr    aBaseentityname// "baseentityname"
0x8f7fe  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8f803  brtrue.s loc_8F81B
0x8f805  ldloc.1
0x8f806  ldloc.0
0x8f807  ldstr    aBaseentityname// "baseentityname"
0x8f80c  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8f811  castclass [mscorlib]System.String
0x8f816  callvirt instance void Microsoft.Crm.Caching.ShareableSimilarityRule::set_BaseEntityLogicalName(string value)
0x8f81b  ldloc.0
0x8f81c  ldstr    aMatchingentity_0// "matchingentityname"
0x8f821  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8f826  brtrue.s loc_8F83E
0x8f828  ldloc.1
0x8f829  ldloc.0
0x8f82a  ldstr    aMatchingentity_0// "matchingentityname"
0x8f82f  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8f834  castclass [mscorlib]System.String
0x8f839  callvirt instance void Microsoft.Crm.Caching.ShareableSimilarityRule::set_MatchingEntityLogicalName(string value)
0x8f83e  ldloc.0
0x8f83f  ldstr    aExcludeinactiv// "excludeinactiverecords"
0x8f844  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8f849  brtrue.s loc_8F861
0x8f84b  ldloc.1
0x8f84c  ldloc.0
0x8f84d  ldstr    aExcludeinactiv// "excludeinactiverecords"
0x8f852  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8f857  unbox.any [mscorlib]System.Boolean
0x8f85c  callvirt instance void Microsoft.Crm.Caching.ShareableSimilarityRule::set_ExcludeInactiveRecords(bool value)
0x8f861  ldloc.0
0x8f862  ldstr    aActiverulefetc// "activerulefetchxml"
0x8f867  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8f86c  brtrue.s loc_8F884
0x8f86e  ldloc.1
0x8f86f  ldloc.0
0x8f870  ldstr    aActiverulefetc// "activerulefetchxml"
0x8f875  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8f87a  unbox.any [mscorlib]System.Boolean
0x8f87f  callvirt instance void Microsoft.Crm.Caching.ShareableSimilarityRule::set_ActiveRuleFetchXml(bool value)
0x8f884  ldloc.0
0x8f885  ldstr    aRuleconditionx// "ruleconditionxml"
0x8f88a  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8f88f  brtrue.s loc_8F8B8
0x8f891  ldloc.1
0x8f892  ldloc.0
0x8f893  ldstr    aRuleconditionx// "ruleconditionxml"
0x8f898  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8f89d  castclass [mscorlib]System.String
0x8f8a2  callvirt instance void Microsoft.Crm.Caching.ShareableSimilarityRule::set_RuleConditionXml(string value)
0x8f8a7  ldloc.1
0x8f8a8  ldloc.1
0x8f8a9  callvirt instance string Microsoft.Crm.Caching.ShareableSimilarityRule::get_RuleConditionXml()
0x8f8ae  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.SimilarityRuleCondition> Microsoft.Crm.SimilarityRuleCondition::ConvertConditionXmlToSimilarityRuleConditions(string conditionXml)
0x8f8b3  callvirt instance void Microsoft.Crm.Caching.ShareableSimilarityRule::set_SimilarityRuleConditions(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.SimilarityRuleCondition> value)
0x8f8b8  ldloc.1
0x8f8b9  ret
```
