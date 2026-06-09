# Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::BuildTableFillProperties

- ea: `0x5aaf0`
- end: `0x5ad79`
- name: `Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::BuildTableFillProperties`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x5a7d0`

## callees

- `0x51010`
- `0x5aaf0`
- `0xabc50`
- `0xabe20`
- `0xabf60`

## string_xrefs

- `0x5ad5c`: `Privilege`
- `0x5aaf8`: `There is no support for adding extra filtering WHERE conditions to filter the metadata data in the Multi Org Sharable cache loader!`
- `0x5ab42`: ` order by ComponentState asc`
- `0x5ab68`: ` order by ComponentState asc`
- `0x5ab8e`: ` order by ComponentState asc`
- `0x5abb4`: ` order by ComponentState asc`
- `0x5abda`: ` order by ComponentState asc`
- `0x5ac26`: ` order by ComponentState asc`
- `0x5ac4c`: ` order by ComponentState asc`
- `0x5ac72`: ` order by ComponentState asc`
- `0x5ac98`: ` order by ComponentState asc`
- `0x5acbe`: ` order by ComponentState asc`
- `0x5ace4`: ` order by ComponentState asc`
- `0x5ad0a`: ` order by ComponentState asc`
- `0x5ad34`: ` order by ComponentState asc`
- `0x5ac00`: ` order by ComponentState, DisplayOrder asc`
- `0x5ad61`: `select {0} from Privilege priv {1} left outer join PrivilegeObjectTypeCodes privotc {1} on (privotc.PrivilegeId = priv.PrivilegeId) left outer join Entity e on privotc.ObjectTypeCode = e.ObjectTypeCode`

## pseudocode

```c

```

## disassembly

```asm
0x5aaf0  ldarg.0
0x5aaf1  call     instance class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_ExtraWhereConditionsToFilterOutData()
0x5aaf6  brfalse.s loc_5AB03
0x5aaf8  ldstr    aThereIsNoSuppo// "There is no support for adding extra fi"...
0x5aafd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x5ab02  throw
0x5ab03  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg>::.ctor()
0x5ab08  ldarg.0
0x5ab09  ldfld    string Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::conditionWithSystemRows
0x5ab0e  ldarg.0
0x5ab0f  ldfld    string Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::conditionNoSystemRows
0x5ab14  ldarg.0
0x5ab15  ldfld    string Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::conditionOnlySystemRows
0x5ab1a  ldarg.0
0x5ab1b  ldfld    string Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::conditionOnlyPublishedNoSystemRows
0x5ab20  ldarg.0
0x5ab21  ldfld    string Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::conditionOnlyDeletedNoSystemRows
0x5ab26  newobj   instance void MultiOrgSharableSelectConditions::.ctor(string withSystemRows, string noSystemRows, string onlySystemRows, string onlyPublishedNoSystemRows, string onlyDeletedNoSystemRows)
0x5ab2b  stloc.0
0x5ab2c  dup
0x5ab2d  ldstr    aManagedpropert_5// "ManagedProperty"
0x5ab32  ldstr    aSelect0FromMan// "select {0} from ManagedProperty {1}"
0x5ab37  ldloc.0
0x5ab38  callvirt instance class MultiOrgSharableSelectConditions MultiOrgSharableSelectConditions::Clone()
0x5ab3d  ldstr    asc_D5A0E// "*"
0x5ab42  ldstr    aOrderByCompone// " order by ComponentState asc"
0x5ab47  ldnull
0x5ab48  newobj   instance void TableFillPropertiesMultiOrg::.ctor(string metadataEntityName, string selectCommand, class MultiOrgSharableSelectConditions selectConditions, [opt] string selectColumns, [opt] string selectOrderBy, [opt] string ifExistsCondition)
0x5ab4d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg>::Add(var<u1>)
0x5ab52  dup
0x5ab53  ldstr    aOptionset_0// "OptionSet"
0x5ab58  ldstr    aSelect0FromOpt// "select {0} from OptionSet {1}"
0x5ab5d  ldloc.0
0x5ab5e  callvirt instance class MultiOrgSharableSelectConditions MultiOrgSharableSelectConditions::Clone()
0x5ab63  ldstr    aConvertBigintV// "*, CONVERT(bigint, VersionNumber) AS Ti"...
0x5ab68  ldstr    aOrderByCompone// " order by ComponentState asc"
0x5ab6d  ldnull
0x5ab6e  newobj   instance void TableFillPropertiesMultiOrg::.ctor(string metadataEntityName, string selectCommand, class MultiOrgSharableSelectConditions selectConditions, [opt] string selectColumns, [opt] string selectOrderBy, [opt] string ifExistsCondition)
0x5ab73  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg>::Add(var<u1>)
0x5ab78  dup
0x5ab79  ldstr    aEntity_0// "Entity"
0x5ab7e  ldstr    aSelect0FromEnt// "select {0} from Entity {1}"
0x5ab83  ldloc.0
0x5ab84  callvirt instance class MultiOrgSharableSelectConditions MultiOrgSharableSelectConditions::Clone()
0x5ab89  ldstr    aConvertBigintV// "*, CONVERT(bigint, VersionNumber) AS Ti"...
0x5ab8e  ldstr    aOrderByCompone// " order by ComponentState asc"
0x5ab93  ldnull
0x5ab94  newobj   instance void TableFillPropertiesMultiOrg::.ctor(string metadataEntityName, string selectCommand, class MultiOrgSharableSelectConditions selectConditions, [opt] string selectColumns, [opt] string selectOrderBy, [opt] string ifExistsCondition)
0x5ab99  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg>::Add(var<u1>)
0x5ab9e  dup
0x5ab9f  ldstr    aAttribute// "Attribute"
0x5aba4  ldstr    aSelect0FromAtt// "select {0} from Attribute {1}"
0x5aba9  ldloc.0
0x5abaa  callvirt instance class MultiOrgSharableSelectConditions MultiOrgSharableSelectConditions::Clone()
0x5abaf  ldstr    aConvertBigintV// "*, CONVERT(bigint, VersionNumber) AS Ti"...
0x5abb4  ldstr    aOrderByCompone// " order by ComponentState asc"
0x5abb9  ldnull
0x5abba  newobj   instance void TableFillPropertiesMultiOrg::.ctor(string metadataEntityName, string selectCommand, class MultiOrgSharableSelectConditions selectConditions, [opt] string selectColumns, [opt] string selectOrderBy, [opt] string ifExistsCondition)
0x5abbf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg>::Add(var<u1>)
0x5abc4  dup
0x5abc5  ldstr    aAttributelooku// "AttributeLookupValue"
0x5abca  ldstr    aSelect0FromAtt_0// "select {0} from AttributeLookupValue {1"...
0x5abcf  ldloc.0
0x5abd0  callvirt instance class MultiOrgSharableSelectConditions MultiOrgSharableSelectConditions::Clone()
0x5abd5  ldstr    asc_D5A0E// "*"
0x5abda  ldstr    aOrderByCompone// " order by ComponentState asc"
0x5abdf  ldnull
0x5abe0  newobj   instance void TableFillPropertiesMultiOrg::.ctor(string metadataEntityName, string selectCommand, class MultiOrgSharableSelectConditions selectConditions, [opt] string selectColumns, [opt] string selectOrderBy, [opt] string ifExistsCondition)
0x5abe5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg>::Add(var<u1>)
0x5abea  dup
0x5abeb  ldstr    aAttributepickl// "AttributePicklistValue"
0x5abf0  ldstr    aSelect0FromAtt_1// "select {0} from AttributePicklistValue "...
0x5abf5  ldloc.0
0x5abf6  callvirt instance class MultiOrgSharableSelectConditions MultiOrgSharableSelectConditions::Clone()
0x5abfb  ldstr    asc_D5A0E// "*"
0x5ac00  ldstr    aOrderByCompone_0// " order by ComponentState, DisplayOrder "...
0x5ac05  ldnull
0x5ac06  newobj   instance void TableFillPropertiesMultiOrg::.ctor(string metadataEntityName, string selectCommand, class MultiOrgSharableSelectConditions selectConditions, [opt] string selectColumns, [opt] string selectOrderBy, [opt] string ifExistsCondition)
0x5ac0b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg>::Add(var<u1>)
0x5ac10  dup
0x5ac11  ldstr    aEntityrelation_0// "EntityRelationship"
0x5ac16  ldstr    aSelect0FromEnt_0// "select {0} from EntityRelationship {1}"
0x5ac1b  ldloc.0
0x5ac1c  callvirt instance class MultiOrgSharableSelectConditions MultiOrgSharableSelectConditions::Clone()
0x5ac21  ldstr    aConvertBigintV// "*, CONVERT(bigint, VersionNumber) AS Ti"...
0x5ac26  ldstr    aOrderByCompone// " order by ComponentState asc"
0x5ac2b  ldnull
0x5ac2c  newobj   instance void TableFillPropertiesMultiOrg::.ctor(string metadataEntityName, string selectCommand, class MultiOrgSharableSelectConditions selectConditions, [opt] string selectColumns, [opt] string selectOrderBy, [opt] string ifExistsCondition)
0x5ac31  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg>::Add(var<u1>)
0x5ac36  dup
0x5ac37  ldstr    aRelationship_0// "Relationship"
0x5ac3c  ldstr    aSelect0FromRel// "select {0} from Relationship {1}"
0x5ac41  ldloc.0
0x5ac42  callvirt instance class MultiOrgSharableSelectConditions MultiOrgSharableSelectConditions::Clone()
0x5ac47  ldstr    asc_D5A0E// "*"
0x5ac4c  ldstr    aOrderByCompone// " order by ComponentState asc"
0x5ac51  ldnull
0x5ac52  newobj   instance void TableFillPropertiesMultiOrg::.ctor(string metadataEntityName, string selectCommand, class MultiOrgSharableSelectConditions selectConditions, [opt] string selectColumns, [opt] string selectOrderBy, [opt] string ifExistsCondition)
0x5ac57  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg>::Add(var<u1>)
0x5ac5c  dup
0x5ac5d  ldstr    aRelationshipex_0// "RelationshipExtraCondition"
0x5ac62  ldstr    aSelect0FromRel_0// "select {0} from RelationshipExtraCondit"...
0x5ac67  ldloc.0
0x5ac68  callvirt instance class MultiOrgSharableSelectConditions MultiOrgSharableSelectConditions::Clone()
0x5ac6d  ldstr    asc_D5A0E// "*"
0x5ac72  ldstr    aOrderByCompone// " order by ComponentState asc"
0x5ac77  ldnull
0x5ac78  newobj   instance void TableFillPropertiesMultiOrg::.ctor(string metadataEntityName, string selectCommand, class MultiOrgSharableSelectConditions selectConditions, [opt] string selectColumns, [opt] string selectOrderBy, [opt] string ifExistsCondition)
0x5ac7d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg>::Add(var<u1>)
0x5ac82  dup
0x5ac83  ldstr    aEntityrelation_4// "EntityRelationshipRole"
0x5ac88  ldstr    aSelect0FromEnt_1// "select {0} from EntityRelationshipRole "...
0x5ac8d  ldloc.0
0x5ac8e  callvirt instance class MultiOrgSharableSelectConditions MultiOrgSharableSelectConditions::Clone()
0x5ac93  ldstr    asc_D5A0E// "*"
0x5ac98  ldstr    aOrderByCompone// " order by ComponentState asc"
0x5ac9d  ldnull
0x5ac9e  newobj   instance void TableFillPropertiesMultiOrg::.ctor(string metadataEntityName, string selectCommand, class MultiOrgSharableSelectConditions selectConditions, [opt] string selectColumns, [opt] string selectOrderBy, [opt] string ifExistsCondition)
0x5aca3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg>::Add(var<u1>)
0x5aca8  dup
0x5aca9  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x5acae  ldstr    aSelect0FromEnt_2// "select {0} from EntityRelationshipRelat"...
0x5acb3  ldloc.0
0x5acb4  callvirt instance class MultiOrgSharableSelectConditions MultiOrgSharableSelectConditions::Clone()
0x5acb9  ldstr    asc_D5A0E// "*"
0x5acbe  ldstr    aOrderByCompone// " order by ComponentState asc"
0x5acc3  ldnull
0x5acc4  newobj   instance void TableFillPropertiesMultiOrg::.ctor(string metadataEntityName, string selectCommand, class MultiOrgSharableSelectConditions selectConditions, [opt] string selectColumns, [opt] string selectOrderBy, [opt] string ifExistsCondition)
0x5acc9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg>::Add(var<u1>)
0x5acce  dup
0x5accf  ldstr    aViewattribute// "ViewAttribute"
0x5acd4  ldstr    aSelect0FromVie// "select {0} from ViewAttribute {1}"
0x5acd9  ldloc.0
0x5acda  callvirt instance class MultiOrgSharableSelectConditions MultiOrgSharableSelectConditions::Clone()
0x5acdf  ldstr    asc_D5A0E// "*"
0x5ace4  ldstr    aOrderByCompone// " order by ComponentState asc"
0x5ace9  ldnull
0x5acea  newobj   instance void TableFillPropertiesMultiOrg::.ctor(string metadataEntityName, string selectCommand, class MultiOrgSharableSelectConditions selectConditions, [opt] string selectColumns, [opt] string selectOrderBy, [opt] string ifExistsCondition)
0x5acef  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg>::Add(var<u1>)
0x5acf4  dup
0x5acf5  ldstr    aEntitykey_0// "EntityKey"
0x5acfa  ldstr    aSelect0FromEnt_3// "select {0} from EntityKey {1}"
0x5acff  ldloc.0
0x5ad00  callvirt instance class MultiOrgSharableSelectConditions MultiOrgSharableSelectConditions::Clone()
0x5ad05  ldstr    aConvertBigintV// "*, CONVERT(bigint, VersionNumber) AS Ti"...
0x5ad0a  ldstr    aOrderByCompone// " order by ComponentState asc"
0x5ad0f  ldsfld   string Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::entityKeyIfExistsCondition
0x5ad14  newobj   instance void TableFillPropertiesMultiOrg::.ctor(string metadataEntityName, string selectCommand, class MultiOrgSharableSelectConditions selectConditions, [opt] string selectColumns, [opt] string selectOrderBy, [opt] string ifExistsCondition)
0x5ad19  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg>::Add(var<u1>)
0x5ad1e  dup
0x5ad1f  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x5ad24  ldstr    aSelect0FromEnt_4// "select {0} from EntityKeyAttribute {1}"
0x5ad29  ldloc.0
0x5ad2a  callvirt instance class MultiOrgSharableSelectConditions MultiOrgSharableSelectConditions::Clone()
0x5ad2f  ldstr    aConvertBigintV// "*, CONVERT(bigint, VersionNumber) AS Ti"...
0x5ad34  ldstr    aOrderByCompone// " order by ComponentState asc"
0x5ad39  ldsfld   string Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::entityKeyAttributeIfExistsCondition
0x5ad3e  newobj   instance void TableFillPropertiesMultiOrg::.ctor(string metadataEntityName, string selectCommand, class MultiOrgSharableSelectConditions selectConditions, [opt] string selectColumns, [opt] string selectOrderBy, [opt] string ifExistsCondition)
0x5ad43  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg>::Add(var<u1>)
0x5ad48  ldnull
0x5ad49  ldnull
0x5ad4a  ldstr    aWhereIscustome// "where IsCustomEntity = 0"
0x5ad4f  ldnull
0x5ad50  ldstr    aWhere12// "where 1=2"
0x5ad55  newobj   instance void MultiOrgSharableSelectConditions::.ctor(string withSystemRows, string noSystemRows, string onlySystemRows, string onlyPublishedNoSystemRows, string onlyDeletedNoSystemRows)
0x5ad5a  stloc.1
0x5ad5b  dup
0x5ad5c  ldstr    aPrivilege// "Privilege"
0x5ad61  ldstr    aSelect0FromPri// "select {0} from Privilege priv {1} left"...
0x5ad66  ldloc.1
0x5ad67  ldstr    aPrivPrivotcObj// "priv.*, privotc.ObjectTypeCode, e.IsCus"...
0x5ad6c  ldnull
0x5ad6d  ldnull
0x5ad6e  newobj   instance void TableFillPropertiesMultiOrg::.ctor(string metadataEntityName, string selectCommand, class MultiOrgSharableSelectConditions selectConditions, [opt] string selectColumns, [opt] string selectOrderBy, [opt] string ifExistsCondition)
0x5ad73  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg>::Add(var<u1>)
0x5ad78  ret
```
