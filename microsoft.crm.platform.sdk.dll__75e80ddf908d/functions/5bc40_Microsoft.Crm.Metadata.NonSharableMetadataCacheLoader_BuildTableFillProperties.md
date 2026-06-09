# Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::BuildTableFillProperties

- ea: `0x5bc40`
- end: `0x5c040`
- name: `Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::BuildTableFillProperties`
- size: `1024`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xac570`

## callees

- `0x51010`
- `0x51fe0`
- `0x5bc40`
- `0x5c040`

## string_xrefs

- `0x5bf98`: `Privilege`
- `0x5bfa7`: `Privilege`
- `0x5bfcf`: `PrivilegeObjectTypeCode`
- `0x5bfde`: `PrivilegeObjectTypeCode`
- `0x5c010`: `RoleTemplatePrivilege`
- `0x5c01f`: `RoleTemplatePrivilege`
- `0x5c026`: `x.RoleTemplatePrivilegeId, x.RoleTemplateId, x.PrivilegeId, x.IsBasic, x.IsLocal, x.IsDeep, x.IsGlobal`

## pseudocode

```c

```

## disassembly

```asm
0x5bc40  ldarg.1
0x5bc41  ldc.i4.s 0x10
0x5bc43  and
0x5bc44  ldc.i4.s 0x10
0x5bc46  ceq
0x5bc48  stloc.0
0x5bc49  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::.ctor()
0x5bc4e  stloc.1
0x5bc4f  ldarg.1
0x5bc50  ldc.i4   0x100
0x5bc55  and
0x5bc56  ldc.i4   0x100
0x5bc5b  bne.un.s loc_5BC8C
0x5bc5d  ldarg.0
0x5bc5e  ldstr    aOptionset_0// "OptionSet"
0x5bc63  ldloc.0
0x5bc64  ldarg.2
0x5bc65  call     instance string Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::GetMetadataSelectCommand(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5bc6a  stloc.s  0xA
0x5bc6c  ldloc.1
0x5bc6d  ldstr    aOptionset_0// "OptionSet"
0x5bc72  ldloc.s  0xA
0x5bc74  ldstr    aConvertBigintV_0// "*,CONVERT(bigint, VersionNumber) AS Tim"...
0x5bc79  ldnull
0x5bc7a  ldarg.0
0x5bc7b  call     instance class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_ExtraWhereConditionsToFilterOutData()
0x5bc80  ldc.i4.0
0x5bc81  ldnull
0x5bc82  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5bc87  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5bc8c  ldarg.0
0x5bc8d  ldstr    aEntity_0// "Entity"
0x5bc92  ldloc.0
0x5bc93  ldarg.2
0x5bc94  call     instance string Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::GetMetadataSelectCommand(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5bc99  stloc.2
0x5bc9a  ldloc.1
0x5bc9b  ldstr    aEntity_0// "Entity"
0x5bca0  ldloc.2
0x5bca1  ldstr    aConvertBigintV_0// "*,CONVERT(bigint, VersionNumber) AS Tim"...
0x5bca6  ldstr    aOrderByXName// "order by x.Name"
0x5bcab  ldarg.0
0x5bcac  call     instance class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_ExtraWhereConditionsToFilterOutData()
0x5bcb1  ldc.i4.0
0x5bcb2  ldnull
0x5bcb3  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5bcb8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5bcbd  ldarg.0
0x5bcbe  ldstr    aAttribute// "Attribute"
0x5bcc3  ldloc.0
0x5bcc4  ldarg.2
0x5bcc5  call     instance string Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::GetMetadataSelectCommand(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5bcca  stloc.3
0x5bccb  ldloc.1
0x5bccc  ldstr    aAttribute// "Attribute"
0x5bcd1  ldloc.3
0x5bcd2  ldstr    aXTypenameAtDes// "x.*, 'typename' = at.Description, 'isqu"...
0x5bcd7  ldstr    aOrderByXEntity// "order by x.EntityId, x.ColumnNumber"
0x5bcdc  ldarg.0
0x5bcdd  call     instance class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_ExtraWhereConditionsToFilterOutData()
0x5bce2  ldc.i4.0
0x5bce3  ldnull
0x5bce4  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5bce9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5bcee  ldarg.1
0x5bcef  ldc.i4   0x40000
0x5bcf4  and
0x5bcf5  ldc.i4   0x40000
0x5bcfa  bne.un.s loc_5BD64
0x5bcfc  ldarg.0
0x5bcfd  ldstr    aEntitykey_0// "EntityKey"
0x5bd02  ldloc.0
0x5bd03  ldarg.2
0x5bd04  call     instance string Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::GetMetadataSelectCommand(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5bd09  stloc.s  0xB
0x5bd0b  ldloc.1
0x5bd0c  ldstr    aEntitykey_0// "EntityKey"
0x5bd11  ldloc.s  0xB
0x5bd13  ldstr    aConvertBigintV_0// "*,CONVERT(bigint, VersionNumber) AS Tim"...
0x5bd18  ldnull
0x5bd19  ldarg.0
0x5bd1a  call     instance class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_ExtraWhereConditionsToFilterOutData()
0x5bd1f  ldc.i4.0
0x5bd20  ldarg.0
0x5bd21  ldfld    string Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::EntityKeyIfExistsCondition
0x5bd26  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5bd2b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5bd30  ldarg.0
0x5bd31  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x5bd36  ldloc.0
0x5bd37  ldarg.2
0x5bd38  call     instance string Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::GetMetadataSelectCommand(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5bd3d  stloc.s  0xC
0x5bd3f  ldloc.1
0x5bd40  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x5bd45  ldloc.s  0xC
0x5bd47  ldstr    aConvertBigintV_0// "*,CONVERT(bigint, VersionNumber) AS Tim"...
0x5bd4c  ldnull
0x5bd4d  ldarg.0
0x5bd4e  call     instance class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_ExtraWhereConditionsToFilterOutData()
0x5bd53  ldc.i4.0
0x5bd54  ldarg.0
0x5bd55  ldfld    string Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::EntityKeyAttributeIfExistsCondition
0x5bd5a  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5bd5f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5bd64  ldarg.1
0x5bd65  ldc.i4   0x8000
0x5bd6a  and
0x5bd6b  ldc.i4   0x8000
0x5bd70  bne.un.s loc_5BDA1
0x5bd72  ldarg.0
0x5bd73  ldstr    aAttributelooku// "AttributeLookupValue"
0x5bd78  ldloc.0
0x5bd79  ldarg.2
0x5bd7a  call     instance string Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::GetMetadataSelectCommand(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5bd7f  stloc.s  0xD
0x5bd81  ldloc.1
0x5bd82  ldstr    aAttributelooku// "AttributeLookupValue"
0x5bd87  ldloc.s  0xD
0x5bd89  ldstr    asc_D5A0E// "*"
0x5bd8e  ldnull
0x5bd8f  ldarg.0
0x5bd90  call     instance class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_ExtraWhereConditionsToFilterOutData()
0x5bd95  ldc.i4.0
0x5bd96  ldnull
0x5bd97  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5bd9c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5bda1  ldarg.1
0x5bda2  ldc.i4   0x4000
0x5bda7  and
0x5bda8  ldc.i4   0x4000
0x5bdad  bne.un.s loc_5BDE2
0x5bdaf  ldarg.0
0x5bdb0  ldstr    aAttributepickl// "AttributePicklistValue"
0x5bdb5  ldloc.0
0x5bdb6  ldarg.2
0x5bdb7  call     instance string Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::GetMetadataSelectCommand(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5bdbc  stloc.s  0xE
0x5bdbe  ldloc.1
0x5bdbf  ldstr    aAttributepickl// "AttributePicklistValue"
0x5bdc4  ldloc.s  0xE
0x5bdc6  ldstr    asc_D5A0E// "*"
0x5bdcb  ldstr    aOrderByXDispla// "order by x.DisplayOrder asc"
0x5bdd0  ldarg.0
0x5bdd1  call     instance class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_ExtraWhereConditionsToFilterOutData()
0x5bdd6  ldc.i4.0
0x5bdd7  ldnull
0x5bdd8  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5bddd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5bde2  ldarg.1
0x5bde3  ldc.i4   0x2000
0x5bde8  and
0x5bde9  ldc.i4   0x2000
0x5bdee  bne.un.s loc_5BE3A
0x5bdf0  ldarg.1
0x5bdf1  ldc.i4   0x20000
0x5bdf6  and
0x5bdf7  ldc.i4   0x20000
0x5bdfc  ceq
0x5bdfe  ldloc.0
0x5bdff  and
0x5be00  brfalse.s loc_5BE0B
0x5be02  ldstr    aSelect0FromLoc// "select {0} from LocalizedLabelAsIfPubli"...
0x5be07  stloc.s  0xF
0x5be09  br.s     loc_5BE1A
0x5be0b  ldarg.0
0x5be0c  ldstr    aLocalizedlabel// "LocalizedLabel"
0x5be11  ldloc.0
0x5be12  ldarg.2
0x5be13  call     instance string Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::GetMetadataSelectCommand(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5be18  stloc.s  0xF
0x5be1a  ldloc.1
0x5be1b  ldstr    aLocalizedlabel// "LocalizedLabel"
0x5be20  ldloc.s  0xF
0x5be22  ldstr    aConvertBigintV_0// "*,CONVERT(bigint, VersionNumber) AS Tim"...
0x5be27  ldnull
0x5be28  ldarg.0
0x5be29  call     instance class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_ExtraWhereConditionsToFilterOutData()
0x5be2e  ldc.i4.1
0x5be2f  ldnull
0x5be30  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5be35  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5be3a  ldarg.0
0x5be3b  ldstr    aEntityrelation_0// "EntityRelationship"
0x5be40  ldloc.0
0x5be41  ldarg.2
0x5be42  call     instance string Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::GetMetadataSelectCommand(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5be47  stloc.s  4
0x5be49  ldloc.1
0x5be4a  ldstr    aEntityrelation_0// "EntityRelationship"
0x5be4f  ldloc.s  4
0x5be51  ldstr    aConvertBigintV_0// "*,CONVERT(bigint, VersionNumber) AS Tim"...
0x5be56  ldnull
0x5be57  ldarg.0
0x5be58  call     instance class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_ExtraWhereConditionsToFilterOutData()
0x5be5d  ldc.i4.0
0x5be5e  ldnull
0x5be5f  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5be64  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5be69  ldarg.0
0x5be6a  ldstr    aRelationship_0// "Relationship"
0x5be6f  ldloc.0
0x5be70  ldarg.2
0x5be71  call     instance string Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::GetMetadataSelectCommand(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5be76  stloc.s  5
0x5be78  ldloc.1
0x5be79  ldstr    aRelationship_0// "Relationship"
0x5be7e  ldloc.s  5
0x5be80  ldstr    asc_D5A0E// "*"
0x5be85  ldnull
0x5be86  ldarg.0
0x5be87  call     instance class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_ExtraWhereConditionsToFilterOutData()
0x5be8c  ldc.i4.0
0x5be8d  ldnull
0x5be8e  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5be93  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5be98  ldarg.0
0x5be99  ldstr    aRelationshipex_0// "RelationshipExtraCondition"
0x5be9e  ldloc.0
0x5be9f  ldarg.2
0x5bea0  call     instance string Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::GetMetadataSelectCommand(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5bea5  stloc.s  6
0x5bea7  ldloc.1
0x5bea8  ldstr    aRelationshipex_0// "RelationshipExtraCondition"
0x5bead  ldloc.s  6
0x5beaf  ldstr    asc_D5A0E// "*"
0x5beb4  ldnull
0x5beb5  ldarg.0
0x5beb6  call     instance class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_ExtraWhereConditionsToFilterOutData()
0x5bebb  ldc.i4.0
0x5bebc  ldnull
0x5bebd  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5bec2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5bec7  ldarg.0
0x5bec8  ldstr    aEntityrelation_4// "EntityRelationshipRole"
0x5becd  ldloc.0
0x5bece  ldarg.2
0x5becf  call     instance string Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::GetMetadataSelectCommand(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5bed4  stloc.s  7
0x5bed6  ldloc.1
0x5bed7  ldstr    aEntityrelation_4// "EntityRelationshipRole"
0x5bedc  ldloc.s  7
0x5bede  ldstr    asc_D5A0E// "*"
0x5bee3  ldnull
0x5bee4  ldarg.0
0x5bee5  call     instance class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_ExtraWhereConditionsToFilterOutData()
0x5beea  ldc.i4.0
0x5beeb  ldnull
0x5beec  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5bef1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5bef6  ldarg.0
0x5bef7  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x5befc  ldloc.0
0x5befd  ldarg.2
0x5befe  call     instance string Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::GetMetadataSelectCommand(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5bf03  stloc.s  8
0x5bf05  ldloc.1
0x5bf06  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x5bf0b  ldloc.s  8
0x5bf0d  ldstr    asc_D5A0E// "*"
0x5bf12  ldnull
0x5bf13  ldarg.0
0x5bf14  call     instance class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_ExtraWhereConditionsToFilterOutData()
0x5bf19  ldc.i4.0
0x5bf1a  ldnull
0x5bf1b  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5bf20  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5bf25  ldarg.0
0x5bf26  ldstr    aViewattribute// "ViewAttribute"
0x5bf2b  ldloc.0
0x5bf2c  ldarg.2
0x5bf2d  call     instance string Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::GetMetadataSelectCommand(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5bf32  stloc.s  9
0x5bf34  ldloc.1
0x5bf35  ldstr    aViewattribute// "ViewAttribute"
0x5bf3a  ldloc.s  9
0x5bf3c  ldstr    asc_D5A0E// "*"
0x5bf41  ldnull
0x5bf42  ldarg.0
0x5bf43  call     instance class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_ExtraWhereConditionsToFilterOutData()
0x5bf48  ldc.i4.0
0x5bf49  ldnull
0x5bf4a  newobj   instance void Microsoft.Crm.Metadata.TableFillProperties::.ctor(string metadataEntityName, string selectCommand, [opt] string selectColumns, [opt] string selectOrderBy, [opt] class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions selectWhereConditions, [opt] bool selectCommandAlreadyContainsWhereConditions, [opt] string ifExistsCondition)
0x5bf4f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.TableFillProperties>::Add(var<u1>)
0x5bf54  ldarg.1
0x5bf55  ldc.i4   0x800
0x5bf5a  and
0x5bf5b  ldc.i4   0x800
0x5bf60  bne.un.s loc_5BF91
0x5bf62  ldarg.0
0x5bf63  ldstr    aManagedpropert_5// "ManagedProperty"
0x5bf68  ldloc.0
0x5bf69  ldarg.2
0x5bf6a  call     instance string Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::GetMetadataSelectCommand(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5bf6f  stloc.s  0x10
0x5bf71  ldloc.1
0x5bf72  ldstr    aManagedpropert_5// "ManagedProperty"
0x5bf77  ldloc.s  0x10
0x5bf79  ldstr    asc_D5A0E// "*"
0x5bf7e  ldnull
  ... truncated ...
```
