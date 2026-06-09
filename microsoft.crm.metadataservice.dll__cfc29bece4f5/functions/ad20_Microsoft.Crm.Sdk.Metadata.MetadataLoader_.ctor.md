# Microsoft.Crm.Sdk.Metadata.MetadataLoader::.ctor

- ea: `0xad20`
- end: `0xb660`
- name: `Microsoft.Crm.Sdk.Metadata.MetadataLoader::.ctor`
- size: `2368`
- prototype: ``
- caller_count: `21`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x8900`
- `0xd9e0`
- `0xda30`
- `0xda40`
- `0xda50`
- `0xda80`
- `0xdab0`
- `0xdad0`
- `0xdaf0`
- `0xdb90`
- `0xdce0`
- `0xdd20`
- `0xdd60`
- `0xe560`
- `0xe5a0`
- `0xe5f0`
- `0xf6c0`
- `0x11c70`
- `0x29080`
- `0x2ddd0`
- `0x3bf10`

## string_xrefs

- `0xae1e`: `linkedattributeid`
- `0xae9c`: `isrenameable`
- `0xb170`: `isrenameable`
- `0xae8a`: `managedpropertyparentcomponenttype`
- `0xae5d`: `canbesecuredforcreate`
- `0xae66`: `canbesecuredforread`
- `0xae6f`: `canbesecuredforupdate`
- `0xade8`: `validforcreateapi`
- `0xadf1`: `validforupdateapi`
- `0xadfa`: `validforreadapi`
- `0xb32b`: `cascadedelete`
- `0xb2fc`: `availableforcreate`
- `0xb305`: `availableforupdate`
- `0xb30e`: `availablefordelete`
- `0xb104`: `isairupdated`
- `0xb0ce`: `isdocumentrecommendationsenabled`
- `0xb200`: `isreadingpaneenabled`
- `0xb209`: `isquickcreateenabled`
- `0xb1dc`: `isreadonlyinmobileclient`
- `0xb224`: `canmodifymobileclientreadonly`
- `0xb182`: `cancreateattributes`
- `0xb18b`: `cancreatecharts`
- `0xb194`: `cancreateforms`
- `0xb19d`: `cancreateviews`
- `0xb10d`: `autocreateaccessteams`
- `0xb333`: `cascadelinkmask`

## pseudocode

```c

```

## disassembly

```asm
0xad20  ldarg.0
0xad21  ldc.i4.s 0x42
0xad23  newarr   [mscorlib]System.String
0xad28  dup
0xad29  ldc.i4.0
0xad2a  ldstr    aAttributetypei// "attributetypeid"
0xad2f  stelem.ref
0xad30  dup
0xad31  ldc.i4.1
0xad32  ldstr    aLogicalname// "logicalname"
0xad37  stelem.ref
0xad38  dup
0xad39  ldc.i4.2
0xad3a  ldstr    aAttributeid// "attributeid"
0xad3f  stelem.ref
0xad40  dup
0xad41  ldc.i4.3
0xad42  ldstr    aName// "name"
0xad47  stelem.ref
0xad48  dup
0xad49  ldc.i4.4
0xad4a  ldstr    aPhysicalname// "physicalname"
0xad4f  stelem.ref
0xad50  dup
0xad51  ldc.i4.5
0xad52  ldstr    aEntityid// "entityid"
0xad57  stelem.ref
0xad58  dup
0xad59  ldc.i4.6
0xad5a  ldstr    aAttributelogic// "attributelogicaltypeid"
0xad5f  stelem.ref
0xad60  dup
0xad61  ldc.i4.7
0xad62  ldstr    aMaxvalue// "maxvalue"
0xad67  stelem.ref
0xad68  dup
0xad69  ldc.i4.8
0xad6a  ldstr    aMinvalue// "minvalue"
0xad6f  stelem.ref
0xad70  dup
0xad71  ldc.i4.s 9
0xad73  ldstr    aAccuracy// "accuracy"
0xad78  stelem.ref
0xad79  dup
0xad7a  ldc.i4.s 0xA
0xad7c  ldstr    aAccuracysource// "accuracysource"
0xad81  stelem.ref
0xad82  dup
0xad83  ldc.i4.s 0xB
0xad85  ldstr    aLength// "length"
0xad8a  stelem.ref
0xad8b  dup
0xad8c  ldc.i4.s 0xC
0xad8e  ldstr    aMaxlength// "maxlength"
0xad93  stelem.ref
0xad94  dup
0xad95  ldc.i4.s 0xD
0xad97  ldstr    aAppdefaultvalu// "appdefaultvalue"
0xad9c  stelem.ref
0xad9d  dup
0xad9e  ldc.i4.s 0xE
0xada0  ldstr    aAggregateof// "aggregateof"
0xada5  stelem.ref
0xada6  dup
0xada7  ldc.i4.s 0xF
0xada9  ldstr    aAttributeof// "attributeof"
0xadae  stelem.ref
0xadaf  dup
0xadb0  ldc.i4.s 0x10
0xadb2  ldstr    aCalculationof// "calculationof"
0xadb7  stelem.ref
0xadb8  dup
0xadb9  ldc.i4.s 0x11
0xadbb  ldstr    aDisplaymask// "displaymask"
0xadc0  stelem.ref
0xadc1  dup
0xadc2  ldc.i4.s 0x12
0xadc4  ldstr    aIspkattribute// "ispkattribute"
0xadc9  stelem.ref
0xadca  dup
0xadcb  ldc.i4.s 0x13
0xadcd  ldstr    aAutonumberform// "autonumberformat"
0xadd2  stelem.ref
0xadd3  dup
0xadd4  ldc.i4.s 0x14
0xadd6  ldstr    aIscustomfield// "iscustomfield"
0xaddb  stelem.ref
0xaddc  dup
0xaddd  ldc.i4.s 0x15
0xaddf  ldstr    aAttributerequi// "attributerequiredlevelid"
0xade4  stelem.ref
0xade5  dup
0xade6  ldc.i4.s 0x16
0xade8  ldstr    aValidforcreate// "validforcreateapi"
0xaded  stelem.ref
0xadee  dup
0xadef  ldc.i4.s 0x17
0xadf1  ldstr    aValidforupdate// "validforupdateapi"
0xadf6  stelem.ref
0xadf7  dup
0xadf8  ldc.i4.s 0x18
0xadfa  ldstr    aValidforreadap// "validforreadapi"
0xadff  stelem.ref
0xae00  dup
0xae01  ldc.i4.s 0x19
0xae03  ldstr    aIsnullable// "isnullable"
0xae08  stelem.ref
0xae09  dup
0xae0a  ldc.i4.s 0x1A
0xae0c  ldstr    aYomiof// "yomiof"
0xae11  stelem.ref
0xae12  dup
0xae13  ldc.i4.s 0x1B
0xae15  ldstr    aIsauditenabled// "isauditenabled"
0xae1a  stelem.ref
0xae1b  dup
0xae1c  ldc.i4.s 0x1C
0xae1e  ldstr    aLinkedattribut// "linkedattributeid"
0xae23  stelem.ref
0xae24  dup
0xae25  ldc.i4.s 0x1D
0xae27  ldstr    aOptionsetid// "optionsetid"
0xae2c  stelem.ref
0xae2d  dup
0xae2e  ldc.i4.s 0x1E
0xae30  ldstr    aColumnnumber_0// "columnnumber"
0xae35  stelem.ref
0xae36  dup
0xae37  ldc.i4.s 0x1F
0xae39  ldstr    aIslogical// "islogical"
0xae3e  stelem.ref
0xae3f  dup
0xae40  ldc.i4.s 0x20
0xae42  ldstr    aIsmanaged// "ismanaged"
0xae47  stelem.ref
0xae48  dup
0xae49  ldc.i4.s 0x21
0xae4b  ldstr    aIssecured// "issecured"
0xae50  stelem.ref
0xae51  dup
0xae52  ldc.i4.s 0x22
0xae54  ldstr    aIntroducedvers// "introducedversion"
0xae59  stelem.ref
0xae5a  dup
0xae5b  ldc.i4.s 0x23
0xae5d  ldstr    aCanbesecuredfo// "canbesecuredforcreate"
0xae62  stelem.ref
0xae63  dup
0xae64  ldc.i4.s 0x24
0xae66  ldstr    aCanbesecuredfo_0// "canbesecuredforread"
0xae6b  stelem.ref
0xae6c  dup
0xae6d  ldc.i4.s 0x25
0xae6f  ldstr    aCanbesecuredfo_1// "canbesecuredforupdate"
0xae74  stelem.ref
0xae75  dup
0xae76  ldc.i4.s 0x26
0xae78  ldstr    aManagedpropert// "managedpropertylogicalname"
0xae7d  stelem.ref
0xae7e  dup
0xae7f  ldc.i4.s 0x27
0xae81  ldstr    aManagedpropert_1// "managedpropertyparentattributename"
0xae86  stelem.ref
0xae87  dup
0xae88  ldc.i4.s 0x28
0xae8a  ldstr    aManagedpropert_0// "managedpropertyparentcomponenttype"
0xae8f  stelem.ref
0xae90  dup
0xae91  ldc.i4.s 0x29
0xae93  ldstr    aIscustomizable// "iscustomizable"
0xae98  stelem.ref
0xae99  dup
0xae9a  ldc.i4.s 0x2A
0xae9c  ldstr    aIsrenameable// "isrenameable"
0xaea1  stelem.ref
0xaea2  dup
0xaea3  ldc.i4.s 0x2B
0xaea5  ldstr    aCanmodifyrequi// "canmodifyrequirementlevelsettings"
0xaeaa  stelem.ref
0xaeab  dup
0xaeac  ldc.i4.s 0x2C
0xaeae  ldstr    aCanmodifysearc// "canmodifysearchsettings"
0xaeb3  stelem.ref
0xaeb4  dup
0xaeb5  ldc.i4.s 0x2D
0xaeb7  ldstr    aCanmodifyaddit// "canmodifyadditionalsettings"
0xaebc  stelem.ref
0xaebd  dup
0xaebe  ldc.i4.s 0x2E
0xaec0  ldstr    aCanmodifyaudit// "canmodifyauditsettings"
0xaec5  stelem.ref
0xaec6  dup
0xaec7  ldc.i4.s 0x2F
0xaec9  ldstr    aDeprecatedvers// "deprecatedversion"
0xaece  stelem.ref
0xaecf  dup
0xaed0  ldc.i4.s 0x30
0xaed2  ldstr    aAttributeimemo// "attributeimemodeid"
0xaed7  stelem.ref
0xaed8  dup
0xaed9  ldc.i4.s 0x31
0xaedb  ldstr    aHasmultiplelab// "hasmultiplelabels"
0xaee0  stelem.ref
0xaee1  dup
0xaee2  ldc.i4.s 0x32
0xaee4  ldstr    aSourcetype// "sourcetype"
0xaee9  stelem.ref
0xaeea  dup
0xaeeb  ldc.i4.s 0x33
0xaeed  ldstr    aFormuladefinit// "formuladefinition"
0xaef2  stelem.ref
0xaef3  dup
0xaef4  ldc.i4.s 0x34
0xaef6  ldstr    aIsglobalfilter// "isglobalfilterenabled"
0xaefb  stelem.ref
0xaefc  dup
0xaefd  ldc.i4.s 0x35
0xaeff  ldstr    aIssortableenab// "issortableenabled"
0xaf04  stelem.ref
0xaf05  dup
0xaf06  ldc.i4.s 0x36
0xaf08  ldstr    aSourcetypemask// "sourcetypemask"
0xaf0d  stelem.ref
0xaf0e  dup
0xaf0f  ldc.i4.s 0x37
0xaf11  ldstr    aIsbasecurrency// "isbasecurrency"
0xaf16  stelem.ref
0xaf17  dup
0xaf18  ldc.i4.s 0x38
0xaf1a  ldstr    aBehavior// "behavior"
0xaf1f  stelem.ref
0xaf20  dup
0xaf21  ldc.i4.s 0x39
0xaf23  ldstr    aCanmodifybehav// "canmodifybehavior"
0xaf28  stelem.ref
0xaf29  dup
0xaf2a  ldc.i4.s 0x3A
0xaf2c  ldstr    aIssearchable// "issearchable"
0xaf31  stelem.ref
0xaf32  dup
0xaf33  ldc.i4.s 0x3B
0xaf35  ldstr    aIsretrievable// "isretrievable"
0xaf3a  stelem.ref
0xaf3b  dup
0xaf3c  ldc.i4.s 0x3C
0xaf3e  ldstr    aIsfilterable// "isfilterable"
0xaf43  stelem.ref
0xaf44  dup
0xaf45  ldc.i4.s 0x3D
0xaf47  ldstr    aCanmodifygloba// "canmodifyglobalfiltersettings"
0xaf4c  stelem.ref
0xaf4d  dup
0xaf4e  ldc.i4.s 0x3E
0xaf50  ldstr    aCanmodifyissor// "canmodifyissortablesettings"
0xaf55  stelem.ref
0xaf56  dup
0xaf57  ldc.i4.s 0x3F
0xaf59  ldstr    aInheritsfrom// "inheritsfrom"
0xaf5e  stelem.ref
0xaf5f  dup
0xaf60  ldc.i4.s 0x40
0xaf62  ldstr    aIsactive// "isactive"
0xaf67  stelem.ref
0xaf68  dup
0xaf69  ldc.i4.s 0x41
0xaf6b  ldstr    aIsdatasourcese// "isdatasourcesecret"
0xaf70  stelem.ref
0xaf71  stfld    string[] Microsoft.Crm.Sdk.Metadata.MetadataLoader::AttributeColumns
0xaf76  ldarg.0
0xaf77  ldc.i4.s 0x67
0xaf79  newarr   [mscorlib]System.String
0xaf7e  dup
0xaf7f  ldc.i4.0
0xaf80  ldstr    aName// "name"
0xaf85  stelem.ref
0xaf86  dup
0xaf87  ldc.i4.1
0xaf88  ldstr    aEntityid// "entityid"
0xaf8d  stelem.ref
0xaf8e  dup
0xaf8f  ldc.i4.2
0xaf90  ldstr    aLogicalname// "logicalname"
0xaf95  stelem.ref
0xaf96  dup
0xaf97  ldc.i4.3
0xaf98  ldstr    aPhysicalname// "physicalname"
0xaf9d  stelem.ref
0xaf9e  dup
0xaf9f  ldc.i4.4
0xafa0  ldstr    aExternalname// "externalname"
0xafa5  stelem.ref
0xafa6  dup
0xafa7  ldc.i4.5
0xafa8  ldstr    aExternalcollec// "externalcollectionname"
0xafad  stelem.ref
0xafae  dup
0xafaf  ldc.i4.6
0xafb0  ldstr    aIsactivity// "isactivity"
0xafb5  stelem.ref
0xafb6  dup
  ... truncated ...
```
