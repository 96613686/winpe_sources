# Microsoft.Crm.Metadata.UpgradeHelper::.cctor

- ea: `0x59490`
- end: `0x59816`
- name: `Microsoft.Crm.Metadata.UpgradeHelper::.cctor`
- size: `902`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x59830`

## string_xrefs

- `0x59641`: `entityrelationshiprelationshipsid`
- `0x594a4`: `CreateIfExistingNotFoundForCreateInUpgradeContext`

## pseudocode

```c

```

## disassembly

```asm
0x59490  ldstr    aV8tov9upgradef// "v8Tov9UpgradeForSystemConvertedSolution"...
0x59495  stsfld   string Microsoft.Crm.Metadata.UpgradeHelper::UpgradeInternalContextVariableKey
0x5949a  ldstr    aTrue_0// "True"
0x5949f  stsfld   string Microsoft.Crm.Metadata.UpgradeHelper::UpgradeInternalContextVariableValue
0x594a4  ldstr    aCreateifexisti// "CreateIfExistingNotFoundForCreateInUpgr"...
0x594a9  stsfld   string Microsoft.Crm.Metadata.UpgradeHelper::CreateIfExistingNotFoundForCreateInUpgradeContextKey
0x594ae  ldstr    aTrue_0// "True"
0x594b3  stsfld   string Microsoft.Crm.Metadata.UpgradeHelper::CreateIfExistingNotFoundForCreateInUpgradeContextValue
0x594b8  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo>::.ctor()
0x594bd  dup
0x594be  ldstr    aEntityrelation_3// "EntityRelationship"
0x594c3  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::.ctor()
0x594c8  dup
0x594c9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x594ce  dup
0x594cf  ldstr    aSchemaname// "schemaname"
0x594d4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x594d9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::Add(var<u1>)
0x594de  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x594e3  dup
0x594e4  ldstr    aEntityrelation// "entityrelationshipid"
0x594e9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x594ee  ldstr    aEntityrelation// "entityrelationshipid"
0x594f3  ldc.i4.s 0xB
0x594f5  newobj   instance void Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo::.ctor(class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>> conditonColumnsSets, class [mscorlib]System.Collections.Generic.List`1<string> guidColumns, string idColumn, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataObjectType componentType)
0x594fa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo>::Add(var<u1>, !!T0)
0x594ff  dup
0x59500  ldstr    aRelationship_0// "Relationship"
0x59505  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::.ctor()
0x5950a  dup
0x5950b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x59510  dup
0x59511  ldstr    aName// "name"
0x59516  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5951b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::Add(var<u1>)
0x59520  dup
0x59521  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x59526  dup
0x59527  ldstr    aReferencingent// "referencingentityid"
0x5952c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x59531  dup
0x59532  ldstr    aReferencingatt// "referencingattributeid"
0x59537  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5953c  dup
0x5953d  ldstr    aReferencedenti// "referencedentityid"
0x59542  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x59547  dup
0x59548  ldstr    aReferencedattr// "referencedattributeid"
0x5954d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x59552  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::Add(var<u1>)
0x59557  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5955c  dup
0x5955d  ldstr    aRelationshipid// "relationshipid"
0x59562  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x59567  dup
0x59568  ldstr    aReferencingatt// "referencingattributeid"
0x5956d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x59572  dup
0x59573  ldstr    aReferencedattr// "referencedattributeid"
0x59578  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5957d  ldstr    aRelationshipid// "relationshipid"
0x59582  ldc.i4.2
0x59583  newobj   instance void Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo::.ctor(class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>> conditonColumnsSets, class [mscorlib]System.Collections.Generic.List`1<string> guidColumns, string idColumn, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataObjectType componentType)
0x59588  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo>::Add(var<u1>, !!T0)
0x5958d  dup
0x5958e  ldstr    aRelationshipex// "RelationshipExtraCondition"
0x59593  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::.ctor()
0x59598  dup
0x59599  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5959e  dup
0x5959f  ldstr    aRelationshipid// "relationshipid"
0x595a4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x595a9  dup
0x595aa  ldstr    aAttributeid// "attributeid"
0x595af  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x595b4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::Add(var<u1>)
0x595b9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x595be  ldstr    aConditionid// "conditionid"
0x595c3  ldc.i4.4
0x595c4  newobj   instance void Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo::.ctor(class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>> conditonColumnsSets, class [mscorlib]System.Collections.Generic.List`1<string> guidColumns, string idColumn, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataObjectType componentType)
0x595c9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo>::Add(var<u1>, !!T0)
0x595ce  dup
0x595cf  ldstr    aEntityrelation_2// "EntityRelationshipRole"
0x595d4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::.ctor()
0x595d9  dup
0x595da  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x595df  dup
0x595e0  ldstr    aEntityid// "entityid"
0x595e5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x595ea  dup
0x595eb  ldstr    aEntityrelation// "entityrelationshipid"
0x595f0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x595f5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::Add(var<u1>)
0x595fa  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x595ff  ldstr    aEntityrelation_1// "entityrelationshiproleid"
0x59604  ldc.i4.s 0xC
0x59606  newobj   instance void Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo::.ctor(class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>> conditonColumnsSets, class [mscorlib]System.Collections.Generic.List`1<string> guidColumns, string idColumn, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataObjectType componentType)
0x5960b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo>::Add(var<u1>, !!T0)
0x59610  dup
0x59611  ldstr    aEntityrelation_4// "EntityRelationshipRelationships"
0x59616  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::.ctor()
0x5961b  dup
0x5961c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x59621  dup
0x59622  ldstr    aRelationshipid// "relationshipid"
0x59627  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5962c  dup
0x5962d  ldstr    aEntityrelation// "entityrelationshipid"
0x59632  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x59637  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::Add(var<u1>)
0x5963c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x59641  ldstr    aEntityrelation_7// "entityrelationshiprelationshipsid"
0x59646  ldc.i4.s 0xD
0x59648  newobj   instance void Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo::.ctor(class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>> conditonColumnsSets, class [mscorlib]System.Collections.Generic.List`1<string> guidColumns, string idColumn, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataObjectType componentType)
0x5964d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo>::Add(var<u1>, !!T0)
0x59652  dup
0x59653  ldstr    aViewattribute// "ViewAttribute"
0x59658  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::.ctor()
0x5965d  dup
0x5965e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x59663  dup
0x59664  ldstr    aRelationshipid// "relationshipid"
0x59669  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5966e  dup
0x5966f  ldstr    aAttributeid// "attributeid"
0x59674  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x59679  dup
0x5967a  ldstr    aRemoteattribut// "remoteattributeid"
0x5967f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x59684  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::Add(var<u1>)
0x59689  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5968e  dup
0x5968f  ldstr    aAttributeid// "attributeid"
0x59694  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x59699  ldstr    aViewattributei// "viewattributeid"
0x5969e  ldc.i4.3
0x5969f  newobj   instance void Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo::.ctor(class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>> conditonColumnsSets, class [mscorlib]System.Collections.Generic.List`1<string> guidColumns, string idColumn, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataObjectType componentType)
0x596a4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo>::Add(var<u1>, !!T0)
0x596a9  dup
0x596aa  ldstr    aAttribute// "Attribute"
0x596af  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::.ctor()
0x596b4  dup
0x596b5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x596ba  dup
0x596bb  ldstr    aName// "name"
0x596c0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x596c5  dup
0x596c6  ldstr    aEntityid// "entityid"
0x596cb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x596d0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::Add(var<u1>)
0x596d5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x596da  dup
0x596db  ldstr    aAttributeid// "attributeid"
0x596e0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x596e5  dup
0x596e6  ldstr    aAttributeof// "attributeof"
0x596eb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x596f0  ldstr    aAttributeid// "attributeid"
0x596f5  ldc.i4.1
0x596f6  newobj   instance void Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo::.ctor(class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>> conditonColumnsSets, class [mscorlib]System.Collections.Generic.List`1<string> guidColumns, string idColumn, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataObjectType componentType)
0x596fb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo>::Add(var<u1>, !!T0)
0x59700  dup
0x59701  ldstr    aLocalizedlabel// "LocalizedLabel"
0x59706  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::.ctor()
0x5970b  dup
0x5970c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x59711  dup
0x59712  ldstr    aObjectid// "objectid"
0x59717  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5971c  dup
0x5971d  ldstr    aObjectcolumnna// "objectcolumnname"
0x59722  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x59727  dup
0x59728  ldstr    aLanguageid// "languageid"
0x5972d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x59732  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::Add(var<u1>)
0x59737  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5973c  ldstr    aLocalizedlabel_0// "localizedlabelid"
0x59741  ldc.i4.7
0x59742  newobj   instance void Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo::.ctor(class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>> conditonColumnsSets, class [mscorlib]System.Collections.Generic.List`1<string> guidColumns, string idColumn, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataObjectType componentType)
0x59747  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo>::Add(var<u1>, !!T0)
0x5974c  dup
0x5974d  ldstr    aAttributelooku// "AttributeLookupValue"
0x59752  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::.ctor()
0x59757  dup
0x59758  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5975d  dup
0x5975e  ldstr    aEntityid// "entityid"
0x59763  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x59768  dup
0x59769  ldstr    aAttributeid// "attributeid"
0x5976e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x59773  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::Add(var<u1>)
0x59778  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5977d  ldstr    aAttributelooku_1// "attributelookupvalueid"
0x59782  ldc.i4.6
0x59783  newobj   instance void Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo::.ctor(class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>> conditonColumnsSets, class [mscorlib]System.Collections.Generic.List`1<string> guidColumns, string idColumn, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataObjectType componentType)
0x59788  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo>::Add(var<u1>, !!T0)
0x5978d  dup
0x5978e  ldstr    aOptionset_0// "OptionSet"
0x59793  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::.ctor()
0x59798  dup
0x59799  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5979e  dup
0x5979f  ldstr    aName// "name"
0x597a4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x597a9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::Add(var<u1>)
0x597ae  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x597b3  dup
0x597b4  ldstr    aOptionsetid// "optionsetid"
0x597b9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x597be  ldstr    aOptionsetid// "optionsetid"
0x597c3  ldc.i4.s 0xE
0x597c5  newobj   instance void Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo::.ctor(class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>> conditonColumnsSets, class [mscorlib]System.Collections.Generic.List`1<string> guidColumns, string idColumn, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataObjectType componentType)
0x597ca  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo>::Add(var<u1>, !!T0)
0x597cf  dup
0x597d0  ldstr    aAttributepickl// "AttributePicklistValue"
0x597d5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::.ctor()
0x597da  dup
0x597db  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x597e0  dup
0x597e1  ldstr    aOptionsetid// "optionsetid"
0x597e6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x597eb  dup
0x597ec  ldstr    aValue// "value"
0x597f1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x597f6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>>::Add(var<u1>)
0x597fb  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x59800  ldstr    aAttributepickl_0// "attributepicklistvalueid"
0x59805  ldc.i4.5
0x59806  newobj   instance void Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo::.ctor(class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<string>> conditonColumnsSets, class [mscorlib]System.Collections.Generic.List`1<string> guidColumns, string idColumn, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataObjectType componentType)
0x5980b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo>::Add(var<u1>, !!T0)
0x59810  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Metadata.UpgradeMetadataComponentInfo> Microsoft.Crm.Metadata.UpgradeHelper::UpgradeMetadataComponentDict
0x59815  ret
```
