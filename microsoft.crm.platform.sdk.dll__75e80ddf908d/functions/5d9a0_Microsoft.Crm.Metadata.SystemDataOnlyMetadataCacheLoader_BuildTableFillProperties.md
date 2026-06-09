# Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::BuildTableFillProperties

- ea: `0x5d9a0`
- end: `0x5dc9c`
- name: `Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::BuildTableFillProperties`
- size: `764`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x51fe0`
- `0x5d9a0`

## string_xrefs

- `0x5dbdf`: `Privilege`
- `0x5dc05`: `PrivilegeObjectTypeCode`
- `0x5dc35`: `RoleTemplatePrivilege`
- `0x5dbe4`: `select {0} from Privilege priv left outer join PrivilegeObjectTypeCodes privotc on (privotc.PrivilegeId = priv.PrivilegeId) where privotc.ObjectTypeCode <= 9999`
- `0x5dc0a`: `select {0} from PrivilegeObjectTypeCodes where ObjectTypeCode <= 9999`
- `0x5dc0f`: `PrivilegeObjectTypeCodeId, PrivilegeId, ObjectTypeCode`
- `0x5dc3a`: `select {0} from RoleTemplatePrivileges`
- `0x5dc3f`: `RoleTemplatePrivilegeId, RoleTemplateId, PrivilegeId, IsBasic, IsLocal, IsDeep, IsGlobal`

## pseudocode

```c

```

## disassembly

```asm
0x5d9a0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::.ctor()
0x5d9a5  stloc.0
0x5d9a6  ldloc.0
0x5d9a7  ldstr    aOptionset_0// "OptionSet"
0x5d9ac  ldstr    aSelect0FromOpt_3// "select {0} from OptionSet"
0x5d9b1  ldsfld   string Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::systemSolutionCondition
0x5d9b6  call     string [mscorlib]System.String::Concat(string, string)
0x5d9bb  ldstr    aConvertBigintV// "*, CONVERT(bigint, VersionNumber) AS Ti"...
0x5d9c0  ldnull
0x5d9c1  ldnull
0x5d9c2  ldc.i4.0
0x5d9c3  ldnull
0x5d9c4  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5d9c9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5d9ce  ldloc.0
0x5d9cf  ldstr    aEntity_0// "Entity"
0x5d9d4  ldstr    aSelect0FromEnt_19// "select {0} from Entity"
0x5d9d9  ldsfld   string Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::systemSolutionCondition
0x5d9de  call     string [mscorlib]System.String::Concat(string, string)
0x5d9e3  ldstr    aConvertBigintV// "*, CONVERT(bigint, VersionNumber) AS Ti"...
0x5d9e8  ldnull
0x5d9e9  ldnull
0x5d9ea  ldc.i4.0
0x5d9eb  ldnull
0x5d9ec  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5d9f1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5d9f6  ldloc.0
0x5d9f7  ldstr    aAttribute// "Attribute"
0x5d9fc  ldstr    aSelect0FromAtt_11// "select {0} from Attribute"
0x5da01  ldsfld   string Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::systemSolutionCondition
0x5da06  call     string [mscorlib]System.String::Concat(string, string)
0x5da0b  ldstr    aConvertBigintV// "*, CONVERT(bigint, VersionNumber) AS Ti"...
0x5da10  ldnull
0x5da11  ldnull
0x5da12  ldc.i4.0
0x5da13  ldnull
0x5da14  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5da19  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5da1e  ldloc.0
0x5da1f  ldstr    aLocalizedlabel// "LocalizedLabel"
0x5da24  ldstr    aSelect0FromLoc_3// "select {0} from LocalizedLabel"
0x5da29  ldsfld   string Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::systemSolutionCondition
0x5da2e  call     string [mscorlib]System.String::Concat(string, string)
0x5da33  ldstr    aConvertBigintV// "*, CONVERT(bigint, VersionNumber) AS Ti"...
0x5da38  ldnull
0x5da39  ldnull
0x5da3a  ldc.i4.0
0x5da3b  ldnull
0x5da3c  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5da41  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5da46  ldarg.1
0x5da47  ldc.i4   0x8000
0x5da4c  and
0x5da4d  ldc.i4   0x8000
0x5da52  bne.un.s loc_5DA7C
0x5da54  ldloc.0
0x5da55  ldstr    aAttributelooku// "AttributeLookupValue"
0x5da5a  ldstr    aSelect0FromAtt_12// "select {0} from AttributeLookupValue"
0x5da5f  ldsfld   string Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::systemSolutionCondition
0x5da64  call     string [mscorlib]System.String::Concat(string, string)
0x5da69  ldstr    asc_D5A0E// "*"
0x5da6e  ldnull
0x5da6f  ldnull
0x5da70  ldc.i4.0
0x5da71  ldnull
0x5da72  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5da77  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5da7c  ldarg.1
0x5da7d  ldc.i4   0x4000
0x5da82  and
0x5da83  ldc.i4   0x4000
0x5da88  bne.un.s loc_5DAB2
0x5da8a  ldloc.0
0x5da8b  ldstr    aAttributepickl// "AttributePicklistValue"
0x5da90  ldstr    aSelect0FromAtt_13// "select {0} from AttributePicklistValue"
0x5da95  ldsfld   string Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::systemSolutionCondition
0x5da9a  call     string [mscorlib]System.String::Concat(string, string)
0x5da9f  ldstr    asc_D5A0E// "*"
0x5daa4  ldnull
0x5daa5  ldnull
0x5daa6  ldc.i4.0
0x5daa7  ldnull
0x5daa8  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5daad  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5dab2  ldloc.0
0x5dab3  ldstr    aEntityrelation_0// "EntityRelationship"
0x5dab8  ldstr    aSelect0FromEnt_20// "select {0} from EntityRelationship"
0x5dabd  ldsfld   string Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::systemSolutionCondition
0x5dac2  call     string [mscorlib]System.String::Concat(string, string)
0x5dac7  ldstr    aConvertBigintV// "*, CONVERT(bigint, VersionNumber) AS Ti"...
0x5dacc  ldnull
0x5dacd  ldnull
0x5dace  ldc.i4.0
0x5dacf  ldnull
0x5dad0  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5dad5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5dada  ldloc.0
0x5dadb  ldstr    aRelationship_0// "Relationship"
0x5dae0  ldstr    aSelect0FromRel_5// "select {0} from Relationship"
0x5dae5  ldsfld   string Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::systemSolutionCondition
0x5daea  call     string [mscorlib]System.String::Concat(string, string)
0x5daef  ldstr    asc_D5A0E// "*"
0x5daf4  ldnull
0x5daf5  ldnull
0x5daf6  ldc.i4.0
0x5daf7  ldnull
0x5daf8  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5dafd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5db02  ldloc.0
0x5db03  ldstr    aRelationshipex_0// "RelationshipExtraCondition"
0x5db08  ldstr    aSelect0FromRel_6// "select {0} from RelationshipExtraCondit"...
0x5db0d  ldsfld   string Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::systemSolutionCondition
0x5db12  call     string [mscorlib]System.String::Concat(string, string)
0x5db17  ldstr    asc_D5A0E// "*"
0x5db1c  ldnull
0x5db1d  ldnull
0x5db1e  ldc.i4.0
0x5db1f  ldnull
0x5db20  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5db25  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5db2a  ldloc.0
0x5db2b  ldstr    aEntityrelation_4// "EntityRelationshipRole"
0x5db30  ldstr    aSelect0FromEnt_21// "select {0} from EntityRelationshipRole"
0x5db35  ldsfld   string Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::systemSolutionCondition
0x5db3a  call     string [mscorlib]System.String::Concat(string, string)
0x5db3f  ldstr    asc_D5A0E// "*"
0x5db44  ldnull
0x5db45  ldnull
0x5db46  ldc.i4.0
0x5db47  ldnull
0x5db48  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5db4d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5db52  ldloc.0
0x5db53  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x5db58  ldstr    aSelect0FromEnt_22// "select {0} from EntityRelationshipRelat"...
0x5db5d  ldsfld   string Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::systemSolutionCondition
0x5db62  call     string [mscorlib]System.String::Concat(string, string)
0x5db67  ldstr    asc_D5A0E// "*"
0x5db6c  ldnull
0x5db6d  ldnull
0x5db6e  ldc.i4.0
0x5db6f  ldnull
0x5db70  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5db75  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5db7a  ldloc.0
0x5db7b  ldstr    aViewattribute// "ViewAttribute"
0x5db80  ldstr    aSelect0FromVie_2// "select {0} from ViewAttribute"
0x5db85  ldsfld   string Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::systemSolutionCondition
0x5db8a  call     string [mscorlib]System.String::Concat(string, string)
0x5db8f  ldstr    asc_D5A0E// "*"
0x5db94  ldnull
0x5db95  ldnull
0x5db96  ldc.i4.0
0x5db97  ldnull
0x5db98  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5db9d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5dba2  ldarg.1
0x5dba3  ldc.i4   0x800
0x5dba8  and
0x5dba9  ldc.i4   0x800
0x5dbae  bne.un.s loc_5DBD8
0x5dbb0  ldloc.0
0x5dbb1  ldstr    aManagedpropert_5// "ManagedProperty"
0x5dbb6  ldstr    aSelect0FromMan_2// "select {0} from ManagedProperty"
0x5dbbb  ldsfld   string Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::systemSolutionCondition
0x5dbc0  call     string [mscorlib]System.String::Concat(string, string)
0x5dbc5  ldstr    asc_D5A0E// "*"
0x5dbca  ldnull
0x5dbcb  ldnull
0x5dbcc  ldc.i4.0
0x5dbcd  ldnull
0x5dbce  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5dbd3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5dbd8  ldarg.1
0x5dbd9  ldc.i4.8
0x5dbda  and
0x5dbdb  ldc.i4.8
0x5dbdc  bne.un.s loc_5DBFC
0x5dbde  ldloc.0
0x5dbdf  ldstr    aPrivilege// "Privilege"
0x5dbe4  ldstr    aSelect0FromPri_2// "select {0} from Privilege priv left out"...
0x5dbe9  ldstr    aPrivPrivotcObj_0// "priv.*, privotc.ObjectTypeCode"
0x5dbee  ldnull
0x5dbef  ldnull
0x5dbf0  ldc.i4.0
0x5dbf1  ldnull
0x5dbf2  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5dbf7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5dbfc  ldarg.1
0x5dbfd  ldc.i4.s 0x40
0x5dbff  and
0x5dc00  ldc.i4.s 0x40
0x5dc02  bne.un.s loc_5DC26
0x5dc04  ldloc.0
0x5dc05  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCode"
0x5dc0a  ldstr    aSelect0FromPri_3// "select {0} from PrivilegeObjectTypeCode"...
0x5dc0f  ldstr    aPrivilegeobjec_5// "PrivilegeObjectTypeCodeId, PrivilegeId,"...
0x5dc14  ldstr    aOrderByObjectt// "order by ObjectTypeCode"
0x5dc19  ldnull
0x5dc1a  ldc.i4.0
0x5dc1b  ldnull
0x5dc1c  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5dc21  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5dc26  ldarg.1
0x5dc27  ldc.i4   0x80
0x5dc2c  and
0x5dc2d  ldc.i4   0x80
0x5dc32  bne.un.s loc_5DC52
0x5dc34  ldloc.0
0x5dc35  ldstr    aRoletemplatepr// "RoleTemplatePrivilege"
0x5dc3a  ldstr    aSelect0FromRol_0// "select {0} from RoleTemplatePrivileges"
0x5dc3f  ldstr    aRoletemplatepr_8// "RoleTemplatePrivilegeId, RoleTemplateId"...
0x5dc44  ldnull
0x5dc45  ldnull
0x5dc46  ldc.i4.0
0x5dc47  ldnull
0x5dc48  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5dc4d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5dc52  ldloc.0
0x5dc53  ldstr    aEntitykey_0// "EntityKey"
0x5dc58  ldarg.0
0x5dc59  ldfld    string Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::_entityKeySelectCommand
0x5dc5e  ldstr    aConvertBigintV// "*, CONVERT(bigint, VersionNumber) AS Ti"...
0x5dc63  ldnull
0x5dc64  ldnull
0x5dc65  ldc.i4.0
0x5dc66  ldarg.0
0x5dc67  ldfld    string Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::_entityKeyIfExistsCondition
0x5dc6c  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5dc71  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5dc76  ldloc.0
0x5dc77  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x5dc7c  ldarg.0
0x5dc7d  ldfld    string Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::_entityKeyAttributeSelectCommand
0x5dc82  ldstr    aConvertBigintV// "*, CONVERT(bigint, VersionNumber) AS Ti"...
0x5dc87  ldnull
0x5dc88  ldnull
0x5dc89  ldc.i4.0
0x5dc8a  ldarg.0
0x5dc8b  ldfld    string Microsoft.Crm.Metadata.SystemDataOnlyMetadataCacheLoader::_entityKeyAttributeIfExistsCondition
0x5dc90  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5dc95  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5dc9a  ldloc.0
0x5dc9b  ret
```
