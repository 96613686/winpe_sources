# Microsoft.Crm.Metadata.Generators.EntityMetadataGenerator::RetrieveMetadataChanges

- ea: `0x623f0`
- end: `0x628fc`
- name: `Microsoft.Crm.Metadata.Generators.EntityMetadataGenerator::RetrieveMetadataChanges`
- size: `1292`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x620a0`

## callees

- `0xe8c0`
- `0xf820`
- `0x623f0`
- `0x62930`

## string_xrefs

- `0x624c1`: `IsDocumentRecommendationsEnabled`
- `0x6252d`: `IsQuickCreateEnabled`
- `0x62536`: `IsReadOnlyInMobileClient`
- `0x625b4`: `Privileges`
- `0x626e1`: `IsValidForCreate`
- `0x626ea`: `IsValidForRead`
- `0x626f3`: `IsValidForUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x623f0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataPropertiesExpression::.ctor()
0x623f5  stloc.0
0x623f6  ldloc.0
0x623f7  ldc.i4.0
0x623f8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataPropertiesExpression::set_AllProperties(bool)
0x623fd  ldloc.0
0x623fe  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<string> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataPropertiesExpression::get_PropertyNames()
0x62403  ldc.i4.s 0x34
0x62405  newarr   [mscorlib]System.String
0x6240a  dup
0x6240b  ldc.i4.0
0x6240c  ldstr    aActivitytypema_0// "ActivityTypeMask"
0x62411  stelem.ref
0x62412  dup
0x62413  ldc.i4.1
0x62414  ldstr    aAttributes_0// "Attributes"
0x62419  stelem.ref
0x6241a  dup
0x6241b  ldc.i4.2
0x6241c  ldstr    aAutoroutetoown_2// "AutoRouteToOwnerQueue"
0x62421  stelem.ref
0x62422  dup
0x62423  ldc.i4.3
0x62424  ldstr    aCanenablesynct_0// "CanEnableSyncToExternalSearchIndex"
0x62429  stelem.ref
0x6242a  dup
0x6242b  ldc.i4.4
0x6242c  ldstr    aCantriggerwork_0// "CanTriggerWorkflow"
0x62431  stelem.ref
0x62432  dup
0x62433  ldc.i4.5
0x62434  ldstr    aDescription// "Description"
0x62439  stelem.ref
0x6243a  dup
0x6243b  ldc.i4.6
0x6243c  ldstr    aDisplaycollect_2// "DisplayCollectionName"
0x62441  stelem.ref
0x62442  dup
0x62443  ldc.i4.7
0x62444  ldstr    aDisplayname// "DisplayName"
0x62449  stelem.ref
0x6244a  dup
0x6244b  ldc.i4.8
0x6244c  ldstr    aEnforcestatetr_0// "EnforceStateTransitions"
0x62451  stelem.ref
0x62452  dup
0x62453  ldc.i4.s 9
0x62455  ldstr    aEntitycolor_0// "EntityColor"
0x6245a  stelem.ref
0x6245b  dup
0x6245c  ldc.i4.s 0xA
0x6245e  ldstr    aEntitysetname_0// "EntitySetName"
0x62463  stelem.ref
0x62464  dup
0x62465  ldc.i4.s 0xB
0x62467  ldstr    aHaschanged// "HasChanged"
0x6246c  stelem.ref
0x6246d  dup
0x6246e  ldc.i4.s 0xC
0x62470  ldstr    aIsactivity_0// "IsActivity"
0x62475  stelem.ref
0x62476  dup
0x62477  ldc.i4.s 0xD
0x62479  ldstr    aIsactivitypart_0// "IsActivityParty"
0x6247e  stelem.ref
0x6247f  dup
0x62480  ldc.i4.s 0xE
0x62482  ldstr    aIsbpfentity_0// "IsBPFEntity"
0x62487  stelem.ref
0x62488  dup
0x62489  ldc.i4.s 0xF
0x6248b  ldstr    aIsbusinessproc_0// "IsBusinessProcessEnabled"
0x62490  stelem.ref
0x62491  dup
0x62492  ldc.i4.s 0x10
0x62494  ldstr    aIschildentity_0// "IsChildEntity"
0x62499  stelem.ref
0x6249a  dup
0x6249b  ldc.i4.s 0x11
0x6249d  ldstr    aIsconnectionse_0// "IsConnectionsEnabled"
0x624a2  stelem.ref
0x624a3  dup
0x624a4  ldc.i4.s 0x12
0x624a6  ldstr    aIscustomentity_0// "IsCustomEntity"
0x624ab  stelem.ref
0x624ac  dup
0x624ad  ldc.i4.s 0x13
0x624af  ldstr    aIscustomizable_0// "IsCustomizable"
0x624b4  stelem.ref
0x624b5  dup
0x624b6  ldc.i4.s 0x14
0x624b8  ldstr    aIsdocumentmana_0// "IsDocumentManagementEnabled"
0x624bd  stelem.ref
0x624be  dup
0x624bf  ldc.i4.s 0x15
0x624c1  ldstr    aIsdocumentreco_0// "IsDocumentRecommendationsEnabled"
0x624c6  stelem.ref
0x624c7  dup
0x624c8  ldc.i4.s 0x16
0x624ca  ldstr    aIsduplicatedet// "IsDuplicateDetectionEnabled"
0x624cf  stelem.ref
0x624d0  dup
0x624d1  ldc.i4.s 0x17
0x624d3  ldstr    aIsenabledforch_0// "IsEnabledForCharts"
0x624d8  stelem.ref
0x624d9  dup
0x624da  ldc.i4.s 0x18
0x624dc  ldstr    aIsimportable_0// "IsImportable"
0x624e1  stelem.ref
0x624e2  dup
0x624e3  ldc.i4.s 0x19
0x624e5  ldstr    aIsinteractionc_0// "IsInteractionCentricEnabled"
0x624ea  stelem.ref
0x624eb  dup
0x624ec  ldc.i4.s 0x1A
0x624ee  ldstr    aIsintersect_0// "IsIntersect"
0x624f3  stelem.ref
0x624f4  dup
0x624f5  ldc.i4.s 0x1B
0x624f7  ldstr    aIsknowledgeman_0// "IsKnowledgeManagementEnabled"
0x624fc  stelem.ref
0x624fd  dup
0x624fe  ldc.i4.s 0x1C
0x62500  ldstr    aIsmailmergeena_0// "IsMailMergeEnabled"
0x62505  stelem.ref
0x62506  dup
0x62507  ldc.i4.s 0x1D
0x62509  ldstr    aIsmanaged_0// "IsManaged"
0x6250e  stelem.ref
0x6250f  dup
0x62510  ldc.i4.s 0x1E
0x62512  ldstr    aIsofflineinmob_0// "IsOfflineInMobileClient"
0x62517  stelem.ref
0x62518  dup
0x62519  ldc.i4.s 0x1F
0x6251b  ldstr    aIsonenoteinteg_0// "IsOneNoteIntegrationEnabled"
0x62520  stelem.ref
0x62521  dup
0x62522  ldc.i4.s 0x20
0x62524  ldstr    aIsoptimisticco_2// "IsOptimisticConcurrencyEnabled"
0x62529  stelem.ref
0x6252a  dup
0x6252b  ldc.i4.s 0x21
0x6252d  ldstr    aIsquickcreatee_0// "IsQuickCreateEnabled"
0x62532  stelem.ref
0x62533  dup
0x62534  ldc.i4.s 0x22
0x62536  ldstr    aIsreadonlyinmo_0// "IsReadOnlyInMobileClient"
0x6253b  stelem.ref
0x6253c  dup
0x6253d  ldc.i4.s 0x23
0x6253f  ldstr    aIsstatemodelaw_0// "IsStateModelAware"
0x62544  stelem.ref
0x62545  dup
0x62546  ldc.i4.s 0x24
0x62548  ldstr    aIsvalidforadva_0// "IsValidForAdvancedFind"
0x6254d  stelem.ref
0x6254e  dup
0x6254f  ldc.i4.s 0x25
0x62551  ldstr    aIsvalidforqueu// "IsValidForQueue"
0x62556  stelem.ref
0x62557  dup
0x62558  ldc.i4.s 0x26
0x6255a  ldstr    aIsvisibleinmob_2// "IsVisibleInMobileClient"
0x6255f  stelem.ref
0x62560  dup
0x62561  ldc.i4.s 0x27
0x62563  ldstr    aLogicalname_0// "LogicalName"
0x62568  stelem.ref
0x62569  dup
0x6256a  ldc.i4.s 0x28
0x6256c  ldstr    aManytomanyrela_2// "ManyToManyRelationships"
0x62571  stelem.ref
0x62572  dup
0x62573  ldc.i4.s 0x29
0x62575  ldstr    aManytoonerelat// "ManyToOneRelationships"
0x6257a  stelem.ref
0x6257b  dup
0x6257c  ldc.i4.s 0x2A
0x6257e  ldstr    aObjecttypecode_5// "ObjectTypeCode"
0x62583  stelem.ref
0x62584  dup
0x62585  ldc.i4.s 0x2B
0x62587  ldstr    aOnetomanyrelat_0// "OneToManyRelationships"
0x6258c  stelem.ref
0x6258d  dup
0x6258e  ldc.i4.s 0x2C
0x62590  ldstr    aOwnershiptype// "OwnershipType"
0x62595  stelem.ref
0x62596  dup
0x62597  ldc.i4.s 0x2D
0x62599  ldstr    aPrimaryidattri// "PrimaryIdAttribute"
0x6259e  stelem.ref
0x6259f  dup
0x625a0  ldc.i4.s 0x2E
0x625a2  ldstr    aPrimaryimageat// "PrimaryImageAttribute"
0x625a7  stelem.ref
0x625a8  dup
0x625a9  ldc.i4.s 0x2F
0x625ab  ldstr    aPrimarynameatt// "PrimaryNameAttribute"
0x625b0  stelem.ref
0x625b1  dup
0x625b2  ldc.i4.s 0x30
0x625b4  ldstr    aPrivileges// "Privileges"
0x625b9  stelem.ref
0x625ba  dup
0x625bb  ldc.i4.s 0x31
0x625bd  ldstr    aUsesbusinessda_0// "UsesBusinessDataLabelTable"
0x625c2  stelem.ref
0x625c3  dup
0x625c4  ldc.i4.s 0x32
0x625c6  ldstr    aIconvectorname_0// "IconVectorName"
0x625cb  stelem.ref
0x625cc  dup
0x625cd  ldc.i4.s 0x33
0x625cf  ldstr    aDataproviderid_0// "DataProviderId"
0x625d4  stelem.ref
0x625d5  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<string>::AddRange(var<u1>[])
0x625da  ldc.i4.0
0x625db  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataFilterExpression::.ctor(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x625e0  stloc.1
0x625e1  ldloc.1
0x625e2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataFilterExpression::get_Conditions()
0x625e7  ldstr    aLogicalname_0// "LogicalName"
0x625ec  ldc.i4.2
0x625ed  ldc.i4.1
0x625ee  newarr   [mscorlib]System.String
0x625f3  dup
0x625f4  ldc.i4.0
0x625f5  ldarg.1
0x625f6  stelem.ref
0x625f7  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionOperator, object)
0x625fc  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionExpression>::Add(var<u1>)
0x62601  ldnull
0x62602  stloc.2
0x62603  ldnull
0x62604  stloc.3
0x62605  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataPropertiesExpression::.ctor()
0x6260a  dup
0x6260b  ldc.i4.0
0x6260c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataPropertiesExpression::set_AllProperties(bool)
0x62611  stloc.s  4
0x62613  ldloc.s  4
0x62615  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<string> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataPropertiesExpression::get_PropertyNames()
0x6261a  ldc.i4.s 0x25
0x6261c  newarr   [mscorlib]System.String
0x62621  dup
0x62622  ldc.i4.0
0x62623  ldstr    aAttributeof_0// "AttributeOf"
0x62628  stelem.ref
0x62629  dup
0x6262a  ldc.i4.1
0x6262b  ldstr    aAttributetype// "AttributeType"
0x62630  stelem.ref
0x62631  dup
0x62632  ldc.i4.2
0x62633  ldstr    aAttributetypen// "AttributeTypeName"
0x62638  stelem.ref
0x62639  dup
0x6263a  ldc.i4.3
0x6263b  ldstr    aColumnnumber_1// "ColumnNumber"
0x62640  stelem.ref
0x62641  dup
0x62642  ldc.i4.4
0x62643  ldstr    aDatetimebehavi// "DateTimeBehavior"
0x62648  stelem.ref
0x62649  dup
0x6264a  ldc.i4.5
0x6264b  ldstr    aDefaultformval// "DefaultFormValue"
0x62650  stelem.ref
0x62651  dup
0x62652  ldc.i4.6
0x62653  ldstr    aDefaultvalue// "DefaultValue"
0x62658  stelem.ref
0x62659  dup
0x6265a  ldc.i4.7
0x6265b  ldstr    aDescription// "Description"
0x62660  stelem.ref
0x62661  dup
0x62662  ldc.i4.8
0x62663  ldstr    aDisplayname// "DisplayName"
0x62668  stelem.ref
0x62669  dup
0x6266a  ldc.i4.s 9
0x6266c  ldstr    aEntitylogicaln_0// "EntityLogicalName"
0x62671  stelem.ref
0x62672  dup
0x62673  ldc.i4.s 0xA
0x62675  ldstr    aFormat_0// "Format"
0x6267a  stelem.ref
0x6267b  dup
0x6267c  ldc.i4.s 0xB
0x6267e  ldstr    aFormatname// "FormatName"
0x62683  stelem.ref
0x62684  dup
0x62685  ldc.i4.s 0xC
0x62687  ldstr    aHaschanged// "HasChanged"
0x6268c  stelem.ref
0x6268d  dup
0x6268e  ldc.i4.s 0xD
  ... truncated ...
```
